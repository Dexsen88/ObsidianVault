### 🧠 **Definition and Mechanism ⚖️**

**Authorization** is the process of determining what an authenticated user or process is permitted to do or access. It answers the question: **"What are you allowed to do?"**

- **Goal:** To enforce security policies by granting access rights (permissions) to specific resources or functions.
    
- **Model:** This is primarily managed through an **[[Access Control]]** model, most commonly **[[Role-Based Access Control (RBAC)]]**, where permissions are grouped into **[[Role]]**s.
    
- **Security Check:** Authorization must be performed on the **[[Server-Side Validation]]** for every request to prevent vulnerabilities like **[[Insecure Direct Object Reference (IDOR)]]**. It is the sequential step following **[[Authentication]]**.