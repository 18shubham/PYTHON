Task 7: Network Latency Calculator 🌐

### Project Title: Latency Averager (`calculate_average_latency`)

### 🎯 Goal

The objective of this task was to combine **Functions** with a new, immutable data structure: the **Tuple**. The goal was to create a reusable function capable of performing a calculation (finding the average) on data passed to it, reinforcing the concept of modular and flexible scripting.

### ⚙️ Core Concepts Covered

1.  **Tuple Data Structure:** An ordered collection of items, defined using parentheses `()`, that is **immutable** (cannot be changed after creation). Ideal for fixed measurements or data records.
2.  **Function Parameters:** Ensuring the function uses the data passed to it, rather than defining fixed data internally, which guarantees **reusability**.
3.  **Built-in Functions:** Utilizing Python's powerful, native functions like `sum()` and `len()` for simple, efficient collection processing.

### 📝 The Task

Create a function named `calculate_average_latency` that accepts one parameter (a tuple of latency values). The function must calculate and return the average latency.

### 💾 Initial Data

```python
latency_data = (25, 30, 35) # A tuple containing three latency measurements
```

### ✅ Solution Code

```python
# The required test data (defined outside the function)
latency_data = (25, 30, 35) 

# 1. Function Definition with a parameter
def calculate_average_latency(latency_tuple):
    
    # 2. Calculation using sum() and len() on the input parameter
    # Average = sum of all elements / count of all elements
    average = sum(latency_tuple) / len(latency_tuple)
    
    # 3. Return the result
    return average

# 4. Test: Call the function and print the result
result = calculate_average_latency(latency_data)

print(f"Latency data: {latency_data}")
print(f"Calculated Average Latency: {result} ms") 
# Expected Output: Calculated Average Latency: 30.0 ms
```

### 💡 Key Takeaway

For complex data processing or calculations, defining a function that accepts the data as a **parameter** is non-negotiable. This ensures the function is **generic** and can handle any input dataset, making it a valuable tool in your scripting library. The use of **`sum()`** and **`len()`** makes the calculation efficient and readable.

