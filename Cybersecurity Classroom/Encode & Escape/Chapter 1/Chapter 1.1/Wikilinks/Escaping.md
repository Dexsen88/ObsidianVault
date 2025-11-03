### 🧠 **Definition and Purpose 🛑**

**Escaping** (often used synonymously with **[[Contextual Output Encoding]]** in security) is the technique of transforming special characters within a data string so that they are treated as literal data rather than commands by a specific interpreter (e.g., a browser, a SQL database, a command shell).

- **Goal:** To prevent injection attacks like **[[XSS]]** or **[[SQL Injection]]** by destroying the special meaning of characters that could break out of the intended data context.
    
- **Mechanism:** It replaces dangerous meta-characters (like `<`, `&`, or `'`) with a safe representation specific to the target context (e.g., `&lt;` for HTML, `\'` for SQL).