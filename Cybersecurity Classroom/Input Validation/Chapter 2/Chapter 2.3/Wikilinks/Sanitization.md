### 🧠 **Definition and Mechanism ✨**

**Sanitization** is the process of actively modifying input data to make it safe by transforming or removing malicious or unwanted elements. It occurs _after_ the initial **Input Validation** confirms the data is generally acceptable.

- **Goal:** To allow slightly more flexible input (like formatted text) while ensuring strict safety. Sanitization cleans the data to protect the **[[Integrity]]** of the system.
    
- **Difference from Validation:**
    
    - **Validation** asks: "Is this input acceptable? (Yes/No)"
        
    - **Sanitization** asks: "How can I safely clean this input? (Modify/Remove)"
        
- **Example:** For a comment field that allows basic formatting tags, sanitization would strip out all unsafe HTML tags like `<script>` or `<iframe >` but leave safe tags like `<b>` or `<i>`. The input is made safe for storage or display without causing **[[XSS]]** vulnerabilities.