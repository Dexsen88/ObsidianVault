### 🧠 **Definition and Purpose 💾**

The **Session Store** is the secure, server-side data repository where the server keeps track of all currently active sessions and their associated state data.

- **Content:** It links the client's received **[[Session Token]]** to the user's identity (e.g., user ID), **[[Role]]**, login time, and any temporary shopping cart or preference data.
    
- **Security Importance:**
    
    - **State Retrieval:** It allows the server to verify the validity of a token and retrieve necessary information for **[[Authorization]]**.
        
    - **Central Control:** It allows the server to instantly terminate a session from a central point (e.g., on user logout or compromise), fulfilling the session **Destruction** requirement.
        
- **Technology:** This is typically implemented using a dedicated database (like Redis or a relational database table) that is fast, secure, and highly **[[Available]]**.