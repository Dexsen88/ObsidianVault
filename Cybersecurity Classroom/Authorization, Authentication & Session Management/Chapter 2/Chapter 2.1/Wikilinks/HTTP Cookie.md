### 🧠 **Definition and Mechanism 🍪**

An **HTTP Cookie** is a small piece of data that a server sends to a user's web browser. The browser may store it and send it back to the same server with subsequent requests. Cookies are the standard mechanism for maintaining **session state** in stateless HTTP.

- **Role in Security:** Cookies are the most common carrier mechanism for the **[[Session Token]]**.
    
- **Security Attributes:** Secure cookies must be set with specific flags to prevent compromise:
    
    - **Secure:** Ensures the cookie is only sent over encrypted **HTTPS** connections.
        
    - **HttpOnly:** Prevents client-side scripts (JavaScript) from accessing the cookie, mitigating many **[[XSS]]** attack vectors for **[[Session Hijacking]]**.
        
    - **SameSite:** Mitigates **[[Cross-Site Request Forgery (CSRF)]]** attacks.
        
- **Storage:** The token stored inside the cookie is the temporary key to the user's identity.