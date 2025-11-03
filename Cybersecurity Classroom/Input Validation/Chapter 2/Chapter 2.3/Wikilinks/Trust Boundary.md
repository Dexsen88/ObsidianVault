### 🧠 **Definition and Identification 🧱**

A **Trust Boundary** is a conceptual or physical line within a software system that separates code, components, or services with different levels of security privileges. Data that crosses this line is considered untrusted until it is explicitly checked.

- **Identifying Boundaries:** Any point where control is passed from a low-privilege component (e.g., a web browser) to a high-privilege component (e.g., a backend database) defines a boundary.
    
- **The Rule:** The security rule enforced at every boundary is simple: **Revalidate**. All data entering a more trusted side of the boundary must be subjected to the full **[[Input Validation]]** process, enforcing the **[[Never Trust User Input]]** principle.
    
- **Examples:** The transition from client to server, or from an external API to an internal processing microservice.