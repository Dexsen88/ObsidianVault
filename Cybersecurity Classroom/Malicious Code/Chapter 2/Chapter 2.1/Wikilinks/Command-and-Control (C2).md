### 🧠 **Definition and Function 🛰️**

A **Command-and-Control (C2)** channel is the hidden, encrypted communication path between an attacker's server and the **[[Malware]]** (often called a "bot" or "zombie") running on a compromised system.

- **Goal:** To establish a persistent, covert means for the attacker to communicate with and remotely control the infected machine.
    
- **Mechanism:** The **[[Malware]]** periodically "phones home" to the C2 server, receiving new instructions (e.g., execute a **[[Command Injection]]**, download an update to the **[[Rootkit]]**) and sending back stolen data (**[[Information Leakage]]**).
    
- **Defense:** Detection relies on network traffic monitoring (for unusual volumes or destinations) and security tools that identify known C2 server IP addresses and domain names.