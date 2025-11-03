🌟 Aisha’s Compromised Passwords
![[Aisha's Compromised Passwords.png]]

Aisha's database was breached, and the attackers stole the entire table of user passwords, which were stored as **[[Password Hash]]**es using the SHA-256 algorithm. The attackers immediately used a pre-computed list to crack 80% of the accounts instantly.

Elena: "The core failure here was not the hashing algorithm, but the failure to use a **[[Salt]]**. Without a unique, random salt for every user, even strong hashing is vulnerable to fast, large-scale brute-force attacks like the **[[Rainbow Table]]** attack."

### 🧠 **Attacks Against Hashing**

While **[[Cryptographic Hash]]** functions are one-way, they are susceptible to brute-force attacks that attempt to guess the original input (the password) by hashing millions of common words and checking for a match against the stolen hashes.

|**Attack Name**|**Mechanism**|**Defense**|
|---|---|---|
|**[[Rainbow Table]]**|Attackers use a pre-computed table of hashes for common passwords.|**[[Salt]]** (Unique random value added to password before hashing).|
|**Dictionary Attack**|Attacker hashes words from a list (dictionary) one by one and compares the result to the target hash.|**[[Salt]]** and **Key Derivation Function (KDF)**.|
|**Brute-Force Attack**|Attacker systematically tries every possible character combination.|**[[Key Derivation Function (KDF)]]** (Making the hash slow) and rate limiting.|

### 💡 **The Importance of Salting**
![[Importance Of Salting.png]]

As we learned in **[[Authentication]]**, a **[[Salt]]** is a unique, random value generated for each user and stored alongside their **[[Password Hash]]**.

- **Why it Works:** The salt ensures that if two users choose the same password (e.g., "password123"), their final **[[Password Hash]]**es are different. This forces the attacker to generate a separate **[[Rainbow Table]]** for _every single salt value_, which is computationally infeasible.
    

### 🎯 **Key Derivation Functions (KDFs)**

The process of hashing a password must be intentionally slowed down to defend against offline brute-force attacks. **[[Key Derivation Function (KDF)]]**s are specialized hash functions designed to be computationally expensive (slow) through iterative hashing and memory use.

- **Standards:** Algorithms like **Argon2** (the winner of the Password Hashing Competition), **bcrypt**, and **scrypt** are preferred over generic hash algorithms like SHA-256 for passwords.
    
- **Defense:** A slow **KDF** ensures that while verifying one user's password takes a server milliseconds, an attacker trying to crack a million passwords takes years, effectively making a brute-force attack impractical.
    
### 🧩 **Mini Quiz – Chapter 2.3**

**Q:** Why is a generic **[[Cryptographic Hash]]** algorithm like SHA-256 insufficient for password storage, even when properly salted, and what is the preferred alternative?

A) SHA-256 is not one-way; the alternative is **[[Symmetric Encryption]]**.

B) SHA-256 does not generate a fixed-length output; the alternative is **[[X.509 Certificate]]**.

C) **SHA-256 is too fast, making offline brute-force attacks practical; the alternative is a slow, iterative [[Key Derivation Function (KDF)]] like Argon2 or bcrypt.** ✅

D) SHA-256 is vulnerable to **[[Cross-Site Request Forgery (CSRF)]]**; the alternative is the **[[SameSite]]** flag.

Click here to view the answer : [[Chapter 2.3 - Answer - Cryptography]]

### 🎯 **Learning Objectives – Chapter 2.3**

By the end of this sub-chapter, you should be able to:

- Identify the primary attacks against password hashes: **[[Rainbow Table]]** and brute-force attacks.
    
- Explain how the **[[Salt]]** provides defense against mass, pre-computed attacks.
    
- Define and justify the use of a **[[Key Derivation Function (KDF)]]** for secure password storage.