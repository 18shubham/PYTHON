
## **1. INDENTATION (MOST IMPORTANT!)**

Python uses **indentation** (spaces) to define code blocks, not curly braces `{}`.

```python
# ✅ CORRECT
if x > 5:
    print("Greater than 5")
    print("Still inside if block")

# ❌ WRONG - IndentationError
if x > 5:
print("This will crash")
```

**Rules:**
- Use **4 spaces** for each indentation level (not tabs!)
- All lines in the same block must have the same indentation
- Never mix tabs and spaces

---

## **2. COLONS (`:`) REQUIRED**

Colons are required after:
- `if`, `elif`, `else`
- `for`, `while`
- `def` (functions)
- `try`, `except`, `finally`
- `class`

```python
# ✅ CORRECT
if status == "UP":
    print("Server is up")

for server in servers:
    print(server)

def my_function():
    return "Hello"

# ❌ WRONG - Missing colons
if status == "UP"
    print("Server is up")
```

---

## **3. CASE SENSITIVITY**

Python is **case-sensitive**. `Server` and `server` are different!

```python
server = "web-01"
Server = "web-02"

print(server)  # web-01
print(Server)  # web-02
```

---

## **4. VARIABLE NAMING RULES**

**Rules:**
- Must start with letter or underscore: `my_var`, `_temp`
- Can contain letters, numbers, underscores: `server_1`, `web_server`
- Cannot start with number: ❌ `1server`
- Cannot use reserved words: ❌ `if`, `for`, `def`, `class`
- Case-sensitive: `myVar` ≠ `myvar`

**Convention (PEP 8):**
```python
# Variables and functions: snake_case
server_name = "web-01"
def check_server():
    pass

# Classes: PascalCase
class ServerManager:
    pass

# Constants: UPPER_CASE
MAX_CONNECTIONS = 100
API_KEY = "abc123"
```

---

## **5. COMMENTS**

```python
# Single-line comment

"""
Multi-line comment
or docstring
"""

x = 5  # Inline comment
```

---

## **6. STRING QUOTES**

All three work the same:

```python
name = "web-01"      # Double quotes
name = 'web-01'      # Single quotes
name = """web-01"""  # Triple quotes (for multi-line)

# Multi-line string
text = """
Line 1
Line 2
"""
```

---

## **7. LINE CONTINUATION**

**Implicit (inside brackets):**
```python
# ✅ BEST - No backslash needed
server_list = [
    "web-01",
    "web-02",
    "db-01"
]

# ✅ Works for long function calls
result = my_function(
    param1,
    param2,
    param3
)
```

**Explicit (backslash):**
```python
# Use backslash for long lines
total = value1 + value2 + \
        value3 + value4
```

---

## **8. ASSIGNMENT RULES**

```python
# Single assignment
x = 5

# Multiple assignment
x, y, z = 1, 2, 3

# Same value to multiple variables
a = b = c = 0

# Swap values (Python magic!)
x, y = y, x
```

---

## **9. COMPARISON OPERATORS**

```python
==  # Equal to
!=  # Not equal to
>   # Greater than
<   # Less than
>=  # Greater than or equal
<=  # Less than or equal

# Chaining (Pythonic!)
if 70 <= cpu < 90:
    print("Warning range")
```

---

## **10. LOGICAL OPERATORS**

```python
and  # Both must be True
or   # At least one must be True
not  # Inverts True/False

# Example
if cpu > 90 and status == "UP":
    print("High CPU on running server")

if status == "DOWN" or cpu > 95:
    print("Alert!")
```

---

## **11. MEMBERSHIP OPERATORS**

```python
# Check if item is in collection
if "web-01" in server_list:
    print("Found")

if "error" in log_line:
    print("Error found")

# Check if NOT in collection
if "db-01" not in server_list:
    print("Not found")
```

---

## **12. NONE VALUE**

```python
# None represents "no value"
result = None

if result is None:
    print("No result")

# Use 'is' for None, not '=='
if result is not None:
    print("Has result")
```

---

## **13. TRUTHY AND FALSY VALUES**

**Falsy (evaluates to False):**
- `False`
- `0`
- `""` (empty string)
- `[]` (empty list)
- `{}` (empty dict)
- `None`

**Everything else is Truthy!**

```python
servers = []

if servers:  # False because empty
    print("Has servers")
else:
    print("No servers")  # This runs

if "text":  # True because not empty
    print("Has text")  # This runs
```

---

## **14. PASS STATEMENT**

Use `pass` when you need a placeholder:

```python
def future_function():
    pass  # TODO: implement later

if condition:
    pass  # Do nothing
else:
    print("Something")
```

---

## **15. IMPORT RULES**

```python
# Import entire module
import os

# Import specific function
from os import path

# Import with alias
import numpy as np

# Import multiple
from datetime import datetime, timedelta

# Avoid this!
from module import *  # Bad practice
```

---

## **COMMON MISTAKES TO AVOID:**

```python
# ❌ Missing colon
if x > 5
    print("test")

# ❌ Wrong indentation
if x > 5:
print("test")

# ❌ Using = instead of ==
if x = 5:  # Assignment, not comparison!

# ❌ Forgetting quotes
server = web-01  # NameError - needs quotes

# ❌ Modifying list while looping
for item in my_list:
    my_list.remove(item)  # Dangerous!
```

---

## **PYTHON STYLE GUIDE (PEP 8) - KEY POINTS:**

1. **4 spaces** for indentation
2. **79 characters** max line length (flexible)
3. **2 blank lines** between functions
4. **Spaces around operators**: `x = 5` not `x=5`
5. **No spaces** inside brackets: `list[0]` not `list[ 0 ]`
6. **snake_case** for variables/functions
7. **PascalCase** for classes
8. **UPPER_CASE** for constants

---

## **ZEN OF PYTHON (Type `import this`)**

Key principles:
- **Simple is better than complex**
- **Explicit is better than implicit**
- **Readability counts**
- **There should be one obvious way to do it**

---

## **QUICK REFERENCE CARD:**

```python
# Variables
my_var = 10

# If statement
if condition:
    # do something
elif other_condition:
    # do something else
else:
    # default action

# For loop
for item in collection:
    # process item

# While loop
while condition:
    # do something

# Function
def my_function(param):
    return result

# Try/Except
try:
    # risky code
except ErrorType:
    # handle error

# List comprehension
new_list = [x*2 for x in old_list if x > 5]

# Dictionary
my_dict = {"key": "value"}

# File reading
with open("file.txt", "r") as f:
    content = f.read()
```

---

Want me to clarify any specific rule? Or ready to continue with the tasks? 🚀
