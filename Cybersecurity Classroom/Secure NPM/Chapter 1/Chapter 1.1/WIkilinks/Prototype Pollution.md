### 🧠 **Definition and Risk 💉**

**Prototype Pollution** is a **[[Vulnerability]]** unique to JavaScript/Node.js where an attacker can inject or modify properties into the base object prototype (`Object.prototype`). Since all objects in JavaScript inherit properties and methods from this prototype, an injection here affects **all** objects globally.

- **Goal:** To inject properties that can be used to bypass **[[Authorization]]** checks (e.g., adding `isAdmin: true` to the prototype) or, more dangerously, to execute arbitrary code (**[[Command Injection]]** style) if the application uses certain library functions unsafely.
    
- **Vulnerability:** Occurs when libraries or application code recursively merges objects using unsafe functions that do not adequately check if the input key is `__proto__` or `constructor.prototype`.
    
- **Impact:** A severe **[[Integrity]]** and **[[Confidentiality]]** risk, as it allows for large-scale application logic tampering or Remote Code Execution (RCE).
    
- **Mitigation:** **Input Validation** that blocks reserved properties (`__proto__`, `constructor`, `prototype`) and using safe, modern functions for object merging.