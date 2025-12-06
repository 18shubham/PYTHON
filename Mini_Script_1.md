server_config = {
    "hostname": "web-01",
    "ip_address": "192.168.1.10",
    "max_connections": 500,
    "status": "running"
}

Your Task:
Access: Write a single line of code to print the ip_address from the server_config dictionary.

Update: Write a single line of code to change the value of the status key from "running" to "maintenance".

Error Simulation (KeyError): Write a line of code that tries to print the value of a non-existent key, like uptime, to see what happens.

Solution:

server_config = {
    "hostname": "web-01",
    "ip_address": "192.168.1.10",
    "max_connections": 500,
    "status": "running"
}

# 1. Access: Print the ip_address
print(server_config["ip_address"])

# 2. Update: Change the status to "maintenance"
server_config["status"] = "maintenance"
print(server_config) # To show the updated status

# 3. Error Simulation (KeyError): Trying to print a non-existent key
print(server_config["uptime"])

Identifying Errors/Bugs
In the third line of the solution (print(server_config["uptime"])), Python will generate a KeyError.

Type of Error: KeyError

Explanation: A KeyError occurs when you try to access a dictionary element using a key that doesn't exist within that dictionary. Dictionaries require exact matches for their keys. This is a very common error when working with configuration files or API responses, and handling it gracefully is a crucial DevOps skill.

💡 Explain the Concept
This task tested your ability to work with Dictionaries.

Dictionaries are Python's primary structure for handling configuration data because they store information as key-value pairs (like a real-world dictionary or JSON object).

Access/Update: Values are accessed or updated using square brackets ([]) with the key name inside (e.g., dictionary_name["key"]).

Mutability: Dictionaries are mutable, meaning you can change, add, or remove key-value pairs after they are created, which is essential for managing dynamic server configurations.
