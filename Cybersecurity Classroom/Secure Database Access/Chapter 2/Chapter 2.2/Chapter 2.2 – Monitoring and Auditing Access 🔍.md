🌟 **Aisha’s Mysterious Deletions** 
![[Aisha's Mysterious Deletions.png]]
Aisha discovered that the _admin_ user account was used to delete several critical customer records. She checked the network logs but found nothing. Without detailed database logs, she couldn't determine which user or application initiated the deletion, nor could she prove the sequence of events.

Elena: “That’s a failure of **[[Non-Repudiation]]** due to poor database **[[Security Logging]]**. For compliance and forensics, you must enforce detailed **Database Auditing** that logs every significant action, including _who_ connected, _when_, and _what_ specific command they executed. You can't secure what you don't monitor.”

### 🧠 **Database Auditing: The Mandatory Log**

**Database Auditing** is the process of recording specific activities performed by users, applications, and administrators within the database engine itself. This provides the most granular level of tracking.

- **Goal:** To achieve **[[Non-Repudiation]]** (proving who did what) and meet compliance requirements. It is a critical component of forensic investigation.
    
- **Mandatory Logs:** Auditing must capture:
    
    - **Successful/Failed Connections:** _Who_ logged in and _when_.
        
    - **Schema Changes:** Any attempt to modify tables or procedures (violating **[[Integrity]]**).
        
    - **Data Manipulation Language (DML):** Every `INSERT`, `UPDATE`, and `DELETE` command executed.
        
    - **Sensitive Data Access:** Detailed logging for queries that touch tables containing **[[Personally Identifiable Information (PII)]]**.
        

### 💡 **Protecting the Audit Trail**

An audit system is useless if the attacker can modify or delete the logs to cover their tracks. Protecting the audit trail is a core security mandate.

- **Log Location:** Audit logs must be immediately and securely transmitted from the database server to a separate, tamper-proof **[[Security Logging]]** system (e.g., a **SIEM** – Security Information and Event Management) that resides on a different machine.
    
- **Access Control:** Access to the audit log system must be strictly limited via **[[Principle of Least Privilege]]**. Crucially, the account used by the application and the standard DBA account **must not** have permission to delete or modify the audit logs. This reinforces the **[[Separation of Duties]]** administrative control.
    

### 🎯 **Monitoring for Suspicious Behavior**
![[Monitoring for Suspicious Behavior.png]]

Simply collecting logs is not enough; the logs must be monitored for anomalies that indicate a breach or misuse of privileges:

- **Time/Frequency Anomalies:** An account performing administrative actions at 3 AM, or a sharp, sudden increase in the number of **read** operations (which could indicate a large-scale data exfiltration attempt).
    
- **Location Anomalies:** A login from an unexpected geographic location.
    
- **Failed Access:** A sudden increase in failed login attempts, which may indicate a brute-force or dictionary attack attempt against the database credentials.
    

---

### 🧩 **Mini Quiz – Chapter 2.2**

**Q:** What is the primary administrative and technical goal of immediately forwarding database audit logs to a separate, tamper-proof **[[Security Logging]]** system?

A) To enforce the use of **[[Parameterization]]** against **[[SQL Injection]]**.

B) To enable **[[Data Masking]]** for development environments.

C) **To prevent a compromised database administrator or attacker from destroying or modifying the logs to hide their actions, thereby ensuring [[Non-Repudiation]].** 

D) To facilitate the **[[Data Encryption]]** process for TDE.

Click here to view the answer : [[Chapter 2.2 - Answer - Secure Database Access]]

---

### 🎯 **Learning Objectives – Chapter 2.2**

By the end of this sub-chapter, you should be able to:

- Explain the role of **Database Auditing** in achieving **[[Non-Repudiation]]**.
    
- Justify the mandatory requirement of forwarding audit logs to a separate, secured **[[Security Logging]]** system.
    
- Identify examples of suspicious database behavior that require monitoring and alerts.