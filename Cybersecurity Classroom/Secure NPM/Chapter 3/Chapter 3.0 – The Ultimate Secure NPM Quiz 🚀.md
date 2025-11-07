This quiz contains five questions covering all material from Chapters 1.1 through 2.3.

### 🧩 **Quiz Question 1 (Supply Chain Defense)**

**Q:** What two purposes does the cryptographic hash recorded in the **`package-lock.json`** file serve, making it a critical defense against **[[Supply Chain Attack]]**s?

A) It ensures the build uses the public registry and disables **[[CSRF (Cross-Site Request Forgery)]]**.

B) **It guarantees [[Determinism (Dependency)]] across environments and verifies the [[Integrity]] of the downloaded package file before execution.** 

C) It automatically runs **[[Software Composition Analysis (SCA)]]** and applies **[[Parameterization]]**.

D) It enforces **[[Rate Limiting]]** and uses **[[Data Encryption]]**.

Click here to view the answer : [[Chapter 3.0 - Answer 1 - Secure NPM]]

---

### 🧩 **Quiz Question 2 (Least Privilege for Secrets)**

**Q:** A CI/CD pipeline needs an NPM **registry token** to **publish** a new package. What is the mandatory security configuration for this token's permissions and storage location?

A) Permissions: Read-only; Storage: Encrypted on the build server's local disk.

B) Permissions: Full Admin; Storage: As a secure environment variable in the Git repository.

C) **Permissions: Publish-only; Storage: Managed by a dedicated [[Key Management System (KMS)]] and injected at runtime.** 

D) Permissions: Read/Write; Storage: Hardcoded in the project's `.npmrc` file.

Click here to view the answer : [[Chapter 3.0 - Answer 2 - Secure NPM]]

---

### 🧩 **Quiz Question 3 (Runtime Safety)**

**Q:** Why is running **`npm install`** with the **`--ignore-scripts`** flag a critical security control, especially in automated build environments?

A) It prevents the installation of **deprecated** packages.

B) **It blocks the execution of malicious `preinstall` or `postinstall` scripts that could perform [[Command Injection]] or install [[Malware]] on the build server.** 

C) It forces the use of **Pinning (Dependency)** in the `package.json` file.

D) It enables **Network Segmentation** for the build server.

Click here to view the answer : [[Chapter 3.0 - Answer 3 - Secure NPM]]

---

### 🧩 **Quiz Question 4 (Mitigating Dependency Confusion)**

**Q:** An organization maintains a mix of private and public NPM packages. To prevent a **[[Dependency Confusion]]** attack, what mandatory configuration setting must be enforced?

A) Enforcing the use of **[[Stored Procedures]]** for all package lookups.

B) **Configuring NPM scopes (e.g., `@org`) in the `.npmrc` file to explicitly route private package requests to the trusted private registry.** 

C) Using the `npm audit fix` command with the `--force` flag.

D) Disabling **[[Data Masking]]** in the build output.

Click here to view the answer : [[Chapter 3.0 - Answer 4 - Secure NPM]]

---

### 🧩 **Quiz Question 5 (Security Debt Management)**

**Q:** Which automated tool and corresponding action are mandatory for identifying and resolving **Security Debt** related to unsupported code, such as packages that are **deprecated** or contain known flaws?

A) Tool: Git; Action: Commit the `package-lock.json` file.

B) Tool: **`npm ci`**; Action: Use **Pinning (Dependency)** on all versions.

C) **Tool: [[Software Composition Analysis (SCA)]] (e.g., `npm audit`); Action: Replace deprecated packages and fail the build on critical vulnerabilities.** 

D) Tool: **[[Key Management System (KMS)]]**; Action: Rotate the registry token frequently.

Click here to view the answer : [[Chapter 3.0 - Answer 5 - Secure NPM]]
