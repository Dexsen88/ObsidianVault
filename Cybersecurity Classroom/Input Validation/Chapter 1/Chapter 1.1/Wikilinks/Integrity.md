### 🧠 **Definition and Context**

**Integrity** is one of the three foundational principles of the **[[CIA Triad]]** (Confidentiality, Integrity, and Availability) in information security.

- **Definition:** Ensuring that data is accurate, consistent, and trustworthy over its entire lifecycle. Data must not be changed, destroyed, or corrupted in an unauthorized manner.
    

### 🚨 **Relevance to Input Validation**

**[[Input Validation]]** is the first step in protecting data integrity.

- **Failure:** If validation is absent, an attacker can intentionally input malformed data to crash the application, poison a database, or elevate their privileges, directly violating data integrity.
    
- **Success:** Effective validation ensures the system only processes data that adheres to both syntactic and semantic rules, maintaining the consistency and reliability of the application's state.