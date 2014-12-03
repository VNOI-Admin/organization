# Writing Idiomatic Python

## Control Structures & functions:

### Avoid comparing directly to True, False and None:

For any object, there is a "truthiness" associated with the object. When checking a if condition is true, prefer relying on the implicit "truthiness" of the object in the conditional statement. The following are considered false:

- None
- False
- Zero for numeric types
- Empty sequences
- Empty dictionaries
- A value of 0 or False returned when either `__len__` or `__nonzero__` is called

Everything else is considered True.

Bad codes:

```python
if foo == True:
    if bar == False:
        if xoo == None:
```

Good codes:

```python
if foo:
    if not bar:
        if xoo is None:
```

Why? There are many reasons:

- Most obvious: if you change from boolean types --> numeric types: still works
- At deeper level, the reason is based on the difference between *equality* and *identity*. Using == determines if two objects have same value, as defined by their *_eq* attribute. Using is determines if the two object are actually the same object. As a consequence, avoid comparing directly to False and None for empty sequence like `[]`, `{}` and `()`.

### Avoid repeating variable name in compound if statement

Bad code:

```python
if name == 'RR' or name == 'flash' or name == 'Khanh':
```

Good code:
```python
if name in ('RR', 'flash', 'Khanh'):
```

### Avoid placing conditional branch code on same line as colon:

Bad code:

```python
if True: print "Hello"
```

Good code:

```python
if True:
    print "Hello"
```

### Use for loop correctly:

Bad code:

```python
alpha = ['a', 'b', 'c']
index = 0
for c in alpha:
    print '{} - {}'.format(index, c)
```

Good code:

```python
alpha = ['a', 'b', 'c']
for index, c in enumerate(alpha):
    print '{} - {}'.format(index, c)
```

### Use else to avoid boolean flag in loop:

Bad code:

```python
has_prime = False
a = [2, 4, 6, 8]
```

