
## 🛠️ Task 3: Processing a List of Server IPs

**Concept Focus:** Lists, `for` Loops, and String Formatting (f-strings).

**Scenario:** You have a list of IP addresses representing servers that need to be checked. You need to iterate over this list and format the output neatly, simulating a network check.

**The Initial Configuration Data:**

```python
ip_list = [
    "10.0.1.5",
    "10.0.1.6",
    "10.0.1.7",
    "10.0.1.8"
]
```

### 🎯 Your Task:

1.  **Iteration:** Write a **`for` loop** that iterates over the `ip_list`.

2.  **Formatting:** Inside the loop, use an **f-string** (formatted string literal) to print a message for each IP address in the following exact format:

    **`Pinging server: 10.0.1.X`**

**Your Action:** Write the Python code containing the `for` loop and the f-string and submit your attempt\!


I'm glad you're sticking to the practice\! Here is the solution for the iteration and string formatting part of **Task 3**.

-----

## ✅ Task 3: Optimal Solution (Iteration and Formatting)

### The Code

```python
ip_list = [
    "10.0.1.5",
    "10.0.1.6",
    "10.0.1.7",
    "10.0.1.8"
]

# 1. Iteration and 2. Formatting
for ip_address in ip_list:
    print(f"Pinging server: {ip_address}")
```

### Output:

```
Pinging server: 10.0.1.5
Pinging server: 10.0.1.6
Pinging server: 10.0.1.7
Pinging server: 10.0.1.8
```

### 🐞 Identifying Errors/Bugs (Common Mistakes)

If an error were to occur here, the most common issues beginners face are:

  * **`IndentationError`:** Forgetting to indent the `print()` line inside the loop. In Python, code blocks (like the body of a `for` loop) **must** be indented.
  * **`SyntaxError`:** Missing the colon (`:`) at the end of the `for` line.
  * **Missing `f`:** Forgetting the `f` before the opening quote of the string literal (`f"..."`), which prevents the variable inside the curly braces (`{ip_address}`) from being substituted correctly.

### 💡 Explain the Concepts

This task tested two fundamental Python concepts crucial for scripting:

1.  **`for` Loops:** The `for` loop is used to iterate over items in a **sequence** (like a list, tuple, or string). The syntax `for item in sequence:` temporarily assigns each item in the sequence to the variable (`ip_address` in this case) for the duration of one pass through the loop. This is essential for processing large batches of data (like servers, logs, or file lines).
2.  **f-strings (Formatted String Literals):** Introduced in Python 3.6, f-strings are the modern and most readable way to embed expressions or variable values directly inside a string. You prepend the string with `f` and wrap the variable name in curly braces (`{}`).

-----

## 🚀 Propose the Next Task

Let's combine what we've learned (dictionaries and loops) and introduce **Nested Data Structures**, which are ubiquitous in **JSON/API responses** you deal with in DevOps.

