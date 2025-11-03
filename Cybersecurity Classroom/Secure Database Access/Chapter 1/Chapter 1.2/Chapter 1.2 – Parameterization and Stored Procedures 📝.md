🌟 **Aisha’s Query Failure** 

Aisha used string concatenation to build a database query based on user input for a search feature. An attacker noticed the input field and typed `' OR '1'='1`. The resulting query was executed, causing the application to return all customer records, not just the one requested.

Elena: “That was a classic **[[SQL Injection]]** attack, the number one database security flaw. Your application violated the **[[Never Trust User Input]]** principle. The single, mandatory, non-negotiable code-level defense against this is **[[Parameterization]]**.”

### 🧠 **SQL Injection and Parameterization**

**[[SQL Injection]]** is a critical **[[Integrity]]** and **[[Confidentiality]]** flaw where an attacker injects malicious SQL commands into an application's input fields (e.g., login, search).

- **Vulnerability:** Occurs when user input is incorrectly treated as executable SQL code instead of inert data.
    
- **Mandatory Defense: [[Parameterization]]** (also known as Prepared Statements): This technique separates the SQL command logic from the user-supplied data. The database driver is told exactly which parts of the statement are code and which parts are variables, ensuring that user input is **always** treated as data and can never be executed as a command.
    

### 💡 **Stored Procedures**

**Stored Procedures** are a collection of pre-compiled SQL statements stored in the database. When securely implemented (and combined with **[[Parameterization]]**), they can offer a strong defense layer.

- **Security Benefit:** They provide a rigid interface for application-to-database interaction. The application can only call the procedure; it cannot submit arbitrary SQL commands. This enforces a tighter **[[Principle of Least Privilege]]** at the command level.
    
- **Limitation:** Stored procedures themselves are _not_ automatically immune to **[[SQL Injection]]**. If the procedure uses unsafe string concatenation internally, the vulnerability persists. **[[Parameterization]]** must be used within the stored procedure.
    

### 🎯 **Separation of Duties (Administrative Control)**

**[[Separation of Duties]]** is an administrative and procedural control that ensures no single individual has control over all critical aspects of a security process. In the context of database access, it is vital for **[[Integrity]]** and **[[Non-Repudiation]]**.

- **Goal:** To prevent fraud, malicious activity, or catastrophic error by requiring the collaboration of multiple people.
    
- **Database Example:**
    
    - The person who **configures the database security and user accounts** (Security Admin) should **not** be the person who **reviews the security audit logs and monitors access** (Security Auditor).
        
    - The developer who **writes the application code** should **not** be the one who **manages the production database server and credentials** (DBA).
        

---

### 🧩 **Mini Quiz – Chapter 1.2**

**Q:** Why is **[[Parameterization]]** the mandatory, non-negotiable defense against **[[SQL Injection]]** attacks?

A) It ensures the database connection uses the **[[TLS Protocol]]** for **[[Confidentiality]]**.

B) It forces the application to use a **[[Key Management System (KMS)]]** for credentials.

C) **It separates the SQL command logic from the user-supplied data, ensuring input is always treated as inert data and can never be executed as a command.** 

D) It automatically encrypts the data at rest using **[[Data Encryption]]**.

Click here to view the answer : [[Chapter 1.2 - Answer - Secure Database Access]]

---

### 🎯 **Learning Objectives – Chapter 1.2**

By the end of this sub-chapter, you should be able to:

- Explain why **[[Parameterization]]** is the mandatory defense against **[[SQL Injection]]**.
    
- Describe the security benefits and limitations of using **Stored Procedures**.
    
- Define **[[Separation of Duties]]** and provide a database-related example.