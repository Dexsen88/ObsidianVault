### 🧠 **Definition and Security Context 🧱**

**Stored Procedures** are pre-compiled SQL routines or functions stored within the database itself. Applications call these procedures by name instead of building and sending raw SQL commands.

- **Security Benefit:** They help enforce the **[[Principle of Least Privilege]]** by limiting the application's ability to execute arbitrary commands (like DROP TABLE) and can provide a fixed, audited interface for data access.
    
- **Security Caveat:** They are **not** inherently protected against **[[SQL Injection]]**. If the stored procedure's internal logic uses unsafe string concatenation, **[[Parameterization]]** is still mandatory inside the procedure.
    
- **Use Case:** Often used to enforce complex business rules and centralize data access logic, making security controls easier to apply consistently.