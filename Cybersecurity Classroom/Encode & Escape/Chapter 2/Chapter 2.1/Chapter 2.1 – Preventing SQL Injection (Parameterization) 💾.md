
🌟 **Aisha’s Database Breach**
![[Aisha's Databse Breach.png]]
Aisha wrote a login query like this: `SELECT * FROM users WHERE username = '` + _userInput_ + `' AND password = '` + _userPass_ + `'`. An attacker entered a username like `' OR '1'='1` in the input field. The resulting query became `SELECT * FROM users WHERE username = '' OR '1'='1' AND password = '...'`, which allowed them to log in without a password.

Elena: “That’s a classic **[[SQL Injection]]** attack. You failed to separate the _data_ from the _code_. The database interpreter saw the user's input not as a username string, but as a new SQL command. The only mandatory defense here is **[[Parameterization]]**.”

### 🧠 **SQL Injection (SQLi)**

**[[SQL Injection]]** (SQLi) is an injection attack that occurs when an attacker can interfere with the queries that an application makes to its database. This generally allows an attacker to view, modify, or delete data they are not authorized to access, violating **[[Confidentiality]]** and **[[Integrity]]**.

- **Root Cause:** Building dynamic queries by concatenating user-supplied input directly into the SQL command string.
    
- **Defense Failure:** The application fails to apply the necessary **[[Escaping]]** (or equivalent control) for the database context.
    

### 💡 **Parameterization: The Mandatory Defense**

**[[Parameterization]]** (also called prepared statements) is the only reliable and mandatory defense against **[[SQL Injection]]**. It structurally separates the SQL command from the user-supplied data.

- **Mechanism:** The application defines the structure of the SQL query first, sending it to the database with placeholders (like `?` or `:name`) where user data will go. Then, the user data is sent separately.
    
- **Database Interpretation:** The database engine treats everything sent as user data in the second step _only_ as literal data values, **never** as executable SQL code, regardless of whether the data contains dangerous characters like `'` or `--`.
    

### 🎯 **Avoiding SQL Escaping**
![[Avoiding SQL Escaping.png]]

While it is technically possible to prevent SQLi by manually **[[Escaping]]** single quotes in user input (e.g., changing `'` to `\'`), this is highly error-prone and considered a weak defense. **[[Parameterization]]** is superior because it fixes the structural vulnerability, making manual escaping unnecessary. The combination of **[[Input Validation]]** (to check length/type) and **[[Parameterization]]** (to prevent code injection) is the gold standard.

---

### 🧩 **Mini Quiz – Chapter 2.1**

**Q:** Why does **[[Parameterization]]** effectively prevent **[[SQL Injection]]** attacks?

A) Because it forces the user to apply **[[Contextual Output Encoding]]** before sending the data.

B) Because it slows down the query execution using a **[[Key Derivation Function (KDF)]]**.

C) **Because it separates the structure of the SQL command from the user-supplied data, ensuring the database treats the input as literal data and never as executable code.** 

D) Because it is a form of **[[Sanitization]]** that removes all dangerous SQL keywords from the input.

Click here to view the answer : [[Chapter 2.1 - Answer - Encode & Escape]]

---

### 🎯 **Learning Objectives – Chapter 2.1**

By the end of this sub-chapter, you should be able to:

- Define **[[SQL Injection]]** and identify its root cause.
    
- Define **[[Parameterization]]** and explain why it is the mandatory defense against SQLi.
    
- Understand the security principle of separating code (query structure) from data (user input).