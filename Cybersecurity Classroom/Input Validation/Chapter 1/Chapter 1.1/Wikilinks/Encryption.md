### 🧠 **Definition and Mechanism 🔒**

**Encryption** is the process of transforming readable data (plaintext) into an unreadable form (ciphertext) using an algorithm and a key. This process is reversible via decryption, which requires the correct key.

- **Goal:** To protect **[[Confidentiality]]** of data, both when it is stored (**Data at Rest**) and when it is being transmitted (**Data in Transit**).
    
- **Types:**
    
    - **Symmetric Encryption:** Uses the same key for both encryption and decryption (e.g., AES). This is fast but requires secure key exchange.
        
    - **Asymmetric Encryption (Public-Key):** Uses a pair of keys—a public key for encryption and a private key for decryption (e.g., RSA). This is slower but solves the key exchange problem.
        
- **Key Concept:** Even if an attacker gains unauthorized access to encrypted data, they cannot read it without the cryptographic key.