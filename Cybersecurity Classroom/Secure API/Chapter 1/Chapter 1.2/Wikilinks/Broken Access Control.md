### 🧠 **Definition and Risk 🔓**

**Broken Access Control** is a critical security vulnerability that occurs when an application fails to properly enforce restrictions on what an authenticated user is permitted to view or do. It is the failure of the **[[Authorization]]** mechanism.

- **Goal:** To ensure that after a user is identified (**[[Authentication]]**), their actions and resource access conform to the **[[Principle of Least Privilege]]**.
    
- **Impact:** Leads to unauthorized **[[Information Leakage]]**, data modification, or privilege abuse (e.g., a standard user accessing administrative functionality).
    
- **Mandate:** **Authorization** checks must be performed on the **[[Server-Side Validation]]** for every request that touches sensitive data or state-changing functions.