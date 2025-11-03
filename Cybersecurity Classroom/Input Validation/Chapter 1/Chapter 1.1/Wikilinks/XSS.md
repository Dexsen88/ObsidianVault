### 🧠 **Definition and Mechanism**

**Cross-Site Scripting (XSS)** is a client-side attack where an attacker injects malicious scripts (usually JavaScript) into a vulnerable web page. When a user loads the affected page, the script executes in the user's browser under the context of your trusted domain.

- This vulnerability typically arises from a failure to perform **[[Output Encoding]]** on user-controlled data before it is rendered to the user's HTML page.
    

### 🚨 **Impact and Mitigation**

The attacker's script runs with the same permissions as the legitimate page, allowing them to:

- **Impact:** Steal the user's **Session Cookie**, capture form data, or redirect the user to a malicious site. It primarily violates user **[[Confidentiality]]** and trust.
    
- **Mitigation:** The primary defense is **Contextual Output Encoding**—converting user input (like `<` or `>`) into a harmless display format (like `&lt;` or `&gt;`) before it is rendered by the browser.