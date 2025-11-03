### 🧠 **Definition and Mechanism 🎣**

**Session Hijacking** is an attack where an attacker successfully steals a valid **[[Session Token]]** belonging to another authenticated user and uses that token to impersonate the user.

- **Mechanism:** The attacker bypasses the **[[Authentication]]** step entirely because the server trusts the valid, stolen token. Common ways to steal tokens include **[[XSS]]** (if the cookie is not HttpOnly), sniffing unencrypted **HTTP Cookie** traffic, or guessing weak tokens.
    
- **Impact:** The attacker gains full access to the user's session, violating **[[Confidentiality]]** and **[[Integrity]]** as they can perform any action the user is authorized to perform (including changing passwords or transferring funds).
    
- **Mitigation:** The primary defense is enforcing **Secure Cookie Flags**, ensuring the token is cryptographically random, and implementing a strict **[[Session Timeout]]**.