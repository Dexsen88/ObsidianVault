This quiz contains five questions covering all material from Chapters 1.1 through 2.3.

### 🧩 **Quiz Question 1 (Fail-Safe Principle)**

**Q:** An application's **[[Session Store]]** becomes unavailable, and the system decides to keep the user logged in, assuming the previous **[[Authentication]]** was valid. Which security principle is being violated, and what is the consequence?

A) Principle Violated: **[[Rate Limiting]]**; Consequence: **[[Denial of Service (DoS)]]**.

B) Principle Violated: **[[Data Minimization]]**; Consequence: **[[Verbose Error Message]]**.

C) **Principle Violated: [[Fail-Safe Defaults]]; Consequence: A [[Confidentiality]] breach by allowing unauthorized access (failing open).** 

D) Principle Violated: **[[Contextual Output Encoding]]**; Consequence: **[[Cross-Site Scripting (XSS)]]**.

Click here to view the answer : [[Chapter 3.0 - Answer 1 - Error & Exceptions Handling]]

---

### 🧩 **Quiz Question 2 (Information Leakage)**

**Q:** Why does the display of a **[[Verbose Error Message]]** on a production website pose a security risk, and what control is compromised?

A) Because it causes a **[[Chained Error]]**; the **[[Integrity]]** control is compromised.

B) **Because it exposes internal server details (e.g., file paths, library versions), leading to [[Information Leakage]], which compromises the [[Confidentiality]] control.** 

C) Because it forces the use of **[[Parameterization]]**; the **[[Availability]]** control is compromised.

D) Because it violates the **[[SameSite]]** cookie attribute; the **[[Non-Repudiation]]** control is compromised.

Click here to view the answer : [[Chapter 3.0 - Answer 2 - Error & Exceptions Handling]]



---

### 🧩 **Quiz Question 3 (Availability Defense)**

**Q:** Which specific security control is the mandatory application-layer defense against a **[[Denial of Service (DoS)]]** attack that attempts to consume server resources through excessive login requests?

A) **[[Data Sanitization]]** of the password field.

B) **[[Security Logging]]** of all failed attempts.

C) **[[Contextual Output Encoding]]** of the login message.

D) **[[Rate Limiting]]** of login attempts per IP address or user ID over a set time period. 

Click here to view the answer : [[Chapter 3.0 - Answer 3 - Error & Exceptions Handling]]

---

### 🧩 **Quiz Question 4 (Handling Distributed Errors)**

**Q:** In a microservices architecture, Service A calls Service B. Service B fails and returns a **[[Verbose Error Message]]** that includes its internal database connection string. What must Service A do before logging the error in the central log system?

A) Re-throw the error as a **[[Chained Error]]** without modification.

B) Apply **[[Parameterization]]** to the connection string.

C) **Sanitize or cleanse the error message to remove the sensitive connection string, then log the sanitized message with a Correlation ID.** 

D) Immediately trigger a **[[Timeout]]** on the connection to Service B.

Click here to view the answer : [[Chapter 3.0 - Answer 4 - Error & Exceptions Handling]]


---

### 🧩 **Quiz Question 5 (Resource Control)**

**Q:** A function that fetches configuration from an external service sometimes hangs indefinitely, causing its thread to be permanently blocked. What mandatory security control should be applied to this external network call?

A) A **[[Custom Exceptions]]** object should be used instead of a generic one.

B) **A mandatory [[Timeout]] should be set to automatically terminate the operation after a maximum duration.** 

C) **[[Server-Side Validation]]** should be performed on the function's return value.

D) The operation should be protected by a **[[Digital Signature]]**.

Click here to view the answer : [[Chapter 3.0 - Answer 5 - Error & Exceptions Handling]]

