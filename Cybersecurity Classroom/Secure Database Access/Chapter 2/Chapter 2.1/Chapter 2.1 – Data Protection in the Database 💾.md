🌟 **Aisha’s Stolen Hard Drive** 

Aisha's database server, which was protected by strong network firewalls, was physically stolen from the data center. While the thief could not log in, they now have the raw hard drive containing the database files.

Elena: “This is why application security extends beyond the network perimeter. Your **[[Defense-in-Depth]]** failed at the physical layer. The final, non-negotiable line of defense for data **[[Confidentiality]]** is **[[Data Encryption]]**. If your data at rest was encrypted, the stolen files would be useless without the keys.”

### 🧠 **Data Encryption at Rest (TDE)**

**[[Data Encryption]]** at rest is mandatory for all sensitive data (**[[Personally Identifiable Information (PII)]]**, financial data, etc.). Even if an attacker gains OS access, the raw database files will be unreadable.

- **TDE (Transparent Data Encryption):** This is the most common form of disk-level encryption.
    
    - **Mechanism:** TDE encrypts the entire database file on the storage medium. The decryption keys are managed by the database software and stored securely (often in a **[[Key Management System (KMS)]]**).
        
    - **Benefit:** The encryption/decryption process is **transparent** to the application; no code changes are required. This protects against theft of the physical files.
        
    - **Limitation:** If an attacker breaches the application server and executes **[[SQL Injection]]** against the live database, the data is decrypted in memory, so TDE alone is not enough.
        

### 💡 **Salting and Hashing Passwords**

Storing user passwords in plaintext is a catastrophic security failure. They must be secured using a strong, one-way cryptographic process.

1. **Salting:** A **Salt** is a unique, random string generated for _each individual password_.
    
2. **Hashing:** The password is combined with its unique **Salt** and run through a strong, slow-to-calculate **[[Cryptographic Hash]]** function (like Argon2 or bcrypt).
    
    - **Goal:** To prevent **Rainbow Table Attacks** (pre-calculated password lists). Because every password has a unique salt, an attacker must crack each password individually, even if two users chose the same password.
        
3. **Mandate:** The **Salt** and the **[[Cryptographic Hash]]** value are stored together in the database. When the user attempts to log in, the provided password is salted, hashed, and compared to the stored hash.
    

### 🎯 **Data Masking and Tokenization**

To protect **[[Confidentiality]]** in non-production environments, two additional controls are used:

- **[[Data Masking]]:** Used primarily in development and testing databases. Sensitive data (e.g., real names) is permanently replaced with realistic, yet fake, non-reversible data (e.g., `John Doe` becomes `Mark Smith`). This protects **[[Confidentiality]]** while maintaining application functionality for testing.
    
- **Tokenization:** Used for payment card data. A sensitive piece of data (like a credit card number) is exchanged for an irreversible, non-sensitive **Token**. The original data is stored in a separate, highly-secure vault. The application stores and uses only the **Token**, drastically reducing the risk exposure.
    

---

### 🧩 **Mini Quiz – Chapter 2.1**

**Q:** When storing user passwords, why is it mandatory to use a unique **Salt** with a strong **[[Cryptographic Hash]]** function?

A) To enforce the **[[Separation of Duties]]** between developers and DBAs.

B) **To prevent Rainbow Table attacks by ensuring that two users who choose the same password will have different unique hash values stored in the database.** 

C) To automatically apply **[[Parameterization]]** to the login query.

D) To facilitate the process of **[[Data Masking]]** in the development environment.

Click here to view the answer : [[Chapter 2.1 - Answer - Secure Database Access]]

---

### 🎯 **Learning Objectives – Chapter 2.1**

By the end of this sub-chapter, you should be able to:

- Explain the role of **TDE** in providing **[[Data Encryption]]** at rest.
    
- Describe the process of **Salting** and **Hashing** passwords and why both are necessary.
    
- Differentiate between **[[Data Masking]]** and **Tokenization** as **[[Confidentiality]]** controls.