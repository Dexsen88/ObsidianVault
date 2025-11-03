### 🧠 **Definition and Mechanism**

**SQL Injection (SQLi)** is a code injection vulnerability where an attacker manipulates the SQL queries an application sends to its database. It occurs when **unvalidated user input** is directly concatenated into an SQL Query statement. The attacker submits SQL code fragments (e.g., `' OR 1=1; --`) via an application field, causing the database to execute unintended commands.

### 🚨 **Impact and Mitigation**

SQLi is one of the most critical vulnerabilities, as it can grant the attacker full access to the database.

- **Impact:** Violates **[[Confidentiality]]** (data theft), **[[Integrity]]** (data tampering/deletion), and **Availability** (system denial of service).
    
- **Mitigation:** The primary defense is using Parameterized Queries(or Prepared Statements), which treat user input as data only, never as executable code.