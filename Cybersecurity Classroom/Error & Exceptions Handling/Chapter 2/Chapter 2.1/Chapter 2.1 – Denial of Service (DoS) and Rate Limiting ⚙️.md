🌟 **Aisha’s Crashed Server**
![[Aisha's Crashed Server.png]]
Aisha’s login page was slow. An attacker wrote a simple script that attempted 100 login attempts per second against a single user account. The server’s CPU usage spiked to 100%, and it stopped responding to legitimate users, causing a complete business outage.

Elena: "That's a classic **[[Denial of Service (DoS)]]** attack, specifically a resource exhaustion attack. It was enabled because you failed to implement **[[Rate Limiting]]**. Secure error handling isn't just about _what_ the server says; it's also about controlling _how many_ requests it processes before failing or responding slowly."

### 🧠 **Denial of Service (DoS)**

A **[[Denial of Service (DoS)]]** attack is any attempt to make a machine or network resource unavailable to its intended users. This violates the **[[Availability]]** pillar of the **[[CIA Triad]]**.

- **Goal:** To consume all available resources (CPU, memory, database connections, bandwidth) so that the system cannot respond to legitimate requests.
    
- **Vulnerability:** Often results from allowing an attacker to trigger an expensive, resource-intensive process (like a complex database query or repeated authentication failures) without restriction. This is amplified by the **[[Information Leakage]]** from **[[Verbose Error Message]]**s, which can guide the attacker.
    

### 💡 **Rate Limiting: The Availability Control**

**[[Rate Limiting]]** is a mandatory defensive control that restricts the number of times a user, IP address, or application endpoint can be accessed within a specific time window.

- **Goal:** To prevent abuse, block brute-force attacks against **[[Authentication]]**, and protect against **[[Denial of Service (DoS)]]** by throttling excessive traffic.
    
- **Mechanism:** When a limit is exceeded (e.g., 5 failed login attempts in 60 seconds), the system should respond with a safe HTTP status code (e.g., 429 Too Many Requests) and temporarily block the client.
    
- **Integration:** The failure condition (too many attempts) is often caught by a **[[Custom Exceptions]]** object (e.g., `RateLimitExceededException`), which triggers the throttle mechanism and ensures a secure, **[[Fail-Safe Defaults]]** response is returned.
    

### 🎯 **Account Lockout vs. Rate Limiting**
![[Account Lockout vs. Rate Limiting.png]]

While related, **Account Lockout** (permanently blocking an account after a set number of failed attempts) is a defense against brute-force attacks, whereas **[[Rate Limiting]]** is primarily a defense against **[[Denial of Service (DoS)]]** that protects the _server's resources_ and all _other_ users. Both are necessary security controls.

---

### 🧩 **Mini Quiz – Chapter 2.1**

**Q:** When an application detects 100 failed login attempts from a single IP address in one minute, which security principle is being violated, and what is the primary defensive control that should be enforced?

A) Principle Violated: **[[Confidentiality]]**; Defense: **[[Parameterization]]**.

B) Principle Violated: **[[Data Protection]]**; Defense: **[[Data Minimization]]**.

C) **Principle Violated: [[Availability]]; Defense: [[Rate Limiting]] (to throttle and block the source IP).** 

D) Principle Violated: **[[Integrity]]**; Defense: **[[Digital Signature]]**.

Click here to view the answer : [[Chapter 2.1 - Answer - Error & Exceptions Handling]]

---

### 🎯 **Learning Objectives – Chapter 2.1**

By the end of this sub-chapter, you should be able to:

- Define **[[Denial of Service (DoS)]]** and explain how it violates the **[[Availability]]** pillar.
    
- Define **[[Rate Limiting]]** and justify its use as the mandatory defense against resource exhaustion attacks.
    
- Differentiate between **[[Rate Limiting]]** and **Account Lockout**.