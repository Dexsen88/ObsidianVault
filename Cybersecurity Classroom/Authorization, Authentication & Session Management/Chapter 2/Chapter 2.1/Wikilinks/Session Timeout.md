### 🧠 **Definition and Purpose ⏳**

**Session Timeout** is a security policy that automatically invalidates an active session after a predetermined period of inactivity or a total maximum duration.

- **Types:**
    
    - **Idle Timeout:** Invalidates the session if the user stops sending requests for a defined time (e.g., 15 minutes).
        
    - **Absolute Timeout:** Invalidates the session regardless of activity after a maximum time (e.g., 8 hours).
        
- **Goal:** To limit the window of opportunity for an attacker to use a stolen **[[Session Token]]**. Even if a token is compromised, its utility is restricted by the short expiry time. This is a critical component of preventing **[[Session Hijacking]]**.
    
- **Best Practice:** Critical applications (like banking) enforce very short idle timeouts (3-5 minutes), while less sensitive applications may use longer times.