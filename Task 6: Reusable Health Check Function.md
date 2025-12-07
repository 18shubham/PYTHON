 Task 6: Reusable Health Check Function

### Project Title: CPU Status Function (`get_cpu_status`) 💡

### 🎯 Goal

The objective of this task was to introduce and master **Functions**. In DevOps, this is essential for creating **modular and reusable code**. Instead of writing the same `if/elif/else` logic repeatedly, we encapsulate it into a function that can be called anywhere, improving code cleanliness and maintainability.

### ⚙️ Core Concepts Covered

1.  **Function Definition (`def`):** The syntax used to create a new, reusable block of code.
2.  **Parameters:** Variables defined in the function signature (`cpu_load`) that act as placeholders for input data.
3.  **`return` Statement:** How a function sends a result back to the calling part of the script, making the function's output usable.
4.  **Modular Logic:** Structuring complex conditional checks inside the function to provide a standardized, simplified output (e.g., transforming a number like `92` into a string like `"CRITICAL"`).

### 📝 The Task

Create a function named `get_cpu_status` that accepts a `cpu_load` integer and uses `if/elif/else` logic to return one of three status strings: `"CRITICAL"` (for \> 90), `"WARNING"` (for 80-90 inclusive), or `"OK"` (for \< 80).

### ✅ Solution Code

```python
# 1. Function Definition
def get_cpu_status(cpu_load):
    # Conditional logic using the passed-in parameter
    if cpu_load > 90:
        return "CRITICAL"
    # Pythonic check: only need to check the lower bound (80)
    elif cpu_load >= 80: 
        return "WARNING"
    # Final fallback for all other cases (below 80)
    else:
        return "OK"

# 2. Test Cases (Demonstrating Reusability)
cpu_server_1 = 92
cpu_server_2 = 75

status_1 = get_cpu_status(cpu_server_1)
status_2 = get_cpu_status(cpu_server_2)

print(f"Server 1 (92%) Status: {status_1}")
print(f"Server 2 (75%) Status: {status_2}")
```

### 💡 Key Takeaway: Reusability

Functions are the foundation of well-structured scripting. By defining the logic once in `get_cpu_status()`, you can call it a thousand times with different inputs, knowing that the status classification logic remains consistent. This is vital for managing infrastructure at scale.

-----

