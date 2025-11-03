### 🧠 **Definition and Role 🗝️**

A **Symmetric Key** (or secret key) is the single, secret value used in **[[Symmetric Encryption]]** for both the encryption of plaintext and the decryption of ciphertext.

- **Goal:** To provide fast, efficient **[[Confidentiality]]** for large volumes of data.
    
- **Security:** The entire security of the encrypted data rests entirely on the secrecy of this single key. If the key is compromised, all data encrypted with it is exposed.
    
- **Usage:** In a **[[Hybrid Cryptosystem]]** (like TLS), a temporary **Symmetric Key** is generated for each session (often called a session key) and is securely exchanged using slower **[[Asymmetric Encryption]]** before being used for bulk data transfer.