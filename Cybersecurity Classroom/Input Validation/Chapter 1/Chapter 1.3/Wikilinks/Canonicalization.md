### 🧠 **Definition and Mechanism ⚙️**

**Canonicalization** is the process of normalizing input data into its simplest, standard, or "canonical" form. This means converting the input into a single, consistent representation before any security controls, such as **[[Input Validation]]**, are applied.

- **Goal:** To defeat obfuscation techniques. Attackers often use multiple layers of encoding (e.g., URL encoding, Unicode escaping, Hex encoding) to disguise malicious characters. If the server does not fully decode the input before validating it, the malicious content can bypass the filter.
    
- **Timing:** Canonicalization must be the **first step** in the **[[Server-Side Validation]]** process, occurring immediately after the data is received.
    
- **Consequence of Failure:** Failure to perform proper canonicalization leaves the application vulnerable to attacks, directly violating the **[[Never Trust User Input]]** principle and potentially leading to **[[Information Leakage]]**.