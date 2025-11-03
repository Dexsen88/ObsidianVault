🌟 **Aisha’s Hidden Fields**
![[Aisha's Hidden Fields.png]]
Aisha created an API endpoint (`/api/users/update`) that allowed users to change their name and email. The application used an automatic data binding library. An attacker intercepted the request, added a hidden field for `role: 'admin'`, and the application automatically updated the attacker's account to an administrator.

Elena: “That’s a classic **[[Mass Assignment]]** vulnerability, also known as **Object Injection**. Your API failed to filter out the malicious input field, violating the **[[Principle of Least Privilege]]** at the data layer. You must strictly control which fields can be updated by the client.”

### 🧠 **Mass Assignment (Object Injection)**

**[[Mass Assignment]]** is a security flaw that occurs when an application automatically binds client-supplied data (from a JSON or form body) to internal data model properties without filtering.

- **Vulnerability:** Attackers can inject fields they are not authorized to change (e.g., `is_admin`, `account_balance`, `user_id`) into the request body. If the application automatically maps this input to the database object, the unauthorized fields are silently updated, violating **[[Integrity]]** and enabling **[[Privilege Escalation]]**.
    
- **Defense Mandate:** Developers must use an **Allow-Listing** (Whitelist) approach, defining _exactly_ which fields the user is permitted to modify, and rejecting all others. **Deny-Listing** (Blacklisting) is prone to failure as developers often forget sensitive fields.
    

### 💡 **Data Limiting: Request and Response**

Beyond **[[Mass Assignment]]**, secure APIs must strictly limit the amount and scope of data handled in both directions:

1. **Request Limiting:** The API must strictly limit resource-intensive inputs to prevent **[[Denial of Service (DoS)]]** attacks. This includes limiting file sizes, maximum length of string inputs, and the complexity of request structures (e.g., number of items in an array). This is a specialized form of **[[Rate Limiting]]** for resource consumption.
    
2. **Response Limiting (Data Minimization):** The API must never return more data than the client needs. This is a crucial application of the **[[Data Minimization]]** principle. If a client only needs the user's name, the response should not include their address, internal database ID, or hashed password. This mitigates **[[Information Leakage]]** if the response is intercepted.
    

### 🎯 **API Schema Validation**
![[API Schema Validation.png]]

The most effective defense against **[[Mass Assignment]]** and resource exhaustion is strict **API Schema Validation**. The API specification (using tools like OpenAPI/Swagger) must clearly define:

- The exact structure, type, and maximum length of **all expected input fields**.
    
- The exact structure of **all returned output fields** (enforcing **[[Data Minimization]]**).
    

---

### 🧩 **Mini Quiz – Chapter 2.1**

**Q:** An attacker sends a request to an API's profile update endpoint and successfully changes the value of a hidden, unlisted field called `premium_status: true`. What is the primary vulnerability exploited, and what is the mandatory defense?

A) Vulnerability: **[[SQL Injection]]**; Defense: **[[Contextual Output Encoding]]**.

B) **Vulnerability: [[Mass Assignment]]; Defense: Strictly allow-list (whitelist) all updatable fields on the server-side.** 

C) Vulnerability: **[[BOLA]]**; Defense: Check the **[[JWT (JSON Web Token)]]**'s expiry time.

D) Vulnerability: **[[Verbose Error Message]]**; Defense: Use **[[Fail-Safe Defaults]]**.

Click here to view the answer : [[Chapter 2.1 - Answer - Secure API]]

---

### 🎯 **Learning Objectives – Chapter 2.1**

By the end of this sub-chapter, you should be able to:

- Define **[[Mass Assignment]]** and explain how it violates **[[Integrity]]**.
    
- Justify the use of an **Allow-List** for updating data models.
    
- Explain how **Response Limiting** enforces the **[[Data Minimization]]** principle.