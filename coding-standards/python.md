# Python Coding Standards

This document outlines the style guide and best practices for Python development, emphasizing readability, consistency, and maintainability. Adhering to these standards ensures that the codebase remains clean and easy to understand for all contributors.

## PEP 8: The Style Guide for Python Code

[PEP 8](https://www.python.org/dev/peps/pep-0008/) is the official style guide for Python code. It covers topics such as code layout, naming conventions, and whitespace. All Python code should follow PEP 8.

### Key PEP 8 Guidelines:

- **Indentation:** Use 4 spaces per indentation level.
- **Line Length:** Limit all lines to a maximum of 79 characters.
- **Imports:**
  - Imports should be on separate lines.
  - Imports should be grouped in the following order:
    1.  Standard library imports.
    2.  Related third-party imports.
    3.  Local application/library specific imports.
- **Whitespace:**
  - Avoid extraneous whitespace in the following situations:
    - Immediately inside parentheses, brackets, or braces.
    - Immediately before a comma, semicolon, or colon.
  - Use a single space around operators.
- **Naming Conventions:**
  - `lowercase` for functions and variables.
  - `lower_case_with_underscores` for functions and variables.
  - `UPPERCASE` for constants.
  - `UPPER_CASE_WITH_UNDERSCORES` for constants.
  - `CapWords` for classes.
  - `_single_leading_underscore`: weak "internal use" indicator.
  - `single_trailing_underscore_`: used by convention to avoid conflicts with Python keywords.
  - `__double_leading_underscore`: when naming a class attribute, invokes name mangling.

## The Zen of Python (PEP 20)

[PEP 20](https://www.python.org/dev/peps/pep-0020/), also known as "The Zen of Python," is a collection of 19 guiding principles for writing computer programs that influence the design of the Python language.

```
Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!
```

## Docstring Conventions (PEP 257)

[PEP 257](https://www.python.org/dev/peps/pep-0257/) describes the conventions for docstrings, which are string literals that appear as the first statement in a module, function, class, or method definition.

- Docstrings should be enclosed in triple quotes (`"""`).
- The docstring for a function or method should summarize its behavior and document its arguments, return value(s), and any exceptions raised.
- The first line of a docstring should be a short, concise summary of the object's purpose.

Example:
```python
def add(a, b):
    """
    Adds two numbers and returns the result.

    :param a: The first number.
    :param b: The second number.
    :return: The sum of the two numbers.
    """
    return a + b
```

## Type Hints (PEP 484)

[PEP 484](https://www.python.org/dev/peps/pep-0484/) introduced type hints, which can be used to indicate the types of variables and function return values. Type hints improve code clarity and can be used by static analysis tools to find bugs.

Example:
```python
def greeting(name: str) -> str:
    return 'Hello ' + name
```

## General Best Practices

- **Explicit is better than implicit:** Write code that is clear and easy to understand.
- **One statement per line:** Avoid multiple statements on a single line.
- **Return statements:** A function should have a single return point for its normal course, but can have multiple return points for error cases.
- **Use `with` for file handling:** The `with` statement ensures that files are closed correctly, even if exceptions are raised.

## Idiomatic Python ("Pythonic" Code)

- **Unpacking:** Use tuple unpacking for assignments.
  ```python
  a, b = 1, 2
  ```
- **List Comprehensions:** Use list comprehensions for creating lists.
  ```python
  squares = [x**2 for x in range(10)]
  ```
- **Generators:** Use generator expressions for iterating over large sequences to save memory.
  ```python
  total = sum(i for i in range(1000000))
  ```
- **String Formatting:** Use f-strings for string formatting (Python 3.6+).
  ```python
  name = "World"
  message = f"Hello, {name}!"
  ```
- **Checking for `None`:** Use `is` or `is not` to check for `None`.
  ```python
  if my_var is not None:
      # ...
  ```

By following these standards and best practices, we can create a Python codebase that is clean, readable, and maintainable.
