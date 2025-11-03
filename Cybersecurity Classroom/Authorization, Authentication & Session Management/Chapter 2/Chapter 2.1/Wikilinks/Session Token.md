### 🧠 **Definition and Purpose 🆔**

A **Session Token** (often called a Session ID) is a unique, cryptographically random string of data issued by the server to a client upon successful **[[Authentication]]**. It acts as the key the client uses to prove its identity for the duration of the session without resubmitting credentials.

- **Mechanism:** The token is transmitted back and forth with every request, typically within an **[[HTTP Cookie]]**. The server uses the token as a lookup key to retrieve the user's saved session data from the **[[Session Store]]**.
    
- **Security Importance:** The token is the most valuable secret after the password. If it is compromised or predictable (e.g., not cryptographically random), an attacker can easily execute **[[Session Hijacking]]**.
    
- **Requirement:** Tokens must be long, randomly generated, and securely managed to ensure the **[[Confidentiality]]** of the user's session.