**🌟 Aisha’s Cross-Origin Problem**
![[Aisha's Cross-Origin.png]]

Aisha’s mobile API was secure, but she created a web dashboard that called the same API. An attacker set up a malicious website that successfully tricked an authenticated user's browser into sending requests to Aisha's API. This exploit allowed the attacker to drain the user's account.

Elena: “That was a **[[CSRF (Cross-Site Request Forgery)]]** attack, enabled by your browser’s default trust and a lack of proper **Security Headers**. The API must defend against both input attacks (like **[[SQL Injection]]**) and external web attacks (like **[[CSRF (Cross-Site Request Forgery)]]**).”

### 🧠 **Input Validation: The Mandatory First Line**

Just like in general application security, all API inputs must be subjected to strict **[[Server-Side Validation]]** immediately upon receipt. This is the first and most critical defense against injection flaws.

- **Goal:** To ensure that the input is exactly what the API expects (e.g., a number is a number, a string is a maximum length, and special characters are not present where they shouldn't be).
    
- **API Injection Risks:** APIs are highly susceptible to injection attacks:
    
    - **[[SQL Injection]]** and **[[Command Injection]]** must be prevented by using **[[Parameterization]]** and **Safe APIs**, but **[[Input Validation]]** is the mandatory first filter.
        
    - **[[Broken Access Control]]** (like **[[BOLA]]**) is often triggered by invalid or malformed IDs.
        

### 💡 **Security Headers: Defending the Client**

**Security Headers** are HTTP response headers sent by the API to the client's browser, instructing the browser on how to behave securely. They are critical for preventing client-side attacks.

|**Security Header**|**Purpose**|**Defense Against**|
|---|---|---|
|**[[CORS (Cross-Origin Resource Sharing)]]** (`Access-Control-Allow-Origin`)|Controls which external domains are authorized to request resources from your API.|**Cross-Origin Data Leaks**|
|**[[CSRF (Cross-Site Request Forgery)]]** Token|A unique, secret, and unpredictable token included in every state-changing request.|**[[CSRF (Cross-Site Request Forgery)]]**|
|**HSTS** (`Strict-Transport-Security`)|Forces the browser to communicate only over **[[TLS Protocol]]** (HTTPS), eliminating the risk of downgrade attacks.|**Protocol Downgrade Attacks**|

### 🎯 **CSRF Defense in APIs**
![[CSRF Defense in APIs.png]]

**[[CSRF (Cross-Site Request Forgery)]]** tokens are the mandatory defense for any state-changing API method (`POST`, `PUT`, `DELETE`) that relies on a browser-managed **[[Session Token]]** (like a cookie). The server must verify that the token submitted with the request matches the expected value, proving the request originated from a trusted, authorized web page.

---

### 🧩 **Mini Quiz – Chapter 2.2**

**Q:** What is the primary purpose of the **[[CORS (Cross-Origin Resource Sharing)]]** header in an API response?

A) To enforce **[[Rate Limiting]]** against **[[Denial of Service (DoS)]]**.

B) To ensure the **[[JWT (JSON Web Token)]]** is signed with an **[[Asymmetric Encryption]]** key.

C) **To specify which external domains are permitted to interact with the API, thereby preventing unauthorized websites from making cross-origin requests.** 

D) To automatically apply **[[Parameterization]]** to the request body.

Click here to view the answer : [[Chapter 2.2 - Answer - Secure API]]

---

### 🎯 **Learning Objectives – Chapter 2.2**

By the end of this sub-chapter, you should be able to:

- Reiterate the mandatory role of **[[Server-Side Validation]]** in preventing API injection attacks.
    
- Define and explain the purpose of **Security Headers** like HSTS and **[[CORS (Cross-Origin Resource Sharing)]]**.
    
- Justify why **[[CSRF (Cross-Site Request Forgery)]]** tokens are mandatory for state-changing API methods used by web browsers.