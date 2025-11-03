🌟 **Aisha’s Persistent Problem** 
![[Pasted image 20251027142540.png]]

Aisha fixed the database issue with **[[Parameterization]]**, but the problem of the malicious nickname `<script>alert(1)</script>` was still executing on the user's browser. She realized the vulnerability wasn't in the database (**[[SQL Injection]]**), but in how the browser rendered the data.

Elena: “This is **[[Cross-Site Scripting (XSS)]]**, and it’s a failure of the **[[Trust Boundary]]** at the output stage. An attacker is injecting client-side code (usually JavaScript) into a page viewed by other users. Since the browser trusts the page source, the script runs with the user's full privileges. The only effective fix is **[[Contextual Output Encoding]]**.”

### 🧠 **Cross-Site Scripting (XSS)**

**[[Cross-Site Scripting (XSS)]]** is a vulnerability that occurs when an application includes untrusted data in an HTTP response without properly handling the browser's context.

- **Impact:** Attackers can steal the victim's **[[HTTP Cookie]]** (which holds the **[[Session Token]]**), perform unauthorized actions on the victim's behalf (**[[Session Hijacking]]**), or capture keystrokes.
    
- **Types:**
    
    - **Stored XSS:** The malicious payload is permanently stored in the application (e.g., in a database field like a nickname or comment).
        
    - **Reflected XSS:** The payload is immediately reflected back to the user in a search result or error message (e.g., from a URL parameter).
        

### 💡 **Contextual Output Encoding: The Silver Bullet**

The mandatory defense against **[[XSS]]** is **[[Contextual Output Encoding]]** (Escaping). This must be applied to _all_ non-static, user-controlled data immediately before it is written to the page.

- **HTML Context:** When writing to the main body of HTML, characters like `<` and `>` must be converted to their HTML entity equivalents (`&lt;` and `&gt;`). This ensures the browser displays the characters as text, not as the start or end of an executable HTML tag.
    
- **JavaScript Context:** If user data is written inside a JavaScript variable, the input must be escaped using a JavaScript-specific encoding scheme (e.g., converting dangerous characters to their Unicode equivalents like `\u0027` for a single quote) to prevent code execution.
    

### 🎯 **Defense in Depth for XSS**
![[Defense In Depth for XSS.png]]

A robust defense uses multiple layers:

1. **Input:** Strong **[[Input Validation]]** and, if allowing rich-text, safe **[[Sanitization]]**.
    
2. **Output (Mandatory):** Always use **[[Contextual Output Encoding]]** based on the exact place (context) the user data is placed.
    

---

### 🧩 **Mini Quiz – Chapter 2.2**

**Q:** An attacker attempts an **[[XSS]]** attack by putting malicious code into a URL parameter. When the server uses this parameter to display an error, the code runs. What type of XSS is this, and what is the mandatory first-line defense _for the output_?

A) Type: Stored XSS; Defense: **[[Parameterization]]**.

B) **Type: Reflected XSS; Defense: [[Contextual Output Encoding]] (Escaping).** 

C) Type: Stored XSS; Defense: The **[[SameSite]]** cookie attribute.

D) Type: Reflected XSS; Defense: **[[Data Minimization]]**.

Click here to view the answer : [[Chapter 2.2 - Answer - Encode & Escape]]]

---

### 🎯 **Learning Objectives – Chapter 2.2**

By the end of this sub-chapter, you should be able to:

- Define **[[Cross-Site Scripting (XSS)]]** and explain its impact (**[[Session Hijacking]]**).
    
- Distinguish between **Stored XSS** and **Reflected XSS**.
    
- Explain why **[[Contextual Output Encoding]]** is the non-negotiable defense against all forms of XSS.