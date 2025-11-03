This quiz contains five questions covering all material from Chapters 1.1 through 2.3.

### 🧩 **Quiz Question 1 (Symmetric vs. Asymmetric Use)**

**Q:** What is the primary advantage of **[[Symmetric Encryption]]** (e.g., AES) over **[[Asymmetric Encryption]]** (e.g., RSA), and for what purpose does the **[[TLS Protocol]]** use this advantage?

A) Advantage: Provides **[[Non-Repudiation]]**; Use: To verify the **[[X.509 Certificate]]**.

B) **Advantage: It is significantly faster for bulk data; Use: To encrypt all the application data after the key exchange.** ✅

C) Advantage: It solves the key exchange problem; Use: To initially encrypt the **[[Public Key]]**.

D) Advantage: It is one-way (irreversible); Use: To create a **[[Cryptographic Hash]]** of each packet.

Click here to view the correct answer : [[Chapter 3.0 - Answer 1 - Cryptography]]

---

### 🧩 **Quiz Question 2 (Hashing and Integrity)**

**Q:** A software developer wants to ensure that a configuration file received from an update server has not been tampered with. Which cryptographic primitive should be used, and which core property guarantees that the check is reliable?

A) Primitive: **[[Symmetric Encryption]]**; Property: Reversibility.

B) Primitive: **[[Digital Signature]]**; Property: **[[Non-Repudiation]]**.

C) **Primitive: [[Cryptographic Hash]] (e.g., SHA-256); Property: Collision Resistance.** 

D) Primitive: **[[Key Derivation Function (KDF)]]**; Property: Intentional Slowness.

Click here to view the correct answer : [[Chapter 3.0 - Answer 2 - Cryptography]]

---

### 🧩 **Quiz Question 3 (Digital Signatures)**

**Q:** What is the specific security role of the sender's **[[Private Key]]** in the creation of a **[[Digital Signature]]**?

A) It is used to encrypt the entire document to ensure **[[Confidentiality]]**.

B) It is shared with the receiver to enable the **[[Non-Repudiation]]** check.

C) **It is used to encrypt the [[Cryptographic Hash]] of the document, which only the sender could do, guaranteeing Authenticity.** 

D) It is stored in the **[[Hardware Security Module (HSM)]]** to protect **[[Data at Rest]]**.

Click here to view the correct answer : [[Chapter 3.0 - Answer 3 - Cryptography]]

---

### 🧩 **Quiz Question 4 (Key Management and Protection)**

**Q:** A company needs to protect the master key used to decrypt all customer databases (**[[Data at Rest]]**). What is the preferred, dedicated hardware solution for storing and using this key without ever exposing it in memory?

A) The **[[Session Store]]** is used to manage the key's **[[Session Timeout]]**.

B) A **[[Certificate Authority (CA)]]** is used to issue the key a public identity.

C) A **[[Key Derivation Function (KDF)]]** is used to intentionally slow down key access.

D) **A [[Hardware Security Module (HSM)]] is used to store the key in tamper-proof hardware, enforcing key access control.** 

Click here to view the correct answer : [[Chapter 3.0 - Answer 4 - Cryptography]]

---

### 🧩 **Quiz Question 5 (Hashing for Passwords)**

**Q:** Why is the use of a unique, per-user **[[Salt]]** mandatory when storing a **[[Password Hash]]**, even when using a strong **[[Key Derivation Function (KDF)]]** like Argon2?

A) To prevent the **[[Salt]]** from being exposed in the **[[X.509 Certificate]]**.

B) To enable the use of **[[Asymmetric Encryption]]** during the user's next login attempt.

C) **To prevent mass, pre-computed [[Rainbow Table]] attacks by ensuring identical passwords result in unique hashes.** 

D) To increase the speed and efficiency of the password verification process.

Click here to view the correct answer : [[Chapter 3.0 - Answer 5 - Cryptography]]

---

This concludes the **Cryptography and Data Protection** module. You've demonstrated a strong command of the core cryptographic tools and their applications in securing both **Data in Transit** and **Data at Rest**.