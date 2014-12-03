# Python

## Python Design Philosophy

Khi học một ngôn ngữ lập trình, điều quan trọng nhất là học những điểm mới của ngôn ngữ đó, nói cách khác là "Design Philosophy" của ngôn ngữ đó.

Những design philosophy của Python: (The Zen of Python)

- Beautiful is better than ugly.
- Explicit is better than implicit.
- Simple is better than complex
- Complex is better than complicated.
- Flat is better than nested.
- Sparse is better than dense.
- Readability counts.
- Special cases aren't special enough to break the rules. Although practicality beats purity.
- Errors should never pass silently. Unless explicitly silenced.
- In the face of ambiguity, refuse the temptation to guess.
- There should be one-- and preferably only one --obvious way to do it.
- Now is better than never.
- If the implementation is hard to explain, it's a bad idea.
- If the implementation is easy to explain, it may be a good idea.
- NameSpaces are one honking great idea -- let's do more of those!

Để đọc lại design philosophy:

```python
import this
```

### Ví dụ:

Beautiful is better than ugly:

```python
# Swap 2 values:
a, b = b, a
```

Special cases aren't special enough to break the rules: A string of length 1 is not special enough to deserve a dedicated char type.

Although practicality beats purity: That's why we still have method `chr()` and `ord()`

Now is better than never:

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


## Python - Interpreted language

Ngôn ngữ lập trình có thể được chia ra làm 2 loại:

- Compiled languages: Các ngôn ngữ được dịch ra, ví dụ: C++. Khi chạy một đoạn code C++, đầu tiên bạn phải compile (với Windows, phải dịch ra file EXE, còn trong linux thì dịch ra executable file, thường không có extension). Rồi sau đó mới chạy được.
- Interpreted languages: Sau khi code, bạn chạy luôn, không cần compile.

## Basic Syntax - Data types

Giống với các ngôn ngữ như C++, Python cũng có các kiểu dữ liệu cơ bản như boolean, số nguyên, số thực, ký tự... Tuy nhiên, khi khai báo biến, bạn không cần nói rõ kiểu dữ liệu. Interpreter sẽ tự động xác định kiểu dữ liệu.

```python
a = 1
b = True
```

## Basic Syntax - Conditions & Loops:

Conditions (điều kiện)

```python
if True:
    print 'Hello'
else:
    print 'What???'
```

Vòng lặp:

```python
for i in xrange(1,10):
    print i

a = [10, 20, 30]
for x in a:
    print x
```

## Những cú pháp khác biệt của Python

```python
a = [x for x in xrange(1, 10)]
```

