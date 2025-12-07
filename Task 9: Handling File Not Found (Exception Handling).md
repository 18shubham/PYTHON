Task 9: Handling File Not Found (Exception Handling)**.

-----

## 📄 README.md for Task 9: Configuration File Reader with Error Handling 🛡️

### Project Title: Robust Config Reader (`read_config_file`)

### 🎯 Goal

The objective of this task was to master **Exception Handling** using the `try...except` block. This is a critical skill in DevOps for creating **fault-tolerant scripts** that do not crash when a resource is missing or unavailable (like a missing configuration file, a dropped network connection, or invalid user input).

### ⚙️ Core Concepts Covered

1.  **Exception Handling:** The mechanism (`try`/`except`) Python uses to manage runtime errors gracefully, preventing the entire program from terminating.
2.  **`try` Block:** Contains the code that may raise an exception (e.g., file operations, network calls).
3.  **`except FileNotFoundError:`:** Specifically catches the error that occurs when a requested file does not exist, allowing for targeted error responses.
4.  **`with open(...) as file:`:** The standard, safe way to handle file I/O, ensuring the file resource is properly closed even if an error occurs.

### 📝 The Task

Create a function named `read_config_file` that attempts to open and read a file. If the file is found, it prints the content. If the file is missing, it catches the `FileNotFoundError` and prints a graceful warning message instead of crashing.

### ✅ Solution Code

```python
import os

# 1. Define the Function with try/except
def read_config_file(filename):
    
    try:
        # Attempt the risky operation
        with open(filename, 'r') as file:
            content = file.read()
        
        # Runs ONLY if the 'try' block was successful
        print(f"SUCCESS: File content of '{filename}' is: {content.strip()}")

    # Catch the specific error (a missing file)
    except FileNotFoundError:
        print(f"ERROR: Configuration file '{filename}' not found. Using default settings.")
    
    # Optional: Catch any other unexpected error
    except Exception as e:
        print(f"UNKNOWN ERROR reading {filename}: {e}")


# --- Testing ---
# Create a dummy file for the successful test case
with open("test_config.txt", 'w') as f:
    f.write("max_cpu_limit=95\n")

print("--- Test 1: File Found ---")
read_config_file("test_config.txt") 

print("\n--- Test 2: File Not Found ---")
read_config_file("missing.txt") 

# Clean up the test file
os.remove("test_config.txt")
```

### 💡 Key Takeaway: Robustness

By catching the specific exception, you ensure that even if a critical resource (like a config file) is absent, your main script logic can continue running. This pattern is fundamental to professional scripting and prevents cascades of failures in production systems.

