### 🧠 **Definition and Application 🔑**

The **Principle of Least Privilege (PoLP)** is a foundational security concept that dictates that every user, program, and process should have only the minimum access rights or permissions necessary to perform its specific task—and nothing more.

- **Goal:** To minimize the potential damage an attacker can inflict if they manage to compromise a user account or exploit a vulnerability in a service. This is a core component of **[[Defense in Depth]]**.
    
- **Application to Code:** If an application's database user only has `SELECT` permissions on certain tables (and no `DELETE` or `DROP TABLE` permissions), an attacker who manages to achieve a limited **[[SQL Injection]]** can only read data, not destroy the database.
    
- **Application to Validation:** For file I/O operations (relevant to **[[Path Traversal]]**), the application service should only have permissions to access the specific directory it needs, preventing lateral movement within the server's file system.