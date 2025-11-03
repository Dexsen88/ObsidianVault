🌟 **Aisha’s Missing Key** 
![[Aisha's Missing Key.png]]
Aisha created a simple API for her mobile app to fetch user data. She designed it using standard HTTP requests and responses. The problem was, anyone who figured out the URL could access _all_ user data because the API relied only on the network being internal.

Elena: “You designed a functional API, but not a secure one. You violated the **[[Never Trust User Input]]** and **[[Authorization]]** principles. Every API request, internal or external, must be treated as untrusted and secured with a mandatory, non-repudiable **[[Authentication]]** mechanism, like an API Key or Token.”

### 🧠 **API Design and REST**

Most modern APIs are built following the **REST (Representational State Transfer)** architectural style, which relies on standard HTTP methods and URLs to manage resources.

- **Resources:** Everything the API exposes is a resource (e.g., `/api/users/123`).
    
- **Methods:** Standard HTTP methods map to CRUD (Create, Read, Update, Delete) operations:
    
    - `GET`: Read (Fetch data)
        
    - `POST`: Create (Submit new data)
        
    - `PUT`/`PATCH`: Update (Modify existing data)
        
    - `DELETE`: Delete (Remove data)
        

### 💡 **API Authentication: Identifying the Caller**

Since APIs are stateless, they cannot rely on a traditional web session cookie for **[[Authentication]]**. Instead, a token or key must be sent with every request.

- **API Keys (Service-to-Service):** A simple secret string used to identify the application or service calling the API. They are typically static and used for machine-to-machine communication.
    
    - _Security Risk:_ API Keys often have poor revocation mechanisms and should **not** be used for user-facing applications.
        
- [[JWT (JSON Web Tokens)]] and OAuth 2.0 (User-Facing):** The mandatory standard for user-facing and mobile applications.
    
    - **OAuth 2.0:** Provides a secure **[[Authorization]]** framework for delegating access.
        
    - **JWT:** A digitally **[[Digital Signature]]**-d token that contains claims (e.g., user ID, roles, expiration time) that the API can trust and verify without a database lookup, ensuring **[[Integrity]]** and **[[Non-Repudiation]]**.
        

### 🎯 **Mandatory Transport Security**
![[HTPPSS Protocol.png]]


Regardless of the authentication scheme chosen, all API traffic **MUST** be secured using **[[TLS Protocol]]** (HTTPS). Sending tokens, keys, or any **[[Personally Identifiable Information (PII)]]** over unencrypted HTTP is a catastrophic violation of **[[Confidentiality]]**.

---

### 🧩 **Mini Quiz – Chapter 1.1**

**Q:** Why is using a **JWT (JSON Web Token)** generally the mandatory and preferred **[[Authentication]]** method for a user-facing mobile API over a static API Key?

A) Because JWTs automatically perform **[[Contextual Output Encoding]]** on the request body.

B) **Because a JWT is digitally signed, allowing the API to quickly verify its integrity and non-repudiation without requiring a database lookup for every request.** 

C) Because static API Keys are only effective against **[[Denial of Service (DoS)]]** attacks.

D) Because JWTs are immune to **[[Phishing]]** attacks.

Click here to view the answer : [[Chapter 1.1 - Answer - Secure API]]

---

### 🎯 **Learning Objectives – Chapter 1.1**


By the end of this sub-chapter, you should be able to:

- Describe how REST design uses HTTP methods and resources.
    
- Justify why **JWT** and **OAuth 2.0** are the standard for user-facing API **[[Authentication]]**.
    
- Explain the mandatory requirement of using the **[[TLS Protocol]]** (HTTPS) for all API traffic.