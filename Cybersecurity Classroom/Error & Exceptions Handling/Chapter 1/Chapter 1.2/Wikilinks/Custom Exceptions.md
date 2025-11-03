### 🧠 **Definition and Purpose 🛑**

**Custom Exceptions** are software error classes that are defined by the application developer to specifically represent and categorize expected or security-relevant fault conditions within the application's logic.

- **Goal:** To allow developers to write targeted code to handle specific faults (e.g., throwing a `DatabaseUnavailableException` instead of a generic `IOException`).
    
- **Security Benefit:** They are essential for enforcing security controls. For instance, a dedicated `AuthenticationFailureException` allows the system to trigger a **rate-limiting** defense and log the event with high priority, without needing to parse the message text of a generic exception.