🌟 Aisha’s Data Breach
![[Aisha's Data Breach.png]]

Aisha fixed her API's [[Authentication]] using JWTs. However, when a user (ID 101) requested their profile data via /api/users/101, the API responded correctly. An attacker simply changed the request to /api/users/102 and instantly accessed another user's private data.

Elena: “That’s a classic case of **[[Broken Access Control]]**, specifically an **IDOR** vulnerability. Your API confirmed _who_ the caller was (**Authentication**), but failed to check _if_ that caller had **[[Authorization]]** to access the specific resource, violating the **[[Principle of Least Privilege]]** and **[[Confidentiality]]**.”

### 🧠 **Broken Access Control (BAC)**

**[[Broken Access Control]]** (BAC) is a critical vulnerability that occurs when an application fails to properly enforce restrictions on what authenticated users are permitted to do. This can allow users to view, modify, or delete data they shouldn't have access to, or perform actions reserved for administrators.

- **Goal:** The mandatory check after **[[Authentication]]**. It determines _what_ a user is allowed to do, based on their role and permissions.
    
- **Defense Failure:** BAC is often caused by an application trusting the user-supplied input (like a record ID) without verifying the user's permission to access that specific record.
    

### 💡 **IDOR and BOLA: The Two Faces of BAC**

Two of the most common and critical BAC flaws involve improper handling of resource identifiers:

|**Flaw**|**Definition**|**Mechanism**|**Severity**|
|---|---|---|---|
|**IDOR (Insecure Direct Object Reference)**|Directly exposing an internal implementation object (like a user ID, file name, or database key) and failing to validate user ownership.|An attacker changes the ID in the URL (`/api/users/102`) to view another user's data.|High|
|**BOLA (Broken Object Level Authorization)**|An industry-specific term for **IDOR** that occurs specifically in RESTful APIs. It is frequently the single most critical API security risk.|An attacker uses a valid **JWT** for user 101 but requests resource 102.|Critical|

### 🎯 **Mandatory Defense: Authorization Checks**
![[Mandatory Defense.png]]

The only mandatory defense against **IDOR** and **BOLA** is **Server-Side Authorization** checks for _every_ resource access:

1. **Extract:** Extract the user's identity (User ID or Role) from the verified **[[JWT (JSON Web Token)]]**.
    
2. **Validate Ownership:** Compare the User ID in the token against the **owner ID** of the requested resource (e.g., compare `token.user_id` with `resource.owner_id`).
    
3. **Mandatory Check:** The API **must** throw a secure 403 Forbidden error if the user ID from the token does not match the resource's owner ID.
    

---

### 🧩 **Mini Quiz – Chapter 1.2**

**Q:** User A successfully logs into an application and receives a valid **[[JWT (JSON Web Token)]]**. They then call the API endpoint `/api/documents/DOC-12345` to retrieve their document. If the API fails to verify that User A is the owner of DOC-12345 before returning the file, what vulnerability class is the API exposed to?

A) **[[Cross-Site Scripting (XSS)]]** due to improper **[[Contextual Output Encoding]]**.

B) **[[Denial of Service (DoS)]]** due to missing **[[Rate Limiting]]**.

C) **Broken Access Control ([[IDOR]]/[[BOLA]])** due to a missing **Authorization** check. 

D) **[[SQL Injection]]** due to missing **[[Parameterization]]**.

Click here to view the answer : [[Chapter 1.2 - Answer - Secure API]]

---

### 🎯 **Learning Objectives – Chapter 1.2**

By the end of this sub-chapter, you should be able to:

- Define **[[Broken Access Control]]** as the failure of **Authorization**.
    
- Define **IDOR** and **BOLA** as specific, critical API access control flaws.
    
- Explain the mandatory defense: performing a **Server-Side Authorization** check against the verified user identity from the token for every resource request.