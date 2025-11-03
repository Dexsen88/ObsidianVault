### 🧠 **Definition and Vulnerability 🎯**

**Insecure Direct Object Reference (IDOR)** is an **[[Access Control]]** vulnerability that occurs when an application exposes a direct reference to an internal implementation object (like a file name, database key, or user ID) and does not properly check if the **authenticated** user is **authorized** to access that specific object.

- **Mechanism:** An attacker bypasses **[[Authorization]]** by changing a parameter in the API call or URL (e.g., changing `user_id=10` to `user_id=12`) to view, modify, or delete a resource belonging to another user.
    
- **Defense:** The mandatory fix is rigorous **[[Authorization]]** on the **[[Server-Side Validation]]** for every request. The application must verify that the user's **[[Role]]** or identity is explicitly linked to the requested object.
    
- **Impact:** A successful IDOR attack leads to a massive violation of **[[Confidentiality]]** and **[[Integrity]]**.