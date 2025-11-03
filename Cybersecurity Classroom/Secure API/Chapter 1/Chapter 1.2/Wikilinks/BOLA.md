### 🧠 **Definition and Context 🎯**

**BOLA (Broken Object Level Authorization)** is a contemporary term for **[[IDOR]]** that specifically applies to **API security**, particularly in RESTful API architectures where unique resource identifiers are exposed in URL paths or parameters.

- **Goal:** To highlight the critical nature of the **[[Authorization]]** flaw when handling object instances exposed via API endpoints (e.g., `/api/orders/{orderId}`).
    
- **Mechanism:** An authenticated user submits a valid token but requests a resource ID for which they lack **[[Authorization]]**.
    
- **Mandate:** Every API endpoint that handles an object ID must contain code to verify the user's ownership of that specific object, based on data extracted from the verified **[[JWT (JSON Web Token)]]**.