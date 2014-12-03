# Writing Idiomatic Python

This post is a summary of the book "Writing Idiomatic Python".

## Working with Data:

### Use list comprehension:

To transform 1 list to another, always use list comprehension

```python
# Bad code:
a = range(10)
b = list()
for x in a:
    if is_prime(x):
        b.append(x + 5)

# Good code:
a = range(10)
b = [x + 5 for x in a if is_prime(x)]
```

Similarly, apply this to dictionaries:

```python
# Bad code:
user_email = {}
for user in users_list:
    if user.email:
        user_email[user.name] = user.email

# Good code
user_email = {user.name: user.email for user in users_list if user.email}
```

### Use default parameter of dict.get to provide default values:

```python
my_map = {
    'admin': 'RR',
    'language': 'Python'
}
# Bad code:
my_admin = ''
if 'admin' in my_map:
    my_admin = my_map['admin']

# Good code:
my_admin = my_map.get('admin', '')
```

### Use format function for formatting strings:

```python
user = { 'name': 'RR', 'language': 'Python' }
# Bad code:
print 'Name: ' + user['name'] + ' - Language: ' + user['language']
# Good code:
print 'Name: {} - Language: {}'.format(user['name'], user['language'])
```

### Use ''.join to create string from list

```python
# Bad code
str = ''
for i in my_list:
    str += i
# Good code
str = ''.join(my_list)
```

### Chaining functions

```python
# Bad code:
formatted_str = my_str.strip()
formatted_str = formatted_str.upper()
formatted_str = formatted_str.replace(':', ',')

# Good code
formatted_str = my_str.strip().upper().replace(':', ',')
```

### Prefer generator expression to list comprehension for simple iteration

```python
# Bad code:
for name in [name.upper() for name in super_long_name_list()]:
    process(name)
# Good code:
for name in (name.upper() for name in super_long_name_list()):
    process(name)
```

The difference between the two is that: list comprehension generates a list object and fills in all the elements immediately --> you can run out of memory right after this (before you even enter the loop).

Generator expression: generates each element "on-demand"

How can *super_long_name_list()* be implemented efficiently? It can be done using keyword yield:

```python
# Bad code:
def get_element(data):
    return [very_complicated_calculation1(data),
            very_complicated_calculation2(data),
        very_complicated_calculation3(data)]

# Good code:
def get_element(data):
    yield very_complicated_calculation1(data)
    yield very_complicated_calculation2(data)
    yield very_complicated_calculation3(data)
```

### Use context manager

```python
# Bad code: file can be left opened:

f = open('my_file.txt', 'w')
f.write('Hello')
assert not 'something true'
f.close()

# Handle open & close now!
with open('my_file.txt', 'w') as f:
    f.write('Hello')
    assert not 'something true'
# This is known as context managers. In Java 7, this concept is implemented.
```

### Tuple to unpack data

```python
# Bad code:
my_list = ['RR', 'Python', 123]
my_name = my_list[0]
my_language = my_list[1]
my_number = my_list[2]

# Good code:
(my_name, my_language, my_number) = my_list
```

Use *_* as placeholder for data that should be ignored:

```python
# Bad code:
(my_name, my_language, my_number_which_isnt_needed) = my_list

# Good code:
(my_name, my_language, _) = my_list
```

