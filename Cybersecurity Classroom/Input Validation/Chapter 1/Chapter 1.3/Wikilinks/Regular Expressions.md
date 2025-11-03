### 🧠 **Definition and Purpose 🔍**

**Regular Expressions (Regex)** is a sequence of characters that defines a search pattern. In the context of **[[Input Validation]]**, Regex is the primary tool used to implement **Whitelisting** by creating precise patterns that define the allowed format, character set, and length of input.

- **Goal:** To enforce strict formatting rules, ensuring the application receives **Syntactic** data that is expected and safe.
    
- **Example:** A Regex pattern for a simple 10-digit phone number strictly allows only digits (`[0-9]`) and enforces a fixed length (`{10}`). This prevents users from injecting malicious characters into the field, mitigating potential **[[SQL Injection]]** or **[[XSS]]** payloads.
    
- **Security Use:** Regex helps enforce the **[[Integrity]]** of the data by ensuring it adheres to the application's design constraints.