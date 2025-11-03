### 🧠 **Definition and Risk 🔓**

**Information Leakage** occurs when an application inadvertently discloses sensitive internal data to an unauthorized party, typically an attacker or a general user.

- **Mechanism:** This often happens when a severe system error, such as an unhandled **Exception** or **Error**, causes the application to display a verbose debug message or a **stack trace** directly on the user screen.
    
- **Leaked Data Examples:** The output might expose:
    
    - Full file paths on the server.
        
    - Database connection strings (usernames and passwords).
        
    - Internal server names, versions, and software architecture details.
        
    - Proprietary business logic.
        
- **Impact:** Attackers use this leaked information (known as **Reconnaissance** or "footprinting") to discover further vulnerabilities and plan more targeted, devastating attacks like **[[SQL Injection]]** or **Path Traversal**.
    

### ✅ **Mitigation**

The primary defense is to use **[[Error and Exception Handling]]** to suppress technical details and display only generic, user-friendly error messages (e.g., "An unexpected error occurred. Please try again later.") while ensuring the full technical details are captured by the **Security Logging** system.