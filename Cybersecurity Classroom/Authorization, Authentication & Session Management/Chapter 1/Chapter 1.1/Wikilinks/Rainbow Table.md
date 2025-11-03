### 🧠 **Definition and Mechanism 📉**

A **Rainbow Table** is a large, pre-computed table used in cryptanalysis to reverse cryptographic hash functions, specifically to recover passwords from stolen hash lists. It stores common passwords and their corresponding **[[Password Hash]]** values.

- **Goal:** To rapidly crack millions of stolen user hashes without having to perform the resource-intensive hashing computation for every possible password in real-time.
    
- **Attack Flow:** If an attacker steals a database of user hashes, they can simply look up the stolen hash in the Rainbow Table to immediately find the original plain-text password.
    
- **Mitigation:** The primary defense against this attack is the mandatory use of a unique, random **[[Salt]]** for every user. Because the salt modifies the password before hashing, the resulting hash is not present in the attacker's generic Rainbow Table.