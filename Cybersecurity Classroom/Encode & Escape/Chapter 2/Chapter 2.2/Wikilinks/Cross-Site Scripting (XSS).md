### 🧠 **Definition and Vulnerability 💻**

**Cross-Site Scripting (XSS)** is an injection attack where an attacker injects client-side scripts (often JavaScript) into a legitimate web page viewed by other users. This is caused by an application including unvalidated or unescaped user-supplied data in the final HTML output.

- **Impact:** High severity, allowing the attacker to bypass the **Same-Origin Policy** and steal the victim's **[[Session Token]]** (**[[Session Hijacking]]**), capture keystrokes, or perform actions on the victim's behalf.
    
- **Types:** **Stored XSS** (payload saved to a database) and **Reflected XSS** (payload immediately returned in the response).
    
- **Mandatory Defense:** **[[Contextual Output Encoding]]** (Escaping) of all user-controlled data to prevent the browser from interpreting the input as executable code.