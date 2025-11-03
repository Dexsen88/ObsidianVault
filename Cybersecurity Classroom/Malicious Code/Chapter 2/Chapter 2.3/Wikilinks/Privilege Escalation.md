### 🧠 **Definition and Mechanism 👑**

**Privilege Escalation** is a post-exploitation technique where an attacker, having gained a low-level foothold on a system, exploits a local **[[Vulnerability]]** or misconfiguration to gain a higher level of **[[Authorization]]** (e.g., from user to administrator/root).

- **Goal:** To defeat the **[[Principle of Least Privilege]]** and gain the necessary permissions to read sensitive files, install a **[[Rootkit]]**, or prepare for **[[Lateral Movement]]**.
    
- **Types:** **Vertical** (gaining higher privileges on the same user account) or **Horizontal** (gaining the same privileges as a different user).
    
- **Defense:** Enforcing **hardening** (secure configuration), timely **Vulnerability Management**, and running all services with the absolute minimum required privileges.