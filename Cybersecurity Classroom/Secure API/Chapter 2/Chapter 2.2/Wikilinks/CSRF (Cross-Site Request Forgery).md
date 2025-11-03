### 🧠 **Definition and Risk 🎭**

**CSRF (Cross-Site Request Forgery)** is an attack that forces an end user's browser to execute unwanted actions on a trusted web application in which they are currently authenticated.

- **Goal:** The attacker leverages the victim's valid **[[Session Token]]** (usually a cookie) to submit malicious requests (e.g., change password, transfer money) without the victim's knowledge.
    
- **Vulnerability:** Occurs when the application relies only on the **[[Session Token]]** (cookie) for **[[Authentication]]** and does not verify where the request originated.
    
- **Mandate:** Mandatory defense is the **[[CSRF (Cross-Site Request Forgery)]] Token**.