### 🧠 **Definition and Mechanism 🧩**

A **Cryptographic Hash** function is a mathematical algorithm that takes an arbitrary block of data (input) and returns a fixed-size, seemingly random bit string (the hash value or digest).

- **Goal:** The primary security goal is to provide proof of **[[Integrity]]**.
    
- **Key Properties:** To be considered cryptographically secure, a hash function must possess:
    
    1. **One-Way (Pre-image Resistance):** It is infeasible to determine the input from the output hash.
        
    2. **Collision Resistance:** It is infeasible to find two different inputs that produce the same output hash.
        
- **Usage:** Used for verifying file integrity, creating **[[Digital Signature]]**s, and securely storing user passwords as a **[[Password Hash]]** (in conjunction with a **[[Salt]]**).