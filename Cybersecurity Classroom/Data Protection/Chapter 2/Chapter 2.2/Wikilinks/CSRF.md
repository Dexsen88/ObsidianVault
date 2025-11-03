### 🧠 **Definition and Mechanism 🎣**

**Cross-Site Request Forgery (CSRF)** is an attack that tricks a user's web browser into executing an unwanted action on a web application where they are currently authenticated.

- **Mechanism:** An attacker crafts a malicious request on a third-party site. When the victim (who is logged into the vulnerable application) visits the malicious page, their browser automatically sends the request to the target application, including the user's **[[HTTP Cookie]]** (which contains their **[[Session Token]]**). The server accepts the request as legitimate since the token is valid.
    
- **Impact:** The attacker can force the victim to execute state-changing actions, such as changing their password, transferring funds, or making purchases, violating **[[Integrity]]** and **[[Confidentiality]]**.
    
- **Mitigation:** The primary defenses are the use of a secret, unpredictable **[[CSRF Token]]** in all state-changing requests and setting the **[[SameSite]]** attribute on **[[HTTP Cookie]]**s.