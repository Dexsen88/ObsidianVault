### 🧠 **Definition and Purpose 🔐**

**Data Encryption** is the process of translating data (plaintext) into a secret code (ciphertext) using a cryptographic algorithm and a key, making the data unreadable to anyone without the correct decryption key.

- **Goal:** To enforce **[[Confidentiality]]** for data at rest (stored in the database) and data in transit (**[[TLS Protocol]]**). If the database files are stolen, they are useless without the key.
    
- **Mechanisms:**
    
    - **Encryption at Rest:** Securing the data on the storage medium (e.g., using **TDE - Transparent Data Encryption** or **Column-Level Encryption**).
        
    - **Encryption in Transit:** Securing the connection between the application and the database (mandatory use of **[[TLS Protocol]]**).
        
- **Mandate:** Encryption keys must be managed by a secure **[[Key Management System (KMS)]]**. Strong, current encryption standards are mandatory for all **[[Personally Identifiable Information (PII)]]** and sensitive financial data.