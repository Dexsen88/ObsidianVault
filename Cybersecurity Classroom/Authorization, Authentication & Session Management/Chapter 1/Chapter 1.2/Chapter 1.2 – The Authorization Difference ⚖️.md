🌟 **Aisha’s Manager Access** 
![[Aisha's Manager Access.png]]
Aisha successfully logged into her new account (Authentication success) but was surprised to see the 'Approve Refunds' button, which she knew only managers should be able to click. She clicked it, and the application processed a refund!

Elena: “Your **Authentication** system is fine, but your **Authorization** system failed. You proved who you are, but the application didn't properly check what you're allowed to do. Authentication is the door lock; Authorization is the bouncer inside.”

### 🧠 **Authentication vs. Authorization**

These two processes are sequential and distinct:

1. **Authentication:** **Who are you?** The process of verifying a claimed identity using **[[Multi-Factor Authentication (MFA)]]** or credentials stored as a **[[Password Hash]]**.
    
2. **Authorization:** **What are you allowed to do?** The process of determining if the authenticated user has the necessary permissions to perform a specific action or access a specific resource.
    

### 💡 **Access Control Models**
![[Access Control Models.png]]

Authorization is enforced using an **[[Access Control]]** model. The most common model for modern applications is:

- **Role-Based Access Control (RBAC):** Permissions are grouped into specific, defined **[[Role]]**s (e.g., 'Admin', 'Manager', 'Standard User'). The user is assigned one or more roles, and the application checks the role against the required permissions for an action.
    
    - _Example:_ The 'Manager' role has the `approve_refund` permission; the 'Standard User' role does not.
        

### 🎯 **The Mandatory Server Check**

The failure in Aisha's scenario is often a result of relying on a client-side check. The 'Approve Refunds' button was visible, but even if it were hidden, an attacker could still make the underlying request.

- **Rule:** Every access decision and every state-changing request (like deleting, modifying, or transferring) must be enforced on the **[[Server-Side Validation]]** after the user's identity has been verified via **Authentication**.
    
- **Vulnerability:** This defense protects against **[[Insecure Direct Object Reference (IDOR)]]**, where an attacker attempts to access data or functions they shouldn't by manipulating a parameter in the URL or API request. This violates **[[Confidentiality]]** and **[[Integrity]]**.
    

### 🔑 **Concept: Principle of Least Privilege**

The entire Authorization system should adhere to the **[[Principle of Least Privilege]]** (PoLP). Users should only be granted the minimum permissions required to perform their jobs, minimizing the damage if their account is compromised.

### 🧩 **Mini Quiz – Chapter 1.2**

**Q:** What is the critical security vulnerability that occurs when an authenticated user modifies a URL parameter from `user_id=10` to `user_id=12` and successfully views another user’s sensitive profile data?

A) **[[Denial of Service (DoS)]]**

B) **[[Cross-Field Validation]]**

C) **[[Insecure Direct Object Reference (IDOR)]]** 

D) **[[Path Traversal]]**

Click here to view the answer : [[Chapter 1.2 Answer - AAS]]

### 🎯 **Learning Objectives – Chapter 1.2**

By the end of this sub-chapter, you should be able to:

- Clearly distinguish between **Authentication** (identity verification) and **Authorization** (permission granting).
    
- Understand **[[Role-Based Access Control (RBAC)]]** as a primary model for granting permissions.
    
- Identify the vulnerability known as **[[Insecure Direct Object Reference (IDOR)]]** and how **Authorization** prevents it.
    
- Apply the **[[Principle of Least Privilege]]** to all user accounts and system processes.