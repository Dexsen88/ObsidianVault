### 🧠 **Definition and Vulnerability 🎯**

**Insecure Direct Object Reference (IDOR)** is an **[[Access Control]]** vulnerability that occurs when an application exposes a reference to an internal implementation object (like a file name, database key, or user ID) and does not properly check if the authenticated user is authorized to access the specific object referenced.

- **Mechanism:** An attacker bypasses authorization by changing a parameter in the API call or URL (e.g., changing `?order_id=123` to `?order_id=124`) to view, modify, or delete a resource they shouldn't have access to.
    
- **Defense:** The mandatory fix is rigorous **Authorization** on the **[[Server-Side Validation]]** for every request. The application must verify two things: 1) the user is authenticated, and 2) the user's **[[Role]]** or identity is explicitly linked to the requested object.
    
- **Impact:** A successful IDOR attack leads to a massive violation of **[[Confidentiality]]** and **[[Integrity]]**.