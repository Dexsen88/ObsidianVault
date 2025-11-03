### 🧠 **Definition and Purpose 🤝**

**OAuth 2.0** is an open standard authorization framework that enables an application to obtain limited access to a user's protected resources (e.g., photos, contacts) on a service provider (e.g., Facebook, Google) without exposing the user's login credentials.

- **Goal:** To securely delegate **[[Authorization]]** from the user to the client application. It ensures the **[[Principle of Least Privilege]]** is applied by granting access only to specific, requested scopes.
    
- **Mechanism:** The framework issues an **[[Access Token]]** which the client application uses to make requests on the user's behalf.
    
- **Crucial Distinction:** OAuth 2.0 is explicitly for **Authorization** (What you can do) and is not intended for **[[Authentication]]** (Who you are).