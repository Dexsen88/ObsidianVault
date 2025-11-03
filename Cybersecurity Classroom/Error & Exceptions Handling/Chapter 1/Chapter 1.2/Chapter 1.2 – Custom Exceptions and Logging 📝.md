🌟 **Aisha’s Audit Trail**
![[Aisha's Audit Trail.png]]
Aisha enforced generic error messages but realized she was flying blind. She couldn't tell the difference between a user typing a wrong password and an attacker probing for an **[[SQL Injection]]** vulnerability, as both resulted in a generic "Authentication Failed" message.

Elena: “You need to centralize and categorize your internal errors. **Custom Exceptions** ensure you handle security-relevant faults differently from normal faults, and **Security Logging** provides the mandatory, tamper-proof record you need for auditing, monitoring, and forensic analysis.”

### 🧠 **Custom Exceptions (Categorizing Faults)**

**[[Custom Exceptions]]** are application-specific error classes designed to categorize and handle different types of faults. Instead of relying on generic system errors (like `System.Exception`), you create specific, meaningful security exceptions.

- **Goal:** To separate security-relevant errors (e.g., `InvalidCredentialsException`, `AuthorizationFailureException`) from operational errors (e.g., `FileNotFoundException`).
    
- **Security Benefit:** This allows the code to perform a specific, secure action for a security fault. For instance, an `InvalidCredentialsException` can trigger an immediate **rate-limiting** mechanism to block brute-force attempts.
    

### 💡 **Security Logging (Tamper-Proof Records)**

**[[Security Logging]]** is the mandatory process of recording all security-relevant events, errors, and access attempts in a central, highly protected log repository.

- **What to Log:** Events like **[[Authentication]]** failures, **[[Authorization]]** failures, **[[Session Hijacking]]** alerts, **[[Data Sanitization]]** failures, and system reconfigurations.
    
- **Log Details:** Logs must contain sufficient detail (timestamp, source IP, user ID, error code) to allow for forensic analysis, but **must never** contain sensitive data like passwords, **[[Private Key]]**s, or unmasked **[[Personally Identifiable Information (PII)]]**.
    
- **Log Protection:** Logs are critical evidence, so they must be stored with strong **[[Integrity]]** controls (e.g., appended only, read-only storage, protected by **[[Cryptographic Hash]]**ing) to prevent an attacker from erasing their tracks after a breach.
    

### 🎯 **The Error Handling Flow**
![[The Error Handling Flow.png]]

1. **Local Catch:** Use `try-catch` blocks to catch specific faults and throw a **[[Custom Exceptions]]** object.
    
2. **Centralized Logger:** The exception is routed to a central **[[Security Logging]]** system. The system records the full stack trace and internal details.
    
3. **User Output:** The error is transformed into a generic message and a safe HTTP status code (e.g., 401, 403, 500) before being returned to the client, preventing **[[Verbose Error Message]]** and **[[Information Leakage]]**.
    

---

### 🧩 **Mini Quiz – Chapter 1.2**

**Q:** Why are **[[Custom Exceptions]]** preferred over generic system exceptions in a secure application?

A) They enforce the **[[Data Minimization]]** principle on the log file size.

B) **They allow the application to programmatically distinguish security-relevant faults (like authorization failures) from operational faults, enabling specific, secure responses (like rate limiting).** 

C) They automatically implement **[[Contextual Output Encoding]]** for all error messages.

D) They prevent **[[Command Injection]]** by using **[[Parameterization]]**.

Click here to view the answer : [[Chapter 1.2 - Answer - Error & Exceptions Handling]]

---

### 🎯 **Learning Objectives – Chapter 1.2**

By the end of this sub-chapter, you should be able to:

- Explain the role and benefit of **[[Custom Exceptions]]** in program logic.
    
- Define **[[Security Logging]]** and identify which events must be logged.
    
- Justify the need to protect logs with **[[Integrity]]** controls against tampering.