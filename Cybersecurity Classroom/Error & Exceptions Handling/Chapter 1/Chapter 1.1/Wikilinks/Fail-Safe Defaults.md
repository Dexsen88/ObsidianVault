### 🧠 **Definition and Principle 🔒**

The principle of **Fail-Safe Defaults** (or Fail Securely) requires that access rights should be based on permission rather than exclusion. When a system or component fails, it must default to a secure, "closed" state.

- **Goal:** To prevent security compromises during periods of system instability or failure, thereby preserving **[[Confidentiality]]** and **[[Integrity]]**.
    
- **Application:** If a security check (like **[[Authentication]]** or **[[Authorization]]**) cannot be completed, the system must default to **denying** the request, rather than allowing it to proceed (failing open).
    
- **Contrast:** The opposite, "fail-open," is almost always a security vulnerability.