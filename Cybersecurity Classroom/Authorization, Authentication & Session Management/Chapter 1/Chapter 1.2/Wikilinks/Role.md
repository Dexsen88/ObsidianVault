### 🧠 **Definition and Purpose 🏷️**

A **Role** is a defined collection of permissions or privileges assigned to a user within an application. Roles are the central element of the **Role-Based Access Control (RBAC)** authorization model.

- **Goal:** To simplify the management of user permissions. Instead of assigning individual permissions to hundreds of users, permissions are grouped into roles (e.g., 'Administrator', 'Editor', 'Guest'), and users are assigned the appropriate role(s).
    
- **Security Benefit:** Enforces the **[[Principle of Least Privilege]]** by making it easier to audit and manage exactly what access a user has. When a user is authenticated, the system checks their assigned role against the permissions required for the requested action to enforce **[[Access Control]]**.
    
- **Example:** The 'Guest' role might have permission to `view_public_data` but not to `edit_data`.