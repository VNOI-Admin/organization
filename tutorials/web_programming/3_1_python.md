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

- Code must be correctly indented
- Should follow PEP8

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

## Cú pháp cơ bản của Python

Để học syntax cơ bản của Python, bạn có thể lên [Codecademy](http://www.codecademy.com/)

Sau khi biết syntax cơ bản, bạn đã có thể bắt đầu code những thứ cơ bản. Hãy thử code những bài A B Codeforces, hoặc những bài dễ của VOJ như POST, LIS... để quen với syntax. Khi học, hãy để ý những điểm khác nhau của Python và C++, và suy nghĩ xem những philosophy thể hiện ở chỗ nào.

Sau đấy, để code Python giống như pro, đọc tiếp tutorial 3.2. Idiomatic Python.
