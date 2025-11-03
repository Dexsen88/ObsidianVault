**🌟 Aisha’s Blocklist Frustration** 
![[Blacklist vs Whitelist.png]]
Aisha started her first validation rule by banning a list of "bad" words and characters, like `SELECT`, `DROP TABLE`, and `<script>`. She quickly found attackers bypassing it using slightly different casing (`sElEcT`) or encoding.

Elena: “Your **Blacklisting** approach is flawed because you’re trying to list everything bad, which is impossible. Attackers only need one character or encoding you missed. Instead, we must use the **Whitelisting** principle: define and permit _only_ what is good and explicitly reject everything else.”

### 🧠 **The Whitelisting Imperative**

**Whitelisting** is the mandatory strategy for any security-critical **[[Input Validation]]**. It is a proactive, defensive approach that enforces the core principle of **[[Never Trust User Input]]**.
![[Whitelisting Imperative.png]]
### 💡 **Technique 1: Regular Expressions**

The most common and flexible tool for implementing whitelisting is the **[[Regular Expressions]]** (Regex) engine. Regex allows a developer to define complex character patterns that exactly match expected input.

- **Example (Good):** A username field is expected to be 5-15 characters long and contain only alphanumeric characters.
    
    - _Regex:_ `^[a-zA-Z0-9]{5,15}$`
        
    - _Result:_ This pattern strictly allows _only_ letters and numbers within that length range, rejecting any symbols, spaces, or control characters that could facilitate **[[SQL Injection]]** or **[[XSS]]**.
        
- **Example (Bad):** Allowing any character and simply trying to block common SQL keywords.
    

### 💡 **Technique 2: Canonicalization**

Before any validation is applied, the application must perform **[[Canonicalization]]** on the input. This is a crucial step that normalizes the input to its simplest, standard form.

- **Goal:** To defeat encoding-based attacks. Attackers often use multiple forms of encoding (e.g., URL encoding, HTML entities, Unicode) to smuggle malicious characters past simple filters.
    
- **Procedure:** The input must be converted to a single, consistent character set (like UTF-8) and decoded completely before the whitelist check begins.
    
    - _Example:_ An attacker submits `%253C` (a double-encoded `<`). **[[Canonicalization]]** ensures the server decodes this down to `<` before the Regex rule rejects it. Failing to do this can lead to **[[Information Leakage]]** or an unhandled exception.
        

### 🎯 **Where to Apply**

These techniques must be applied universally: on every input, from form fields and URL parameters to HTTP headers and file metadata, and they must run on the trusted **[[Server-Side Validation]]**.

### 🧩 **Mini Quiz – Chapter 1.3**

**Q:** An attacker attempts to submit a username containing the character `<` encoded as `%253C`. Which step must occur **first** before the whitelist check to ensure this input is properly rejected?

A) **Output Encoding** to prevent browser interpretation.

B) **[[Log the Failure]]** and terminate the request.

C) **[[Canonicalization]]** to decode the input to its simplest form. 

D) Server-Side Validation to check the password field.

See the answer here : [[Chapter 1.3 Answer]]

### 🎯 **Learning Objectives – Chapter 1.3**

By the end of this sub-chapter, you should be able to:

- Explain why **Whitelisting** is mandatory and **Blacklisting** is fundamentally flawed.
    
- Use **[[Regular Expressions]]** as the core technology for implementing character and length whitelists.
    
- Understand the purpose of **[[Canonicalization]]** and why it must occur before any other validation step.