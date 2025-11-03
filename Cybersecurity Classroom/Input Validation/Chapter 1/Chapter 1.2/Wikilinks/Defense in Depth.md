### 🧠 **Definition and Purpose 📜**

**Security Logging** is the systematic recording of all security-relevant events that occur within an application or system. This includes events like login attempts, authorization failures, configuration changes, and, critically, failed input validation attempts.

- **Goal:** To establish an audit trail that documents system state and user actions, which is essential for ensuring accountability and providing proof of non-repudiation in security events.
    
- **Best Practice:** Logs must contain full context (user ID, timestamp, source IP), be stored securely on a separate server, and be protected from any tampering or deletion.
    
- **Defense:** A robust logging system is a core principle of **Defense in Depth** as it helps administrators and security teams detect attacks that have bypassed other controls.