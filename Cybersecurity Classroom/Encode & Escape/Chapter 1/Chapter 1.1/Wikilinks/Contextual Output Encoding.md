### 🧠 **Definition and Mechanism 📐**

**Contextual Output Encoding** is the mandatory security control that involves applying a specific escaping scheme to data immediately before it is rendered or executed, based on the _exact_ context in which the data will be used.

- **Goal:** To implement the **[[Escaping]]** principle effectively and prevent any form of code injection.
    
- **The Mandate:** You must use the correct encoding library for the specific context: HTML Entity Encoding for an HTML body, JavaScript String Escaping for a `<script>` block, and URL Encoding for query parameters.
    
- **Vulnerability:** Failure to use this technique, or using the wrong type of encoding for the context, is the root cause of most injection flaws, as demonstrated by the **[[XSS]]** attack.