 Task 5: Filtering and Transforming Data

### Project Title: Deployment Result Filter 🚀

### 🎯 Goal

The objective of this task was to replace a traditional, multi-line `for` loop with a single, highly efficient **List Comprehension**. This is a crucial step towards writing **"Pythonic"** code—code that is not only correct but also concise and performant, which is highly valued in DevOps scripting for processing large logs or API responses.

### ⚙️ Core Concepts Covered

1.  **List Comprehension:** A single-line syntactic construct used to create a new list based on an existing sequence.
2.  **Filtering:** The `if` condition within the comprehension allows the script to selectively include only the desired items (in this case, successful deployments).
3.  **Transformation:** The output expression defines which part of the filtered item is kept (in this case, transforming the whole dictionary into just the IP address string).

### 📝 The Task

Given a `deployment_log` (a list of dictionaries), create a new list named `success_ips` that contains only the **IP addresses** of the servers where the deployment result was `"SUCCESS"`.

### 💾 Initial Data

```python
deployment_log = [
    {"server": "web-01", "ip": "10.0.1.5", "result": "SUCCESS"},
    {"server": "web-02", "ip": "10.0.1.6", "result": "FAILURE"},
    {"server": "db-01", "ip": "10.0.1.7", "result": "SUCCESS"},
    {"server": "cache-01", "ip": "10.0.1.8", "result": "FAILURE"}
]
```

### ✅ Solution Code (List Comprehension)

```python
# new_list = [ <output_expression> for <item> in <iterable> if <condition> ]

success_ips = [item['ip'] for item in deployment_log if item['result'] == 'SUCCESS']

print(success_ips)
# Output: ['10.0.1.5', '10.0.1.7']
```

### 💡 Key Takeaway: Structure

The power of List Comprehension lies in its structure, which reads logically from left to right:

| Part of Comprehension | What it Does |
| :--- | :--- |
| **`item['ip']`** | **Tells Python what to put in the final list (the IP).** |
| **`for item in deployment_log`** | **Tells Python what to iterate over (each log dictionary).** |
| **`if item['result'] == 'SUCCESS'`** | **Tells Python the rule for filtering (only successful results).** |

This single-line command is the preferred method for data manipulation in professional Python scripts.
