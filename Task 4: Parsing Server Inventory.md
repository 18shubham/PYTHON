Project Title: Inventory and Health Checker 🏥
🎯 Goal
The objective of this task was to master processing nested data structures (specifically, a List of Dictionaries). This structure is the exact format used when reading inventory or detailed status data from Cloud APIs (e.g., listing AWS EC2 instances or Kubernetes pods).

The task required combining iteration with nested conditional logic to process multiple resource records efficiently.

⚙️ Core Concepts Covered
List of Dictionaries: Handling complex data where multiple records (servers) are stored in a list, and each record is a dictionary containing attributes (name, IP, status).

Nested Access: Retrieving values from a dictionary (server['name']) that is currently being iterated over by a for loop.

Nested Control Flow: Using an if statement inside a for loop to execute conditional actions (like alerting) on a per-item basis.

📝 The Task
Given a list named server_inventory, iterate through the list, print the name and status of each server, and print an alert for any server whose status is exactly "DOWN".

💾 Initial Data
Python

server_inventory = [
    {"name": "auth-api", "ip": "10.0.1.10", "status": "UP"},
    {"name": "db-master", "ip": "10.0.1.20", "status": "DOWN"},
    {"name": "front-end", "ip": "10.0.1.30", "status": "UP"}
]
✅ Solution Code
Python

server_inventory = [
    {"name": "auth-api", "ip": "10.0.1.10", "status": "UP"},
    {"name": "db-master", "ip": "10.0.1.20", "status": "DOWN"},
    {"name": "front-end", "ip": "10.0.1.30", "status": "UP"}
]

for server in server_inventory:
    # 1. Nested Access & Formatting
    print(f"Server: {server['name']} | Status: {server['status']}")

    # 2. Conditional Check: Correctly indented logic block
    if server['status'] == "DOWN":
        print("    --> ACTION REQUIRED! This server is down.") 
💡 Key Takeaway
When working with APIs and infrastructure data, the key to success is correctly handling the nested structure. The for loop peels off the outer layer (the list), and the square bracket notation ([]) accesses the inner layer (the dictionary keys). Ensure your if condition and action are correctly indented within the for loop!
