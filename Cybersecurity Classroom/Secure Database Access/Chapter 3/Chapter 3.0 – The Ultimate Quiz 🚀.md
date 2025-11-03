This quiz contains five questions covering all material from Chapters 1.1 through 2.3.

### 🧩 **Quiz Question 1 (Injection Defense)**

**Q:** What is the single, mandatory code-level defense that ensures user-supplied input is treated only as inert data and can never be executed as part of an SQL command?

A) Using **[[Data Masking]]** in the application layer.

B) Applying **[[Cryptographic Hash]]** to the user input.

C) **Employing [[Parameterization]] (Prepared Statements) for all database queries.** 

D) Restricting the application account via **[[Separation of Duties]]**.

Click here to view the answer : [[Chapter 3.0 - Answer 1 - Secure Database Access]]

---

### 🧩 **Quiz Question 2 (Defense-in-Depth Layer)**

**Q:** If a database server's physical hard drive is stolen, which **[[Defense-in-Depth]]** control is the final, non-negotiable layer required to maintain the **[[Confidentiality]]** of the customer data?

A) **[[Separation of Duties]]** for the DBAs.

B) **[[Parameterization]]** of the stolen queries.

C) **[[Data Encryption]]** at rest (e.g., using TDE). 

D) Strict **[[Rate Limiting]]** on the login attempts.

Click here to view the answer : [[Chapter 3.0 - Answer 2 - Secure Database Access]]

---

### 🧩 **Quiz Question 3 (Administrative Control)**

**Q:** The security team requires that the account used by the web application for database access only has `SELECT`, `INSERT`, and `UPDATE` permissions on the `customers` table, but no permission to `DROP` or `ALTER` any tables. Which mandatory security principle is being enforced?

A) **[[Non-Repudiation]]**.

B) **[[Separation of Duties]]**.

C) **[[Principle of Least Privilege]]**. 

D) **[[Data Masking]]**.

Click here to view the answer : [[Chapter 3.0 - Answer 3 - Secure Database Access]]

---

### 🧩 **Quiz Question 4 (Post-Exploitation Defense)**

**Q:** An attacker compromises a low-security internal server that is on the same internal network as the database server. To prevent the attacker from connecting from the compromised server to the database, what two controls must be strictly enforced?

A) Using **[[Tokenization]]** and **[[Data Masking]]**.

B) **Network Segmentation with firewall ACLs that allow connections only from the specific application servers.** 

C) **[[Cryptographic Hash]]** for all table names and columns.

D) Implementing **[[Verbose Error Message]]** suppression and **[[Timeout]]**.

Click here to view the answer : [[Chapter 3.0 - Answer 4 - Secure Database Access]]


---

### 🧩 **Quiz Question 5 (Audit Trail Integrity)**

**Q:** What is the primary administrative goal of ensuring that the database auditing logs are immediately forwarded to a separate, immutable **[[Security Logging]]** system, and that the database admin account cannot delete these logs?

A) To enforce the use of a **[[Key Management System (KMS)]]**.

B) To apply a unique **[[Salt ]]** to every log entry.

C) **To ensure the integrity of the audit trail, thereby guaranteeing [[Non-Repudiation]] in case an attacker attempts to hide their actions.** 

D) To facilitate **[[Data Encryption]]** for **[[Personally Identifiable Information (PII)]]**.

Click here to view the answer : [[Chapter 3.0 - Answer 5 - Secure Database Access]]
