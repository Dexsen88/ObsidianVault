### 🧠 **Definition and Principle 🛡️**

**Input Validation** is the practice of ensuring that data received from an external source is correct, clean, and safe before the application processes or stores it.

- **Core Principle:** **[[Never Trust User Input]]**. All input from users, files, or APIs is assumed to be hostile until proven otherwise.
    
- **Primary Defense:** It is the **First Line of Defense** against the vast majority of web vulnerabilities, including **[[SQL Injection]]** and **[[XSS]]**.
    
- **Layers of Validation:**
    
    - **Syntactic:** Checks format, type, and length (e.g., ensuring a date is in YYYY-MM-DD format).
        
    - **Semantic:** Checks context and business logic (e.g., ensuring a price is positive).
        
- **Mitigation:** Must always be performed on the **Server-Side Validation** using **Whitelisting** rules.