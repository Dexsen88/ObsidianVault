🌟 **Aisha’s Unrestricted Access** 
![[Aisha's Unrestricted Access.png]]
Aisha enforced **[[Principle of Least Privilege]]** on her application's database account, but she forgot to restrict the network access. An attacker, after breaching a separate, low-security marketing server on the same network, was able to connect directly to the database server because the database port was open to _everyone_ internally.

Elena: "That's a failure of **Network Segmentation**. The database should be in its own restricted network zone, accessible only by the specific, authorized application servers. Furthermore, the database server itself must be **Hardened** to prevent attackers from using system defaults to gain a foothold."

### 🧠 **Network Segmentation and Firewalls**

**Network Segmentation** is a **[[Defense-in-Depth]]** strategy that separates a network into smaller, isolated sub-networks. This is the **network-level firewall** defense for the database.

- **Database Zone:** The database server should reside in a highly restricted network segment, often called a **database tier** or a **private subnet**.
    
- **Access Control Lists (ACLs):** The network firewall must enforce **ACLs** that explicitly **Allow-List** (whitelist) only the **IP addresses of the application servers** that need to connect to the database port (typically TCP 3306 for MySQL, 1433 for SQL Server, etc.). All other connections, even from other servers on the same local network, must be blocked.
    
- **Goal:** To prevent **[[Lateral Movement]]** by an attacker who has successfully compromised a less-secure server elsewhere in the network.
    

### 💡 **Database Hardening (Secure Configuration)**

**Database Hardening** is the mandatory process of securing the default installation configuration of the database server and its operating system (OS). Default installations are almost always insecure.

- **Removal of Defaults:** Mandatory step is to immediately **change or remove all default passwords** for all service and administrative accounts.
    
- **Unused Features:** **Disable or remove all unnecessary features, services, and ports.** For instance, if the database isn't used for email, disable the mail stored procedure. Fewer open doors mean fewer **[[Vulnerability]]**s.
    
- **Patching:** The database operating system and the database software itself must be part of the strict **[[Vulnerability Management]]** process, ensuring timely application of **Security Patch**es to prevent **Exploit**ation.
    

### 🎯 **Disabling Administrative Access**
![[Disabling Administrative Access.png]]

The most critical part of hardening is ensuring that the application logic **never** uses the database's super-user or root account.

- **Separate Accounts:** Maintain distinct accounts for different roles:
    
    - **Application Account:** Used by the web server; minimum privileges (`SELECT`, `INSERT`, `UPDATE`).
        
    - **DBA Account:** Used by administrators for maintenance; high privileges, but only via an audited management network.
        
    - **Backup Account:** Used only for data backups; only has read-only privileges.
        
- **Goal:** Enforce **[[Principle of Least Privilege]]** at the highest level to ensure that a credential breach does not lead to complete system compromise.
    

---

### 🧩 **Mini Quiz – Chapter 2.3**

**Q:** An attacker compromises a secondary internal server and attempts to connect to the production database server. What mandatory network security control should prevent this connection from being established?

A) **[[Data Masking]]** of the connection string.

B) **Network Segmentation and firewall ACLs that only allow connections from the specific, authorized application servers.** 

C) Implementing a **[[Cryptographic Hash]]** for the backup files.

D) Enforcing **[[Separation of Duties]]** between developers and DBAs.

Click here to view the answer : [[ Chapter 2.3 - Answer - Secure Database Access]]

---

### 🎯 **Learning Objectives – Chapter 2.3**

By the end of this sub-chapter, you should be able to:

- Explain how **Network Segmentation** and **ACLs** prevent **[[Lateral Movement]]** to the database.
    
- Define **Database Hardening** and list two mandatory steps (removing defaults, disabling unused features).
    
- Justify the use of separate, low-privilege accounts for the application and administrative tasks.