🌟 **Aisha’s Infinite Loop**
![[Aisha's Infinite Loop.png]]
Aisha wrote a simple loop that processed items from a queue. However, due to a bug, the queue never emptied. The process ran indefinitely, consuming all available system memory until the entire server crashed, taking down unrelated applications.

Elena: "That crash was a direct result of improper **Resource Management** and a missing **Timeout** control. Any function that uses shared resources—memory, CPU, database connections, or file handles—must be bounded. Allowing a process to run indefinitely is a critical **[[Availability]]** vulnerability."

### 🧠 **Resource Allocation and Exhaustion**

**Resource Allocation** refers to the consumption of shared system assets. Secure resource management is a core principle for preventing **[[Denial of Service (DoS)]]** attacks.

- **Vulnerability:** Allowing user input to dictate the scale of a resource-intensive operation. For example, letting a user specify an unbounded file size for upload, an infinite number of database records to return, or a very complex regular expression (leading to a **ReDoS** attack).
    
- **Defense:** Mandatory limits on all inputs, such as maximum file size, maximum number of loop iterations, and mandatory **Timeouts** on all I/O operations.
    

### 💡 **Timeouts: Enforcing Bounded Operations**

A **[[Timeout]]** is a security control that sets a maximum duration for an operation (e.g., a database query, a network connection, or a file read) before the system automatically terminates it.

- **Goal:** To ensure that a single slow, hung, or malicious request cannot monopolize system resources indefinitely, thus maintaining the **[[Availability]]** of the service for other users.
    
- **Types:**
    
    - **Connection Timeout:** Maximum time allowed to establish a network connection.
        
    - **Read/Write Timeout (Socket Timeout):** Maximum time allowed for data transfer after a connection is established.
        
    - **Query Timeout:** Maximum time a database is allowed to spend processing a single query.
        
- **Security Principle:** **[[Timeout]]** is a practical implementation of the **[[Fail-Safe Defaults]]** principle, as they ensure the system recovers from a hung state without crashing.
    

### 🎯 **Memory Leak Management**
![[Memory Leak management.png]]

An application that continuously allocates memory without properly releasing it suffers from a **Memory Leak**. While not always an immediate security breach, prolonged memory leaks lead to resource exhaustion and eventual **[[Denial of Service (DoS)]]**. Secure coding practices, including explicit resource cleanup using `finally` blocks in error handling, are mandatory for preventing this.

---

### 🧩 **Mini Quiz – Chapter 2.2**

**Q:** Why is a **[[Timeout]]** control mandatory for all external database queries in a secure application?

A) To enforce **[[Parameterization]]** and prevent **[[SQL Injection]]**.

B) **To prevent a hung or excessively slow query from monopolizing the database connection and other system resources indefinitely, thus protecting [[Availability]].** 

C) To ensure the **[[Cryptographic Hash]]** of the returned data is calculated correctly.

D) To implement **[[Contextual Output Encoding]]** on the query results.

Click here to view the answer : [[Chapter 2.2 - Answer - Error & Exceptions Handling]]

---

### 🎯 **Learning Objectives – Chapter 2.2**

By the end of this sub-chapter, you should be able to:

- Explain the security risk of **unbounded resource allocation**.
    
- Define a **[[Timeout]]** and justify its use as a mandatory control.
    
- Identify different types of necessary **[[Timeouts]]** (connection, query, read/write).