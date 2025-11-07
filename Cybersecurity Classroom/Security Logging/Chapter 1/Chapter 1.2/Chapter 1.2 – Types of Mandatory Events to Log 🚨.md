🌟 **Aisha’s Missing Evidence** 
![[Aisha's Missing Evidence.png]]

Aisha’s application had a **[[Rate Limiting]]** policy on the login page. An attacker launched a dictionary attack. The **SIEM** didn't receive any logs until the server's CPU utilization spiked. By then, the attack was over, and the original login attempts were lost, preventing analysis of the brute-force pattern.

Elena: “You failed to log events that are early indicators of an attack. **[[Security Logging]]** must capture activity across all layers, especially **access control** and **exceptions**, which are the first signs of attack or system failure. You must log for both success and failure.”

### 🧠 **Access Control and Authentication (Critical)**

These are the most critical events to log, as they directly involve the **[[Authentication]]** and **[[Authorization]]** processes. Failure to log these means an attacker can move laterally or gain unauthorized access without detection.

- **Mandatory Log Points:**
    
    - **Successful Login:** (Who, When, Where).
        
    - **Failed Login/Brute-Force:** Crucial for detecting attacks like brute-force or dictionary attacks.
        
    - **Account Lockout/Unlock:** Indicates a security mechanism has been triggered.
        
    - **Permission Denied:** Any attempt to perform an action without **[[Authorization]]** (e.g., a **[[BOLA]]** attempt).
        
    - **Credential Changes:** Password resets, API key generation, or multi-factor authentication enrollment changes.
        

### 💡 **Input and Data Events (Integrity)**

Logging events related to user input and data manipulation is essential for maintaining **[[Integrity]]** and detecting injection flaws.

- **Input Validation Failures:** Logs of input that violate expected formats (e.g., an unusually long string in a username field) can indicate an attacker is probing for flaws like **[[SQL Injection]]** or **[[Buffer Overflow]]**.
    
- **Sensitive Data Manipulation:** All successful `INSERT`, `UPDATE`, or `DELETE` operations on sensitive data (e.g., financial records, **[[Personally Identifiable Information (PII)]]**) must be logged at the database layer (**Database Auditing**).
    
- **System Commands:** Any attempt to execute system commands (via an API or application function) must be logged, as this can indicate a **[[Command Injection]]** attack.
    

### 🎯 **System and Exception Events (Availability)**
![[System and Exception Events.png]]

Logging system errors and resource limitations is key to maintaining **[[Availability]]** and detecting **[[Denial of Service (DoS)]]** attacks.

- **Application Errors (Exceptions):** All application-level exceptions (HTTP 500 status codes, unhandled exceptions) must be logged. Crucially, these logs **must not** contain **[[Verbose Error Message]]**s that expose internal details to the user.
    
- **Security Control Triggers:** Any time a security mechanism intervenes: **[[Rate Limiting]]** activation, WAF (Web Application Firewall) blocking, or **[[Session Token]]** invalidation.
    
- **Resource Exhaustion:** Logs showing high CPU, memory, or disk usage, which are early signs of a **[[Denial of Service (DoS)]]** or resource misuse.
    

---

### 🧩 **Mini Quiz – Chapter 1.2**

**Q:** When an application receives a malformed request that attempts to perform an unauthorized action (e.g., accessing another user's file ID), what two pieces of information are mandatory to log for forensic analysis?

A) **[[Data Masking]]** of the log entry and **[[Data Encryption]]** status.

B) **The unique User ID (Who) from the verified session and the status of "Permission Denied" (What) for [[Non-Repudiation]] and [[BOLA]] detection.** 

C) The **[[Cryptographic Hash]]** of the entire log file and the current **[[Principle of Least Privilege]]** status.

D) The IP address of the attacker and the **[[Parameterization]]** status of the input.

Click here to view the answer : [[Chapter 1.2 - Answer - Security Logging]]

---

### 🎯 **Learning Objectives – Chapter 1.2**

By the end of this sub-chapter, you should be able to:

- Identify the mandatory log points for the **Authentication** and **Authorization** processes.
    
- Justify the need to log **input validation failures** and **sensitive data manipulation** events.
    
- List key system events that indicate security control activation or resource issues.