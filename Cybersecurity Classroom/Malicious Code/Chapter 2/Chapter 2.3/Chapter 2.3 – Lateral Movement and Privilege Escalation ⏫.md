🌟 **Aisha’s Domain Compromise**
![[Aisha's Domain Compromise.png]]
The **[[Worm]]** that infected Aisha's unpatched server (Chapter 2.2) couldn't access sensitive customer data because the web server ran with low privileges (**[[Principle of Least Privilege]]**). However, the **[[Malware]]** spent the next 48 hours collecting cached credentials and exploiting a local configuration flaw to gain administrative access, allowing it to jump to the finance server.

Elena: "That two-step attack is **Privilege Escalation** followed by **Lateral Movement**. It's the standard post-exploitation playbook. If **[[Malware]]** can't immediately get what it wants, it attempts to gain a higher privilege level on the current machine and then uses those new credentials to move to a more valuable target across the network."

### 🧠 **Privilege Escalation**

**[[Privilege Escalation]]** is the act of exploiting a **[[Vulnerability]]** (e.g., a buggy system driver or a misconfigured service) on a compromised machine to gain a higher level of **[[Authorization]]** (e.g., moving from a standard user account to a system administrator/root account).

- **Goal:** To bypass the **[[Principle of Least Privilege]]** and gain full control over the host machine, enabling the **[[Malware]]** (or attacker) to install a persistent **[[Rootkit]]** or read highly sensitive local files.
    
- **Defense:** Mandatory use of application whitelisting and **hardening** (secure configuration) of the operating system to prevent the execution of unauthorized or vulnerable code.
    

### 💡 **Lateral Movement**

**[[Lateral Movement]]** is the technique used by attackers to move deeper into a network from an initial foothold machine, usually by compromising accounts and leveraging stolen credentials (often captured by a **[[Keylogger]]**).

- **Goal:** To reach the "Crown Jewels"—the most valuable assets (e.g., a database of customer **[[Personally Identifiable Information (PII)]]** or a corporate domain controller) that are isolated from the initial access point.
    
- **Mechanism:** Typically involves credential hopping, where a credential stolen from Machine A is used to authenticate to Machine B, and so on.
    

### 🎯 **Defense Against Post-Exploitation**
![[Defense Againts Post-Exploitation.png]]

The only defense against **Lateral Movement** and **Privilege Escalation** is strict network segmentation and identity management:

1. **Network Segmentation:** Use internal firewalls to restrict the servers a compromised host can talk to.
    
2. **Zero Trust:** Never trust any device inside the network. Implement multi-factor **[[Authentication]]** and re-authenticate every time a service is accessed, even internally.
    
3. **[[Principle of Least Privilege]]**: Ensure that if one server (like the web server) is compromised, its credentials are not valid on any other server (like the finance server).
    

---

### 🧩 **Mini Quiz – Chapter 2.3**

**Q:** An attacker successfully breaches a public-facing web server that runs with low privileges. They then steal an administrative token from the server's memory and use it to log into an internal financial database. What are the two attack stages that occurred here, in order?

A) **[[SQL Injection]]** followed by **[[Contextual Output Encoding]]**.

B) **[[Privilege Escalation]]** (on the web server) followed by **[[Lateral Movement]]** (to the database). 

C) **[[Denial of Service (DoS)]]** followed by **[[Command Injection]]**.

D) **[[Phishing]]** followed by **[[Vulnerability Management]]**.

Click here to view the answer : [[Chapter 2.3 - Answer - Malicious Code]]

---

### 🎯 **Learning Objectives – Chapter 2.3**

By the end of this sub-chapter, you should be able to:

- Define **[[Privilege Escalation]]** and explain how it bypasses the **[[Principle of Least Privilege]]**.
    
- Define **[[Lateral Movement]]** and explain why it is necessary to reach high-value assets.
    
- Understand that **[[Malware]]** uses both techniques to achieve its ultimate objective.