**🌟 Aisha’s Display Blunder**
![[Aisha's Display Blunder.png]]
Aisha created a user profile page that displayed a user's chosen nickname. A security researcher set their nickname to <script>alert(1)</script>. When Aisha viewed the profile, the script executed, showing the alert box.

Elena: “This happened because you failed to apply **[[Contextual Output Encoding]]**. The browser interpreted a piece of user data as executable code because you didn't tell it, 'Hey, this is just text, not an HTML tag.' Security is all about managing **Trust Boundaries** and treating all user input as malicious until proven otherwise.”

### 🧠 **The Trust Boundary**

A **[[Trust Boundary]]** is a conceptual border where the security properties or the level of trust changes. All data moving _across_ a trust boundary must be treated as untrusted and subjected to strict security checks.

- **Common Boundary:** The most critical boundary is between the **user** (client-side) and the **application** (server-side).
    
- **The Rule:** Data sourced from one side (e.g., a user's nickname) must be secured before being processed or rendered on the other side. This is the **[[Never Trust User Input]]** principle.
    

### 💡 **Encoding vs. Escaping**

The two core defenses against interpreting data as code are **Encoding** and **Escaping**.

| **Technique**    | **Primary Goal**         | **Mechanism**                                                                                      | **Example (HTML Context)**             |
| ---------------- | ------------------------ | -------------------------------------------------------------------------------------------------- | -------------------------------------- |
| **[[Encoding]]** | **Data Representation**  | Converts special characters into a different format so they can be stored or transmitted reliably. | Converting a space to `%20` for a URL. |
| **[[Escaping]]** | **Injection Prevention** | Converts special characters into a literal, safe format specific to the _interpreter's context_.   | Converting `<` to `&lt;` in HTML.      |

In web security (preventing **[[XSS]]**), we mostly use **[[Contextual Output Encoding]]** (or escaping) to change the meaning of characters that would otherwise be interpreted as code.

### 🎯 **Contextual Output Encoding (Escaping)**
![[Contextual Output Encoding.png]]

**[[Contextual Output Encoding]]** is the mandatory process of transforming special characters in data so that they cannot break out of the intended data context and inject executable code.

- **Example:** To safely render a user input string in an HTML body, you must convert HTML-specific characters (`<`, `>`, `&`, `"`, `'`) into their HTML entities (`&lt;`, `&gt;`, `&amp;`, `&quot;`, `&#x27;`). Failure to do this causes **[XSS]]**.
    
- **The Rule:** The type of escaping applied **MUST** match the output context (HTML, JavaScript, SQL, URL). Applying HTML encoding to a string destined for a JavaScript variable is ineffective.
    

---

### 🧩 **Mini Quiz – Chapter 1.1**

**Q:** Why did Aisha's application fail when a user entered `<script>alert(1)</script>` as a nickname, and what specific action was missing?

A) The system failed **[[Authentication]]** checks; the missing action was **[[Data Sanitization]]**.

B) The system failed to enforce the **[[Trust Boundary]]**; the missing action was **[[Input Validation]]**.

C) **The browser misinterpreted the data as executable code; the missing action was [[Contextual Output Encoding]] (Escaping) for the HTML context.** ✅

D) The **[[TLS Protocol]]** failed; the missing action was **[[Symmetric Encryption]]**.

Click here to view the answer : [[Chapter 1.1 - Answer - Encode & Escape]]

---

### 🎯 **Learning Objectives – Chapter 1.1**

By the end of this sub-chapter, you should be able to:

- Define a **[[Trust Boundary]]** and explain the **[[Never Trust User Input]]** principle.
    
- Distinguish between **[[Encoding]]** (representation) and **[[Escaping]]** (injection prevention).
    
- Explain why **[[Contextual Output Encoding]]** is the primary defense against injection flaws like **[[XSS]]**.