### 🧠 **Definition and Purpose 🐌**

**Rate Limiting** is a defensive technique that restricts the number of requests a user, client, or specific network endpoint can make to an application within a defined time period.

- **Goal:** To protect the application's resources from abuse and exhaustion, thereby maintaining **[[Availability]]** and preventing **[[Denial of Service (DoS)]]** attacks. It also serves as a strong defense against brute-force attacks.
    
- **Mechanism:** When a request limit is surpassed, the system throttles the client by delaying responses or outright blocking future requests, typically returning a 429 (Too Many Requests) HTTP status code.
    
- **Integration:** Must be implemented on the **[[Server-Side Validation]]** across all resource-intensive or security-sensitive endpoints (like login, password reset, or search APIs).