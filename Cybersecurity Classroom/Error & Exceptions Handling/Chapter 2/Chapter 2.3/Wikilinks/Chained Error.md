### 🧠 **Definition and Risk ⛓️**

A **Chained Error** occurs when one software component (Service A) calls a second component (Service B), and Service B fails, causing Service A to fail and wrap the original failure details from B into its own exception message.

- **Vulnerability:** If Service A does not perform **Error Cleansing**, it can inadvertently propagate a **[[Verbose Error Message]]** (including internal system details like IP addresses, stack traces, or configuration strings) from the downstream service across a **[[Trust Boundary]]**.
    
- **Impact:** High risk of **[[Information Leakage]]** and compromise of **[[Confidentiality]]** in complex, distributed architectures (microservices).
    
- **Defense:** Service A must catch, sanitize, and log the upstream error, then re-throw a **[[Custom Exceptions]]** object with only safe, local information (like a Correlation ID).