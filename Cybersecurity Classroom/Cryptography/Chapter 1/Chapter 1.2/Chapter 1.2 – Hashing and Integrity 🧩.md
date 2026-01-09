🌟 Aisha’s Download Dilemma
![[Aisha's Download Dilemma.png]]

Aisha downloaded an important software update, but she worried that a hacker might have tampered with the file while it was in transit, violating the file's [[Integrity]]. She saw a 64-character string labeled "SHA-256 Hash" next to the download link.

Elena: “That string is a **[[Cryptographic Hash]]**. It’s a one-way, irreversible function that acts as a digital fingerprint for the file. By computing the hash on your downloaded file and comparing it to the official hash, you can instantly verify if the data was tampered with.”

### 🧠 **Cryptographic Hashing Fundamentals**

**[[Cryptographic Hash]]** functions (like SHA-256) are fundamentally different from **[[Encryption]]** algorithms because they are **one-way**.

|**Property**|**Description**|**Security Requirement**|
|---|---|---|
|**One-Way** (Irreversible)|It's computationally infeasible to get the input (plaintext) back from the output (hash).|Essential for secure **[[Password Hash]]** storage.|
|**Collision Resistance**|It's computationally infeasible to find two different inputs that produce the same hash output.|Essential for ensuring **[[Integrity]]** and preventing fraud.|
|**Fixed-Length Output**|No matter the size of the input, the output hash (e.g., 256 bits for SHA-256) is always the same fixed length.|Ensures efficiency and predictability.|
### 💡 **The Two Core Uses of Hashing**

1. **Integrity Check (Data Verification):** As in Aisha's case, hashing provides verifiable proof that data has not been modified. If even a single bit of the file changes, the resulting hash will change drastically. This enforces the **[[Integrity]]** pillar of the **[[CIA Triad]]**.
    
2. **Password Storage:** As covered in the **[[Authentication]]** module, hashing is mandatory for storing user passwords (creating a **[[Password Hash]]**). This maintains **[[Confidentiality]]** by ensuring the password itself is never stored in plaintext, even with the use of a unique **[[Salt]]**.
    

### 🎯 **The Difference from Encryption**
![[The DIfference From Encryption.png]]

A common confusion point is the difference between hashing and encryption:

- **[[Encryption]]** is **two-way** (reversible with a key). Its goal is **[[Confidentiality]]** (hiding the data).
    
- **[[Cryptographic Hash]]** is **one-way** (irreversible). Its goal is **[[Integrity]]** (proving the data hasn't changed).

### 🧩 **Mini Quiz – Chapter 1.2**

**Q:** Why is **[[Cryptographic Hash]]** specifically used to verify the **[[Integrity]]** of a file download, rather than a reversible **[[Symmetric Encryption]]** algorithm?

A) Symmetric Encryption is too slow for large files and requires a **[[Public Key]]**.

B) **Hashing proves the file hasn't changed without needing a secret key, and the one-way nature guarantees that an attacker cannot reverse the hash to insert malicious code.** 

C) Symmetric Encryption can be reversed by an attacker, revealing the original file content.

D) Hashing provides **[[Confidentiality]]**, which is the primary goal of the integrity check.

Click here to view the answer : [[Chapter 1.2 Answer - Cryptography]]

### 🎯 **Learning Objectives – Chapter 1.2**

By the end of this sub-chapter, you should be able to:

- Define a **[[Cryptographic Hash]]** and list its three essential properties (one-way, collision resistance, fixed length).
    
- Differentiate the goal of **hashing** (**[[Integrity]]**) from the goal of **[[Encryption]]** (**[[Confidentiality]]**).
    
- Explain the two core security applications of hashing (data verification and **[[Password Hash]]** storage).