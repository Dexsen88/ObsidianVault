### 🧠 **Definition and Mechanism ⚡️**

A **Hybrid Cryptosystem** is a practical security protocol (like **TLS/HTTPS**) that combines the best features of both **[[Symmetric Encryption]]** and **[[Asymmetric Encryption]]**.

- **Goal:** To achieve the secure key exchange of asymmetric cryptography with the high-speed data transfer of symmetric cryptography.
    
- **Mechanism:**
    
    1. **Asymmetric Phase:** The client and server use the slower **[[Public Key]]** cryptography to securely negotiate and exchange a randomly generated, single-use **[[Symmetric Key]]** (called a session key).
        
    2. **Symmetric Phase:** All subsequent bulk data is then encrypted and decrypted using the high-speed **[[Symmetric Key]]**.
        
- **Benefit:** This method protects both the key exchange and the bulk data efficiently.