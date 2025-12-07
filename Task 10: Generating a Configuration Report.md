
Task 10: Generating a Configuration Report 📝

### Project Title: Report Writer (`write_report`)

### 🎯 Goal

The objective of this final foundational task was to master **File Output (I/O)**. This is essential in scripting for logging results, generating summary reports, and writing new configuration files. The main focus was on using the correct mode for opening a file and ensuring proper formatting using the newline character.

### ⚙️ Core Concepts Covered

1.  **File I/O (`with open`):** Using the safe `with open(filename, mode)` context manager to ensure files are always closed, preventing data corruption or resource leaks.
2.  **File Modes (`'w'`):** Using the `'w'` (write) mode to create a new file or overwrite an existing one.
3.  **Iteration for Writing:** Using a `for` loop to process a list of data, writing each item to the file individually.
4.  **Newline Character (`\n`):** The crucial technique of concatenating the newline character to each line written to the file to ensure the final report is readable and not one continuous string.

### 📝 The Task

Create a function named `write_report` that accepts a filename and a list of strings (`report_lines`). The function must write each string in the list to the file, adding a newline (`\n`) after every line.

### 💾 Initial Data

```python
report_lines = [
    "--- SERVER HEALTH REPORT ---", 
    "CPU Check: OK", 
    "Memory Check: WARNING", 
    "Deployment: SUCCESS"
]
```

### ✅ Solution Code

```python
report_lines = [
    "--- SERVER HEALTH REPORT ---", 
    "CPU Check: OK", 
    "Memory Check: WARNING", 
    "Deployment: SUCCESS"
]

def write_report(filename, lines_list):
    try:
        # Open the file in 'w' (write) mode using the safe context manager
        with open(filename, 'w') as f:
            # Loop through the list of strings
            for line in lines_list:
                # Write the line, and crucially, add the newline character
                f.write(line + '\n')
        
        return f"Report successfully created: {filename}"
        
    except Exception as e:
        return f"File writing failed: {e}"

# Test the function
status_message = write_report("health_summary.txt", report_lines)
print(status_message)
```

### 💡 Key Takeaway: Formatting File Output

File writing requires explicit instruction on where line breaks should occur. Always remember that the **`f.write()`** method does not automatically add a newline. For readable reports, you must append **`+ '\n'`** to the string being written during the loop.

-----

