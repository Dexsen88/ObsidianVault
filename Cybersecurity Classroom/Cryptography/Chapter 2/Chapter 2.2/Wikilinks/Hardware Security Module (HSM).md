### 🧠 **Definition and Mechanism 🛡️**

A **Hardware Security Module (HSM)** is a physical, tamper-resistant computing device designed specifically to secure cryptographic keys and perform cryptographic operations within its hardware boundary.

- **Goal:** To provide the highest level of protection for the most sensitive secrets (e.g., the root **[[Private Key]]** for a CA or a master encryption key).
    
- **Security Benefit:** The **[[Private Key]]** or master key is generated and stored _inside_ the HSM and is never permitted to leave. The HSM only exports the encrypted data or the **[[Digital Signature]]**, not the key itself.
    
- **Assurance:** HSMs provide a strong guarantee of **[[Confidentiality]]** and **[[Integrity]]** for the master key, making them mandatory for high-security applications like banking and payment processing.