### 🧠 **Definition and Risk 🔗**

A **Supply Chain Attack** targets the software development process by compromising a trusted third-party component, dependency, or update mechanism to deliver **[[Malware]]** or a **[[Backdoor]]** to the final application.

- **Goal:** To compromise a wide range of downstream targets by attacking a single upstream source (e.g., a popular NPM package).
    
- **Impact:** A successful attack can compromise the **[[Integrity]]** of the final product and lead to **[[Information Leakage]]** or **[[Command Injection]]** on the target systems.
    
- **Defense:** Strict **[[Vulnerability Management]]**, **[[Software Composition Analysis (SCA)]]**, and restricting the execution permissions of build tools.