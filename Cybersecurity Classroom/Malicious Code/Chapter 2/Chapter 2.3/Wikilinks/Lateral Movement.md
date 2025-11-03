### 🧠 **Definition and Process ➡️**

**Lateral Movement** is the process by which an attacker, having compromised an initial system, moves deeper into a network by compromising and accessing other hosts and services.

- **Goal:** To pivot from the initial, low-value foothold to reach the final, high-value target (e.g., a centralized database or domain controller).
    
- **Mechanism:** This is often achieved by stealing credentials (e.g., via a **[[Keylogger]]** or memory dump) from the compromised host and using those credentials to authenticate to adjacent machines.
    
- **Defense:** Strong network segmentation (internal firewalls) and an identity system that restricts the credentials from one system to be valid on others, even within the trusted network zone (Zero Trust model).