Here are some key thumb rules to follow in Python:
Naming conventions:

Use snake_case for variables and functions: my_variable, calculate_total()
Use PascalCase for classes: MyClass, UserAccount
Use UPPER_CASE for constants: MAX_SIZE, API_KEY
Make names descriptive: user_count is better than uc

Code style:

Follow PEP 8 (Python's style guide)
Use 4 spaces for indentation, not tabs
Keep lines under 79-80 characters when possible
Put two blank lines between function definitions
Use spaces around operators: x = 5 not x=5

Best practices:

Use if __name__ == "__main__": for scripts that can be imported
Prefer list comprehensions over loops when simple: [x*2 for x in range(10)]
Use with statements for file operations to ensure proper cleanup
Don't use mutable default arguments: avoid def func(lst=[]):
Use f-strings for formatting: f"Hello {name}" instead of older methods

Pythonic thinking:

"Easier to ask forgiveness than permission" (EAFP): use try/except rather than checking everything first
Iterate directly over collections: for item in items: not for i in range(len(items)):
Use enumerate() when you need indices: for i, item in enumerate(items):
Unpack tuples: x, y = (1, 2)

Common wisdom:

"Explicit is better than implicit" and "Simple is better than complex" (from the Zen of Python - try typing import this)
Write docstrings for functions and classes
Avoid using * imports: from module import *
