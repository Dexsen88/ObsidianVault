### 🧠 **Definition and Mechanism ✍️**

A **Digital Signature** is a mathematical scheme for proving the authenticity, **[[Integrity]]**, and non-repudiation of a digital message or document. It is the cryptographic equivalent of a handwritten signature.

- **Goal:** To ensure two key security properties:
    
    1. **Authenticity:** Proves the sender's identity.
        
    2. **Non-Repudiation:** Prevents the sender from falsely denying they sent the message.
        
- **Mechanism (Creation):** The sender uses their **[[Private Key]]** to encrypt a **[[Cryptographic Hash]]** of the message.
    
- **Mechanism (Verification):** The receiver uses the sender's openly available **[[Public Key]]** to decrypt the hash and then compares it to the hash they compute themselves from the received message. If the two hashes match, the message is authentic and has not been tampered with.