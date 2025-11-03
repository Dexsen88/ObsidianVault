🌟 **Aisha’s Cookie Exposure**
![[Aisha's Cookie Exposure.png]]
Aisha’s new application was hit by an **[[XSS]]** attack. An attacker injected a simple JavaScript line (`document.cookie`) and was able to read the user's **[[Session Token]]** straight from the browser. This led to a mass instance of **[[Session Hijacking]]**.

Elena: "That happened because your cookie was not properly secured with the **HttpOnly** flag. The **[[Session Token]]** is a critical secret, and it must be protected from both network eavesdropping and client-side code execution. We use security flags and headers to enforce this."

### 🧠 **Mandatory Cookie Security Flags**

The **[[HTTP Cookie]]** used to carry the **[[Session Token]]** must be secured with the following flags enforced on the **[[Server-Side Validation]]**:
![[Mandatory Cookie Security Flags.png]]

### 💡 **Protecting the Session Store**

Even a secure cookie can't help if the **[[Session Store]]** is compromised. All server-side session data must be stored and accessed according to the **[[Principle of Least Privilege]]**. Furthermore, the token itself must be invalidated upon specific events:

- **Logout:** The server must explicitly destroy the token in the **[[Session Store]]**.
    
- **Password Change:** The server must invalidate (force logout of) all current sessions for that user. This is **[[Session Revocation]]**.
    
- **Privilege Change:** If a user's **[[Role]]** or permission set changes (e.g., promoted to Admin), the existing session should be invalidated, forcing a new login to prevent using old, less restricted sessions.
    

### 🎯 **The Defense Against CSRF**

![[The Defense Against CSRF.png]]

While the `SameSite` flag on the cookie is a great modern defense against **[[Cross-Site Request Forgery (CSRF)]]**, it is not a complete solution. For all sensitive, state-changing actions (POST, PUT, DELETE), an explicit **[[CSRF Token]]** must be implemented.

### 🧩 **Mini Quiz – Chapter 2.2**

**Q:** What is the security consequence of omitting the **HttpOnly** flag on the cookie containing the **[[Session Token]]**?

A) The session will fail to expire correctly, violating the **[[Session Timeout]]** policy.

B) A successful [[XSS]] attack can use JavaScript to read and steal the Session Token, leading directly to [[Session Hijacking]]. 

C) The token will be transmitted over unencrypted HTTP, violating the **Secure** flag.

D) The token will be exposed to a **[[Path Traversal]]** attack on the server's file system.

Click here to view the answer : [[Chapter 2.2 - Answer AAS]]

### 🎯 **Learning Objectives – Chapter 2.2**

By the end of this sub-chapter, you should be able to:

- Explain the function and security necessity of the **Secure**, **HttpOnly**, and **SameSite** cookie flags.
    
- Understand the concept of **[[Session Revocation]]** and why it's necessary upon sensitive user actions.
    
- Identify the **[[CSRF Token]]** as the definitive defense against **[[Cross-Site Request Forgery (CSRF)]]**.