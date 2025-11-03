### 🧠 **Core Security Principle 🛑**

**"Never Trust User Input"** is the fundamental maxim in application security. It states that _any_ data originating outside the application's trusted boundary—whether from a web form, an API parameter, a file upload, or a database query result—must be treated as potentially malicious or malformed.

- **Rationale:** Attackers exploit the assumption of trust. They craft input to be malicious, while legitimate users often provide data that is simply formatted incorrectly.
    
- **Action:** This principle mandates rigorous **[[Input Validation]]** at the server boundary (the "trust boundary") before the data is processed, stored, or used in any sensitive operation.
    
- **Bypassing:** Security controls applied only at the client-side (browser) are **never** sufficient, as they can be easily bypassed by attackers using simple tools to send direct requests to the server.