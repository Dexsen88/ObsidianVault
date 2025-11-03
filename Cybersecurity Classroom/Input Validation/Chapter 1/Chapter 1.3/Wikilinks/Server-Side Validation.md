### 🧠 **Definition and Role 🛡️**

**Server-Side Validation** is the process of rigorously validating all input on the application's backend server **before** it is processed, stored, or used in any sensitive operation (like a database query).

- **Primary Purpose:** **Security**. This is the mandatory, un-bypassable security gate that ensures input conforms to both **Syntactic** and **Semantic** rules.
    
- **Trust Boundary:** This validation must occur immediately after the data crosses the trust boundary (the moment the server receives the request).
    
- **Compliance:** It is the only reliable way to enforce the **[[Never Trust User Input]]** principle and effectively prevent critical vulnerabilities like **[[SQL Injection]]** and **[[XSS]]**.
    
- **Procedure:** If the server's check fails, the application must immediately **[[Log the Failure]]** and reject the request, as this preserves the **[[Integrity]]** of the system.