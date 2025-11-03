### 🧠 **Definition and Purpose 🐌**

A **Key Derivation Function (KDF)** is a specialized **[[Cryptographic Hash]]** function designed to be intentionally slow and resource-intensive (consuming CPU time and memory) by performing a large number of iterative calculations.

- **Goal:** To securely derive cryptographic keys from a secret (like a password) and, critically, to protect against high-speed offline brute-force and dictionary attacks.
    
- **Defense Mechanism:** The slow nature of the function makes it computationally expensive for an attacker to test billions of passwords, even with specialized hardware (GPUs).
    
- **Standards:** Secure KDFs include **Argon2**, **bcrypt**, and **scrypt**. These are mandatory for storing user passwords, as a generic, fast hash like SHA-256 provides insufficient protection against modern cracking tools.