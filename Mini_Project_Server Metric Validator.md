🎯 Goal
The objective of this task was to practice conditional logic (if/else) and safe dictionary access (.get())—two fundamental skills required for writing robust scripts that handle dynamic system metrics and configuration files.

⚙️ Core Concepts Covered
Control Flow (if/else): Making decisions in the script based on a metric's value.

Safe Dictionary Access (.get()): Retrieving data from a dictionary while preventing a program crash (KeyError) if a key is missing.

📝 The Task
Given a dictionary of server metrics, the script had two requirements:
Check CPU Load: Alert the user if the cpu_percent is $\ge 90$.Check Latency (Safely): 
Retrieve the value of network_latency_ms. Since this key might be missing in some server configurations, the script must default the value to "N/A" instead of failing.

server_metrics = {
    "cpu_percent": 95,
    "memory_gb": 3.8,
    "disk_space_gb": 150
}

# 1. Conditional Check
if server_metrics["cpu_percent"] >= 90:
    print("ALERT: High CPU Usage!")
else:
    print("CPU Usage is nominal.")

# 2. Safe Access using .get()
# This will return "N/A" because 'network_latency_ms' is missing.
latency = server_metrics.get("network_latency_ms", "N/A")
print(f"Network Latency: {latency}")

Key Takeaway
For production-ready DevOps scripts, always assume data (especially configuration or API results) might be incomplete or malformed. Using methods like .get(key, default_value) is a critical step to ensure your script is fault-tolerant and stable.
