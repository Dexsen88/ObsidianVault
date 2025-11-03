### 🧠 **Definition and Structure 🎟️**

A **JWT (JSON Web Token)** is a compact, URL-safe means of representing claims (user ID, roles, expiry) to be transferred between two parties. It is the mandatory standard for session management in stateless APIs.

- **Goal:** To establish trust between the client and the API endpoint without relying on server-side session state.
    
- **Mechanism:** It consists of three parts (Header, Payload, Signature). The Signature part is a **[[Digital Signature]]** created using a secret **[[Symmetric Encryption]]** key or an **[[Asymmetric Encryption]]** **[[Private Key]]**, which the API uses to verify the token's **[[Integrity]]** and **[[Non-Repudiation]]**.
    
- **Security:** If signed with a strong key, the API can trust the data inside the token (the claims) because any tampering would invalidate the signature.