### 🧠 **Definition and Mechanism 🎣**

**Cross-Site Request Forgery (CSRF)** is an attack that tricks a user's web browser into executing an unwanted action on a web application where they are currently authenticated.

- **Mechanism:** An attacker crafts a malicious link or image on a third-party site. When the victim (who is logged into the vulnerable application) visits the malicious page, their browser automatically sends a request to the vulnerable application, including the user's **[[HTTP Cookie]]** (which contains their **[[Session Token]]**). The server accepts the request as legitimate since the token is valid.
    
- **Impact:** The attacker can force the victim to execute state-changing actions, such as changing their password, transferring funds, or making purchases.
    
- **Mitigation:** The primary defense is the use of **CSRF Tokens** (a secret, unpredictable value included in forms) and setting the `SameSite` attribute on **[[HTTP Cookie]]**s.