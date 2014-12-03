# Writing Idiomatic Python

This post is a summary of the book "Writing Idiomatic Python".

## General advices:

- When coding, always follow PEP8 (standard formatting rules). If you use Sublime text, install plugin SublimeLinter and SublimeLinter-flake8
- Use *if __name__ == '__main__'* pattern to allow file to be both imported and run directly:

```python
def my_add(a, b):
    return a + b

if __name__ == '__main__':
    # Get arguments
    a = float(sys.argv[1])
    b = float(sys.argv[2])
    print "a + b = {}".format(a + b)
```

- Prefer absolute imports over relative imports
```python
# Bad code
from ...package import other_module
# Good code
import package.other_module
```

- Arrange import in standard order:
    1. Standard library modules
    2. Third party library modules installed in site-packages
    3. Modules local to current project.

- Learn to use [itertools](https://docs.python.org/library/itertools.html#recipes)

