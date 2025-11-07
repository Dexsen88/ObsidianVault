🌟 **Aisha’s Build Server RCE** 
![[Aisha's Build Server RCE.png]]
Aisha's team installed a package that included a malicious post-install script. When the developer ran `npm install`, the script executed with the developer's elevated user permissions on their local machine, automatically downloading an external binary and installing a **[[Backdoor]]**.

Elena: “That’s a **Malicious Script Execution** failure. When you run `npm install`, you grant execution power to unknown code. You must minimize the risk by disabling unnecessary scripts and strictly applying the **[[Principle of Least Privilege]]** to the environment where the code runs, preventing **Remote Code Execution (RCE)**.”

### 🧠 **Disabling Install Scripts**

NPM allows packages to include scripts that run automatically during the installation process (`preinstall`, `install`, `postinstall`). These are a common vector for **[[Supply Chain Attack]]**s, allowing malicious code to execute on the build or development machine.

- **Risk:** A malicious script can perform arbitrary actions, such as installing **[[Malware]]**, stealing environment variables, or initiating **[[Information Leakage]]** to a remote **[[Command-and-Control (C2)]]** server.
    
- **Defense Mandate:**
    
    - **Disable Scripts:** Use the configuration setting `ignore-scripts=true` in your **`.npmrc`** file or run installation with `npm install --ignore-scripts` in CI/CD environments where possible.
        
    - **Manual Review:** Only enable scripts for the few, necessary, and thoroughly audited internal packages.
        

### 💡 **Principle of Least Privilege for Build Systems**

The security of your **build environment** (where packages are installed and compiled) is paramount, as a breach here can contaminate the final product.

- **Isolated Accounts:** The user account running `npm install` (especially in CI/CD) should be a dedicated, non-human, **low-privilege** service account.
    
- **Network Restriction:** The build server should be isolated via **Network Segmentation** and only allowed to communicate with authorized sources (e.g., the package registry, internal Git, and the **[[Key Management System (KMS)]]**). It should be blocked from communicating with external, random **[[Command-and-Control (C2)]]** IPs.
    
- **Read-Only Filesystem:** Where possible, the build account should only have read-only access to the filesystem, except for the dedicated build workspace, to prevent the **[[Malware]]** from gaining persistent system access or performing unauthorized **[[Lateral Movement]]**.
    

### 🎯 **Secure Runtime Configuration**
![[Secure Runtime Configuration.png]]

Even after installation, the production Node.js process itself must be secured:

- **Read-Only Process:** Configure the production Node.js application to run with a non-root user that has read-only access to the deployment folder and only write access to necessary directories (like logs or uploads). This enforces the **[[Principle of Least Privilege]]** at runtime.
    
- **Environment Variables:** Do not store sensitive secrets (like production database passwords) directly in local files; inject them as environment variables and ensure the server's OS is hardened to prevent unauthorized reading of process memory.
    

---

### 🧩 **Mini Quiz – Chapter 2.2**

**Q:** An attacker places a malicious script in a dependency's `postinstall` hook. What two security controls could prevent this script from causing damage when a developer runs `npm install` on their local machine?

A) **[[Data Encryption]]** and enforcing **[[Separation of Duties]]**.

B) **Running `npm install` with the `--ignore-scripts` flag, and running the install process using a dedicated, low-privilege service account.** 

C) Using **[[Parameterization]]** and setting a **[[Rate Limiting]]** policy.

D) Enforcing **[[Determinism (Dependency)]]** and using **[[Stored Procedures]]**.

Click here to view the answer : [[Chapter 2.2 - Answer - Secure NPM]]

---

### 🎯 **Learning Objectives – Chapter 2.2**

By the end of this sub-chapter, you should be able to:

- Explain the risks of package **install scripts** and the mandate to disable them.
    
- Justify the use of **low-privilege, isolated accounts** for running build systems.
    
- Describe how **Network Segmentation** can block a compromised build server's outbound C2 communication.