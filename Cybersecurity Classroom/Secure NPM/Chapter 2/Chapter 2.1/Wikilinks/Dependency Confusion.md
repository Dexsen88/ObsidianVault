### 🧠 **Definition and Mechanism 🤨**

**Dependency Confusion** is a specific type of **[[Supply Chain Attack]]** where an attacker registers a malicious package on a public registry (like NPM) using the same name as a private, internal package used by a company.

- **Goal:** To exploit package manager heuristics, which often prioritize the highest version number available, regardless of whether it's public or private. The build system pulls the malicious, higher-versioned public package instead of the intended private package.
    
- **Impact:** Leads to unauthorized code execution and **[[Information Leakage]]** from the build environment, violating **[[Integrity]]** and **[[Confidentiality]]**.
    
- **Mitigation:** Using **registry scopes** (e.g., `@mycompany/mypackage`) or dedicated configuration files (`.npmrc`) to explicitly define and prioritize trusted **private registries** over public ones.