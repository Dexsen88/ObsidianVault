🌟 **Aisha’s Costly Burst** 
![[Aisha's Costly Burst.png]]
Aisha enforced **[[Rate Limiting]]** on her login page (as discussed in the Error Handling module), but forgot to apply it to her search API, which queries a multi-terabyte database. An attacker realized this and sent 500 search queries per second, causing the database costs to spike and slowing the entire application to a crawl.

Elena: "That's a **[[Denial of Service (DoS)]]** attack via resource exhaustion, targeting your API's business logic. **[[Rate Limiting]]** is mandatory for _all_ resource-intensive API endpoints, not just **[[Authentication]]**. Furthermore, complex API payloads (like XML or deeply nested JSON) require special security checks to prevent abuse."

### 🧠 **API Rate Limiting: The Availability Guard**

**[[Rate Limiting]]** is a critical application-layer defense against **[[Denial of Service (DoS)]]** attacks and is mandatory for API security.

- **Goal:** To protect the API's backend resources (database, CPU, memory) and ensure **[[Availability]]** by limiting the number of requests a single client (identified by IP, User ID from the **[[JWT (JSON Web Token)]]**, or API Key) can make within a specified time window.
    
- **Implementation:** Different endpoints should have different limits based on cost. For instance, a `/profile` endpoint can allow 100 requests/minute, but a cost-intensive `/search` endpoint might only allow 5 requests/minute.
    
- **Response:** When the limit is exceeded, the API must return a secure HTTP 429 (Too Many Requests) status code.
    

### 💡 **Payload Security: XML and Deep Nesting**

Modern APIs often handle complex data structures, which introduce specific vulnerabilities:

1. **XML External Entity (XXE) Injection:** If the API accepts XML input, it must be configured to disable the processing of **External Entities**. An attacker can use these entities to perform **[[Information Leakage]]** (reading local files on the server) or launch **[[Denial of Service (DoS)]]** attacks (entity expansion, known as "Billion Laughs").
    
2. **Deep Nesting/Large Payloads:** Attackers can send huge, deeply nested JSON or XML payloads to force the parser to consume excessive memory and CPU, leading to resource exhaustion and a **[[Denial of Service (DoS)]]** crash.
    
    - **Defense:** Mandatory **input validation** must enforce limits on **maximum payload size** and **maximum nesting depth**.
        

### 🎯 **The API Security Triad**

Secure API design enforces three layers of defense on every request, in this order:

1. **[[Authentication]]** (Who are you? - **JWT**).
    
2. **Authorization** (Are you allowed? - **BOLA** check).
    
3. **Control** (How often/much? - **[[Rate Limiting]]**).
    

---

### 🧩 **Mini Quiz – Chapter 2.3**

**Q:** Why is it mandatory to disable the processing of **External Entities** when an API is configured to accept XML payloads?

A) To enforce **[[Parameterization]]** against **[[SQL Injection]]**.

B) **To prevent XXE (XML External Entity) attacks, which can lead to local file disclosure (Information Leakage) or resource exhaustion (Denial of Service).** 

C) To ensure the XML payload is signed with a **[[Digital Signature]]**.

D) To block **[[CSRF (Cross-Site Request Forgery)]]** attacks from unauthorized origins.

Click here to view the answer : [[Chapter 2.3 - Answer - Secure API]]

---

### 🎯 **Learning Objectives – Chapter 2.3**

By the end of this sub-chapter, you should be able to:

- Reiterate the mandatory use of **[[Rate Limiting]]** across all resource-intensive API endpoints.
    
- Identify the risks of **XML External Entity (XXE) Injection** and deep nesting.
    
- Explain the need for setting limits on **maximum payload size** and nesting depth to prevent **[[Denial of Service (DoS)]]**.