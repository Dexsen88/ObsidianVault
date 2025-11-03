🌟 **Aisha’s First Secure Input** 
![[Aisha's FIrst Secure Input.png]]
Aisha needed to validate three core input fields: a numeric User ID, a customer's name, and a specific six-character product code. She knew she had to use **[[Regular Expressions]]** and the **[[Canonicalization]]** process on the **[[Server-Side Validation]]**.

Elena: “Good. Now we apply the **Whitelisting** principle to different data types. For security and stability, every input must be checked against its expected **data type**, **format**, and **length**.”

### 🧠 **Example 1: Numeric Whitelisting**

For any input expected to be a number (like a User ID, price, or quantity), the whitelist must be the most restrictive.

- **Allowed Characters:** Only digits (0-9).
    
- **Regex:** `^[0-9]+$`
    
- **Security:** This pattern **disallows** the comma (`,`), decimal point (`.`), plus (`+`), and minus (`-`) symbols, unless they are specifically expected for a formatted currency field. By strictly allowing only digits, you prevent almost all forms of attack that rely on breaking the data structure.
    

### 💡 **Example 2: Text/Alphanumeric Whitelisting**

Text fields (like names, addresses, or short descriptions) require a balanced approach to be usable while still being secure.

- **Allowed Characters:** Basic letters, numbers, and very few, safe symbols (like a hyphen, space, or apostrophe).
    
- **Regex:** `^[a-zA-Z0-9\s\-\']{1,100}$` (Letters, numbers, spaces, hyphens, and apostrophes, 1-100 characters long).
    
- **Concept: Input Length Limit.** Every text field must have a secure, fixed maximum length. An excessively long string could trigger a **[[Denial of Service (DoS)]]** attack by overwhelming system memory or database row capacity.
    

### 💡 **Example 3: File Path Whitelisting**

When an application accepts input that represents a file or directory name, it becomes vulnerable to a **[[Path Traversal]]** attack, where an attacker tries to access files outside the intended directory using sequences like `../` (dot-dot-slash).

- **Allowed Characters:** Restrict to alphanumeric characters, hyphens, and underscores. **Explicitly forbid** periods (`.`), forward slashes (`/`), and backslashes (`\`) unless the specific context absolutely requires it.
    
- **Security:** After whitelisting, always use a **[[Principle of Least Privilege]]** approach: ensure the application process only has read/write permissions for the single directory it needs, preventing access to critical system files.

### 🧩 **Mini Quiz – Chapter 2.1**

**Q:** What is the primary security risk of defining a maximum length for a text input field as "10,000 characters (Very large)"?

A) It can lead to an **[[SQL Injection]]** if the database encoding is mismatched.

B) It allows an attacker to conduct a [[Denial of Service (DoS)]] attack by overwhelming the server or database with excessive memory allocation. 

C) It complicates the **[[Canonicalization]]** process.

D) It violates the **[[Confidentiality]]** of the user data.

Click here to view the answer : [[Chapter 2.1 - Answer]]

### 🎯 **Learning Objectives – Chapter 2.1**

By the end of this sub-chapter, you should be able to:

- Apply specific **[[Regular Expressions]]** to enforce **Syntactic** whitelisting for numeric and text data.
    
- Understand why limiting input length is a key defense against **[[Denial of Service (DoS)]]** attacks.
    
- Identify and defend against the security vulnerability of **[[Path Traversal]]** using strict whitelisting and the **[[Principle of Least Privilege]]**.