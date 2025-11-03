### 🧠 **Definition and Procedure 🚨**

**Logging the Failure** is the mandatory server-side procedure that is executed immediately after an **Input Validation** check fails. This is a critical step in both application security and incident response.

- **Action Plan:**
    
    1. **Immediate Halt:** The application must stop processing the untrusted request to prevent data corruption or security breaches.
        
    2. **Generic Response:** Send a non-specific, vague error (e.g., HTTP 400 Bad Request) back to the client. This is essential to prevent **Information Leakage** that could aid an attacker.
        
    3. **Audit Record:** Securely log the full details of the failed attempt on the internal **Security Logging** system.
        

### 📝 **What to Record**

The log entry must be comprehensive for **Forensics** purposes:

- **Time and Origin:** Timestamp and source IP address of the request.
    
- **Attempted Action:** The endpoint or action the user was trying to perform.
    
- **Failure Point:** The specific validation rule that was violated.
    
- **Raw Input:** The malicious or malformed input data itself (handle securely to avoid re-introducing vulnerabilities in the log system).