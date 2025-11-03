### 🧠 **Definition and Mechanism 🔐**

A **Password Hash** is the result of applying a one-way cryptographic function (like Argon2, bcrypt, or scrypt) to a user's password. The resulting output (the hash) is what is stored in the database, **NOT** the plain-text password.

- **One-Way Function:** Hashing is designed to be irreversible; you cannot get the original password back from the hash.
    
- **Goal:** To protect the user's password even if the database is breached and the hash table is stolen. Since the attacker only has the hash, they cannot log in as the user. This maintains the **[[Confidentiality]]** of the password.
    
- **Process:** To verify a login, the system hashes the password provided by the user during login and compares the new hash to the stored **Password Hash**. If they match, the identity is authenticated.