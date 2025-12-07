Task 8: Server Provisioning Function with Defaults**.

-----

## 📄 README.md for Task 8: Server Provisioning Function with Defaults

### Project Title: Hostname Generator (`generate_hostname`) 🖥️

### 🎯 Goal

The objective of this task was to master **Default Arguments** in functions. This concept is fundamental in **DevOps** because configuration parameters often have a standard, common value (e.g., the default environment is "dev" or the default region is "us-east-1"). Using defaults makes function calls cleaner and faster, as only required or non-default parameters need to be explicitly passed.

### ⚙️ Core Concepts Covered

1.  **Default Arguments:** Defining a parameter with an equals sign (`=`) and a value directly in the function signature. This makes the parameter optional for the caller.
2.  **Required Arguments:** Parameters without a default value must always be provided when the function is called.
3.  **Function Flexibility:** Demonstrating how the same function can be called in two ways (with and without the optional argument) to manage different environments.
4.  **String Formatting (f-strings):** Constructing the final standardized output string using variables.

### 📝 The Task

Create a function named `generate_hostname` that requires a `service_name` but defaults the `environment` to `"dev"`. The function must return the hostname in the format `[service_name]-[environment]-01`.

### ✅ Solution Code

```python
# 1. Define Function with Default Argument
# environment is optional and defaults to "dev" if not provided.
def generate_hostname(service_name, environment="dev"): 
    
    # 2. String Formatting using f-strings
    return f"{service_name}-{environment}-01"

# 3. Test 1 (Using Default)
# Only passing 'auth', 'environment' uses the default "dev"
hostname_dev = generate_hostname("auth")
print(f"Default Hostname: {hostname_dev}")

# 4. Test 2 (Overriding Default)
# Explicitly passing "prod" overrides the default "dev"
hostname_prod = generate_hostname("db", "prod")
print(f"Production Hostname: {hostname_prod}")
```

### 💡 Key Takeaway

Default arguments simplify function calls and improve code readability. When defining functions, always place **required arguments** first, followed by all **optional arguments** that have a default value. This is a strict Python rule that ensures consistency and clarity.

-----

