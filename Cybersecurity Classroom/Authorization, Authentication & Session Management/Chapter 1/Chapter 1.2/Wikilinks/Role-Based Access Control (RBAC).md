### 🧠 **Definition and Mechanism 🏷️**

**Role-Based Access Control (RBAC)** is the most common model used to manage **Authorization** in modern applications. In this model, permissions are not assigned directly to individual users but are instead aggregated into logical groups called **[[Role]]**s. Users are then assigned one or more roles.

- **Goal:** To streamline the management of access rights and simplify security auditing. It separates users from privileges.
    
- **Security Benefit:** RBAC inherently enforces the **[[Principle of Least Privilege]]** because it's easier to verify that a role only contains the minimum permissions required. This minimizes the attack surface and potential damage from issues like **[[Insecure Direct Object Reference (IDOR)]]**.
    
- **Procedure:** When an authenticated user requests an action, the application checks the user's assigned role(s) against the permission required for that action on the **[[Server-Side Validation]]**. This is a core component of **[[Access Control]]**.