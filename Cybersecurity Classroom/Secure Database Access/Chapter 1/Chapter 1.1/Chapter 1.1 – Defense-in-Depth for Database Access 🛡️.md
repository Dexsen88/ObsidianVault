**🌟 Aisha’s Compromised Credentials**
![[Aisha's Compromised Credentials.png]]

Aisha's web server was breached due to an unpatched [[Vulnerability]]. The attacker found the database connection string and used those credentials to log into the database directly, bypassing all application-level controls and stealing the entire customer list.

Elena: "That breach occurred because you relied on a single point of failure: the application layer. Your database needed **Defense-in-Depth**. Credentials found on the web server shouldn't grant full administrative access to the data. Database security requires layering controls at the network, host, user, and data levels."

### 🧠 **Defense-in-Depth for Databases**

**[[Defense-in-Depth]]** is the mandatory strategy of having multiple, independent layers of security controls so that if one fails (like the web server's security), others are still in place to protect the core asset (the data).

|**Layer**|**Control**|**Security Goal**|
|---|---|---|
|**Network (Perimeter)**|**Firewalls** and **Network Segmentation**|Restrict _who_ can connect to the database server's port.|
|**Host (OS)**|**OS Hardening** and Patching|Protect the database server itself from **[[Malware]]** and **Exploit**s.|
|**Database (User/Role)**|**[[Principle of Least Privilege]]**|Restrict _what_ the application/user can do once connected.|
|**Data (Inside DB)**|**[[Data Encryption]]** and **[[Data Masking]]**|Protect the data even if the attacker gains access.|

### 💡 **Mandatory Principles: Least Privilege and Separation**

Two security principles are non-negotiable for database access:

1. **[[Principle of Least Privilege]] (for the Application):** The database account used by the web application **must only** have the minimum permissions required for its function. If the application only needs to read and write customer data, it must **not** have permissions to drop tables, modify schemas, or access administrative audit logs. This minimizes the damage if the web server is compromised.
    
2. **Separation of Duties (for Personnel):** The personnel responsible for managing the database infrastructure (DBAs) must be distinct from the personnel managing the security and auditing of the data. The person who manages the data **[[Integrity]]** should not be the same person who reviews the access **[[Security Logging]]**.
    

### 🎯 **Connection Strings and Key Management**
![[Connection Strings and Key Management.png]]

Database connection strings contain critical **[[Authentication]]** secrets. They must **never** be stored directly in source code or configuration files that are checked into version control.

- **Mandate:** Connection strings must be stored in a secured **[[Key Management System (KMS)]]** or a dedicated secret store. The application retrieves the secret at runtime using a highly privileged, tightly controlled service account, minimizing the risk of **[[Information Leakage]]** if the server is breached.
    

---

### 🧩 **Mini Quiz – Chapter 1.1**

**Q:** An application's database account has full administrator rights (DROP, ALTER, CREATE). Which principle does this configuration violate, and what is the primary security consequence if the web server is compromised?

A) Principle Violated: **[[Separation of Duties]]**; Consequence: **[[Denial of Service (DoS)]]** on the web server.

B) **Principle Violated: [[Principle of Least Privilege]]; Consequence: The attacker can use the stolen credentials to modify or destroy the entire database (Integrity/Availability breach).** 

C) Principle Violated: **[[Contextual Output Encoding]]**; Consequence: **[[Cross-Site Scripting (XSS)]]**.

D) Principle Violated: **[[Data Protection]]**; Consequence: **[[Verbose Error Message]]**.

Click here to view the answer : [[Chapter 1.1 - Answer - Secure Database Access]]

---

### 🎯 **Learning Objectives – Chapter 1.1**

By the end of this sub-chapter, you should be able to:

- Explain the concept of **[[Defense-in-Depth]]** as applied to database security.
    
- Justify the mandatory application of the **[[Principle of Least Privilege]]** to database service accounts.
    
- Understand why sensitive connection strings must be stored in a **[[Key Management System (KMS)]]**.