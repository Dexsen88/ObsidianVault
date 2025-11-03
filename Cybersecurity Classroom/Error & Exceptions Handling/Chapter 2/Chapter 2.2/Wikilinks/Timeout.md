### 🧠 **Definition and Mechanism ⏱️**

A **Timeout** is a security and reliability control that specifies the maximum amount of time a system component is allowed to wait for a particular operation (e.g., establishing a connection, executing a query, or receiving a network response) before it forcefully terminates the operation.

- **Goal:** To prevent resource exhaustion and **[[Denial of Service (DoS)]]** attacks by ensuring that no single request can lock up or hang the application indefinitely. This protects the overall system **[[Availability]]**.
    
- **Mandate:** Must be implemented on all external I/O operations (database calls, external API requests, file system operations) and any internal resource-intensive processes.
    
- **Security Principle:** Enforcing a **[[Timeout]]** is a proactive measure that complements **[[Rate Limiting]]** by addressing resource consumption over time, rather than just request volume.