### 🧠 **Definition and Mechanism 🌐**

The **SameSite** cookie attribute is a security feature that instructs a user's browser to restrict when a **[[HTTP Cookie]]** (which often carries the **[[Session Token]]**) is sent with cross-site requests.

- **Goal:** To mitigate the risk of **[[Cross-Site Request Forgery (CSRF)]]** attacks by preventing an external, malicious site from tricking a user's browser into sending their authenticated session cookie along with an unwanted request.
    
- **Modes:** Common modes include:
    
    - **Strict:** The cookie is _never_ sent with cross-site requests.
        
    - **Lax (Recommended Default):** The cookie is only sent with cross-site requests for top-level navigations (like following a link), but _not_ with cross-site POST requests or requests made via scripts (like an image tag).
        
- **Security Benefit:** It is a modern, server-side defense that must be implemented on the **[[HTTP Cookie]]** alongside the **[[CSRF Token]]** for a robust **[[Defense in Depth]]** strategy against CSRF.