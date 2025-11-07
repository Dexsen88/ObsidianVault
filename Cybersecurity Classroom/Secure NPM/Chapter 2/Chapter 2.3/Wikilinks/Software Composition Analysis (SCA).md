### 🧠 **Definition and Role 🔬**

**Software Composition Analysis (SCA)** is an automated process of identifying and inventorying all open-source and third-party components (dependencies) used in a codebase.

- **Goal:** To detect **known vulnerabilities**, license compliance issues, and general security risks within the dependency graph. SCA is mandatory for modern **[[Vulnerability Management]]** programs.
    
- **Mechanism:** SCA tools read the project's manifest files (`package.json`, `package-lock.json`) and compare the component versions against a regularly updated database of known security flaws (like the NPM registry or NVD). They also report on **deprecation** and **licensing**.
    
- **Mandate:** SCA tools should be integrated into the CI/CD pipeline to provide continuous, real-time auditing and block builds containing critical vulnerabilities or non-compliant licenses.