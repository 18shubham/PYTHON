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

That's a great idea\! Before introducing functions, let's take a moment to solidify the five core concepts we've covered. This summary will serve as a quick reference for the foundational scripting skills crucial for **DevOps and Cloud**.

-----

## 💡 Summary of Concepts (Tasks 1-5)

| Task | Core Concept | Python Structure | DevOps Application |
| :--- | :--- | :--- | :--- |
| **Task 1 & 2 (Part 1)** | **Dictionaries** | `my_dict["key"] = value` | Handling single server configurations (YAML, JSON). |
| **Task 2 (Part 2)** | **Conditional Logic** | `if/elif/else` & `.get()` | Creating alerts and making scripts fault-tolerant against missing data. |
| **Task 3 & 4** | **`for` Loops** | `for item in list:` | Processing lists of resources (servers, users, log lines). |
| **Task 4** | **Nested Data** | `list[i]['key']` | Parsing complex data from APIs or configuration files (JSON). |
| **Task 5** | **List Comprehension** | `[expr for item in list if cond]` | Efficiently filtering and transforming data in a single, "Pythonic" line. |

-----

## 🧠 Detailed Review of Methods and Concepts

### 1\. Dictionaries and Key Access (Tasks 1 & 2)

Dictionaries (`dict`) are Python's way of storing data in **key-value pairs**. They are the workhorse for handling structured data like server configuration files (which are often JSON or YAML).

  * **Access/Update:** We use square brackets with the key name to either retrieve or change a value:
    ```python
    config["status"] = "maintenance"
    print(config["ip_address"])
    ```
  * **Safe Access (`.get()`):** This is critical for robust scripting. If you try to access a key that doesn't exist using square brackets, your script will crash with a **`KeyError`**. The `.get()` method prevents this by returning a default value if the key is missing.
    ```python
    # Returns "N/A" if 'latency' is not found, preventing a crash
    latency = metrics.get("latency", "N/A")
    ```

### 2\. Control Flow (`if/elif/else`) (Tasks 2 & 4)

Control flow dictates the order in which code executes, allowing your scripts to make decisions.

  * **Structure:** Every `if`, `elif`, or `else` statement that defines a code block **must** end with a colon (`:`).
  * **Indentation is Law:** The code block that belongs to the condition *must* be indented. This indentation defines the scope of the code.
    ```python
    # The condition block:
    if cpu_load >= 90:
        # This line is indented, so it runs only if load >= 90
        print("Alert!")
    ```

### 3\. `for` Loops and Iteration (Tasks 3 & 4)

The `for` loop is essential for automating tasks across multiple items (e.g., looping over a list of servers to deploy a patch).

  * **Syntax:** The loop temporarily assigns a variable (`item`) to each element in an iterable object (`list` or `dictionary`).
    ```python
    for server in server_inventory:
        # 'server' is the temporary variable holding the current dictionary
        print(server['name'])
    ```
  * **Nested Access (Task 4):** When looping over a **List of Dictionaries** (common in API responses), the temporary variable (`server`) inside the loop is a dictionary, allowing you to access its keys:
    ```python
    # server_inventory is a LIST of DICTIONARIES
    for server in server_inventory:
        if server['status'] == 'DOWN': # Accessing the dictionary key
            print("Action!")
    ```

### 4\. List Comprehension (Task 5)

List comprehension is a powerful, single-line technique for creating a new list by iterating over an existing sequence while optionally applying **filtering** and **transformation**.

  * **Efficiency:** It achieves the same result as a standard `for` loop combined with an `if` statement and the `.append()` method, but in a highly readable and typically faster way.
  * **Structure Breakdown:**
    $$\text{new\_list} = \left[ \quad \text{Expression (what to keep)} \quad \text{for item in iterable} \quad \text{if condition (optional)} \quad \right]$$
      * **Transformation:** We took the dictionary (`item`) and *transformed* it into just the IP address string (`item['ip']`).
      * **Filtering:** We added the `if item['result'] == 'SUCCESS'` condition to filter the original data.

This comprehensive overview confirms your mastery of the fundamental building blocks. You are now perfectly set up to move on to **Functions**\!
