### 🧠 **Definition and Purpose ✨**

A **Salt** is a unique, randomly generated string of data that is appended to or prepended to a user's password **before** it is hashed. The salt is stored in the database alongside the **[[Password Hash]]**.

- **Security Benefit:** It prevents **[[Rainbow Table]]** attacks and makes hashing more secure. A Rainbow Table is a pre-calculated table of common passwords and their corresponding hashes.
    
- **Mechanism:** Because the salt is unique for every user (even if they share the same password), the resulting hash is unique. This forces an attacker to crack each password individually, which drastically increases the time and computational resources required for an attack.
    
- **Requirement:** Using a strong, unique salt is mandatory for any secure password storage scheme.