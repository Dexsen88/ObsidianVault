🌟 **Aisha’s Blind Spot**
![[Avoiding Log Injection and PII.png]]
A security alert notified Aisha that a server was potentially compromised. She checked the server's log files but found only entries like "Request processed successfully." She had no information about _which user_ made the request, _what_ the request was, or _if_ it contained any malicious input.

Elena: “Your logs failed the **Context** and **Relevance** principles. Logs must be **Actionable**. Every log entry related to security or sensitive data must contain sufficient detail to answer the 'who,' 'what,' 'where,' 'when,' and 'how' of an event, which is necessary for **[[Non-Repudiation]]**.”

### 🧠 **The Five Ws of Security Logging**

For a log entry to be useful for forensics and **[[Vulnerability Management]]**, it must follow the mandatory structure:

1. **Who:** The unique authenticated user ID, IP address, or application service account that initiated the action.
    
2. **What:** The specific action taken (e.g., `LOGIN_SUCCESS`, `FILE_DELETED`, `PERMISSION_DENIED`).
    
3. **When:** A precise, synchronized timestamp (mandatory **UTC/GMT** standard).
    
4. **Where:** The source system (host IP, server name) and the endpoint/function accessed.
    
5. **How:** Any relevant input data, parameters, or resulting status codes (e.g., HTTP 403, 500, or a database error).
    

### 💡 **Mandatory Principle: Log Centralization and Protection**

Logging must follow two non-negotiable architectural mandates:

1. **Centralization:** Logs must be immediately and securely transmitted from the source application/server to a dedicated, secured **[[Security Logging]]** system (a **SIEM - Security Information and Event Management** solution or dedicated log aggregator).
    
2. **Immutability (Tamper-Proof):** The centralized log store **must** be configured to be **Write-Once, Read-Many (WORM)**. The application or administrator account that _generates_ the log **must not** have permission to delete or modify the stored logs. This enforces **[[Non-Repudiation]]** and protects the forensic chain of evidence.
    

### 🎯 **Avoiding Log Injection and PII**
![[Aisha's Blind Spot.png]]

Logging itself presents a security risk if not handled correctly:

- **Log Injection:** Attackers can craft input that, when logged, pollutes the log file with false or misleading entries (e.g., `malicious user: LOGIN_SUCCESS`). Logs must use **Safe Logging APIs** that escape or sanitize input before writing.
    
- **PII/Secrets:** Logs must **never** contain sensitive data like passwords, secret keys, credit card numbers, or full session tokens. Logging this information violates the **[[Data Minimization]]** and **[[Confidentiality]]** principles. Use placeholders or **[[Data Masking]]** instead.
    

---

### 🧩 **Mini Quiz – Chapter 1.1**

**Q:** What is the primary reason why logs must be immediately moved from the source server to a separate, centralized, tamper-proof system?

A) To enforce **[[Parameterization]]** against **[[SQL Injection]]**.

B) To enable **[[Data Encryption]]** at the application layer.

C) **To ensure the log data is immutable and protected from tampering by an attacker who has compromised the source server, thereby guaranteeing [[Non-Repudiation]].** 

D) To automatically run **[[Software Composition Analysis (SCA)]]** on log entries.

Click here to view the answer : [[Chapter 1.1 - Answer - Security Logging]]

---

### 🎯 **Learning Objectives – Chapter 1.1**

By the end of this sub-chapter, you should be able to:

- List the **Five Ws** and explain their importance in log content.
    
- Justify the mandatory principles of **Centralization** and **Immutability** for security logs.
    
- Explain why logs must **avoid sensitive PII** and secrets.