### 🧠 **Definition and Risk 💬**

A **Verbose Error Message** is a detailed system error that contains technical information useful for debugging but dangerous for security, such as stack traces, database strings, or internal file paths.

- **Vulnerability:** It is a primary source of **[[Information Leakage]]**, providing an attacker with free reconnaissance on the application's technology stack and architecture.
    
- **Defense:** All application errors, especially uncaught exceptions, must be intercepted by a global handler and translated into generic, user-friendly messages (e.g., HTTP 500 error page) before being returned to the client.