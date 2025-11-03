### 🧠 **Definition and Risk 🗑️**

**Mass Assignment** (or Object Injection) is an API security flaw where an application automatically maps user-supplied input (e.g., JSON or form data) directly to a data model or database object without explicit field filtering.

- **Goal:** The attacker injects unauthorized fields (like `admin_role: true` or `user_id: 1`) into the request body. If the application's binding logic is too broad, these sensitive fields are silently updated.
    
- **Impact:** Violates **[[Integrity]]** and can lead to **[[Privilege Escalation]]** or fraudulent transactions.
    
- **Mandate:** Developers **must** adopt an **Allow-Listing** (Whitelist) strategy, explicitly specifying every field that can be updated from client input, and discarding all others.