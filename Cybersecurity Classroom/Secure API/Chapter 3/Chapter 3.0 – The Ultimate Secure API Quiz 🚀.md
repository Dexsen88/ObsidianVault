This quiz contains five questions covering all material from Chapters 1.1 through 2.3.

### 🧩 **Quiz Question 1 (Broken Access Control)**

**Q:** An API uses a valid **[[JWT (JSON Web Token)]]** to successfully authenticate User A. User A then calls the endpoint `/api/documents/ID-555` to retrieve a document. The document ID belongs to User B. If the API returns the document, which specific, critical vulnerability has been exploited?

A) **[[Mass Assignment]]**.

B) **[[CSRF (Cross-Site Request Forgery)]]**.

C) **Broken Object Level Authorization (BOLA/IDOR)**. 

D) **[[Command Injection]]**.

Click here to view the answer : [[Chapter 3.0 - Answer 1 - Secure API]]

---

### 🧩 **Quiz Question 2 (Authentication Standard)**

**Q:** When designing a modern, stateless API for a mobile application, why is a **[[JWT (JSON Web Token)]]** the mandatory, preferred method for **[[Authentication]]** over a simple static API Key?

A) JWTs are always encrypted with **[[Asymmetric Encryption]]**.

B) JWTs ensure **[[Availability]]** by enforcing **[[Rate Limiting]]**.

C) **JWTs contain claims and are secured with a [[Digital Signature]], allowing the API to verify the token's [[Integrity]] and [[Non-Repudiation]] instantly without server-side lookups.** 

D) JWTs automatically apply **[[Parameterization]]** to the request body.

Click here to view the answer : [[Chapter 3.0 - Answer 2 - Secure API]]

---

### 🧩 **Quiz Question 3 (Defense Against Unintended Updates)**

**Q:** An application's API allows a user to update their profile data. The developer uses an object-relational mapper (ORM) that automatically binds all received JSON fields to the user object. To prevent a **[[Mass Assignment]]** attack where an attacker injects an unauthorized `role: 'admin'` field, what is the mandatory defense?

A) Enforcing **[[Timeout]]** on the update request.

B) Applying **[[Contextual Output Encoding]]** to the user input.

C) **Using an Allow-List (Whitelist) to explicitly specify and enforce only the fields (e.g., 'name', 'email') the client is permitted to update.** 

D) Implementing a **[[CSRF (Cross-Site Request Forgery)]] Token**.

Click here to view the answer : [[Chapter 3.0 - Answer 3 - Secure API]]

---

### 🧩 **Quiz Question 4 (Resource Protection)**

**Q:** Why is **[[Rate Limiting]]** mandatory for all API endpoints, and what security pillar does it primarily protect?

A) It prevents **[[IDOR]]** and protects **[[Confidentiality]]**.

B) **It prevents resource exhaustion and [[Denial of Service (DoS)]] attacks, protecting [[Availability]].** 

C) It prevents **[[SQL Injection]]** and protects **[[Integrity]]**.

D) It enforces **[[Digital Signature]]** and protects **[[Non-Repudiation]]**.

Click here to view the answer : [[Chapter 3.0 - Answer 4 - Secure API]]

---

### 🧩 **Quiz Question 5 (External Attack Defense)**

**Q:** When an API is called by a web browser, which two security headers or tokens are essential for protecting the client from external website attacks?

A) **[[JWT (JSON Web Token)]]** and **HSTS**.

B) **[[CSRF (Cross-Site Request Forgery)]] Token** and **[[CORS (Cross-Origin Resource Sharing)]]** Header. 

C) **[[TLS Protocol]]** and **[[Verbose Error Message]]**.

D) **[[Phishing]]** Protection and **[[Mass Assignment]]** Protection.

Click here to view the answer : [[Chapter 3.0 - Answer 5 - Secure API]]
