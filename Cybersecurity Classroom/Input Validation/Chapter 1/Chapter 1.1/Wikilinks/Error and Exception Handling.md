### 🧠 **The Distinction 🚧**

This concept addresses the difference between severe, unrecoverable system failures and manageable, recoverable runtime issues.

1. **Errors (Fatal):**
    
    - **Definition:** Severe problems, often related to the runtime environment or resource exhaustion (e.g., `OutOfMemoryError`, `StackOverflowError`).
        
    - **Recoverability:** Generally **unrecoverable**. The best practice is to shut down the service cleanly and log the incident to prevent **[[Information Leakage]]**.
        
2. **Exceptions (Recoverable):**
    
    - **Definition:** Predictable, abnormal events that interrupt the normal flow of a program (e.g., `FileNotFoundException`, `ZeroDivisionError`).
        
    - **Recoverability:** **Manageable**. They can and should be handled using a `try-catch/except` block to allow the program to gracefully recover or degrade functionality.
        

- **Security Relevance:** Proper **[[Error and Exception Handling]]** is vital for **Availability** and preventing security issues caused by unhandled crashes.