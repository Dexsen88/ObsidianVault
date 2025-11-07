🌟 **Aisha’s Leaked Secret** 
![[Aisha's Leaked Secret.png]]

Aisha committed her CI/CD pipeline script, which contained the plaintext NPM **[[Authentication]]** token, to a public Git repository. A bot quickly scraped the token. The attacker used the token to publish a malicious update to one of Aisha’s private packages, initiating a **[[Supply Chain Attack]]** against her entire organization.

Elena: “That’s a catastrophic **[[Information Leakage]]** failure, violating **[[Confidentiality]]** and **[[Integrity]]**. All registry tokens are high-value secrets. They must be treated like production database credentials, secured by a dedicated **[[Key Management System (KMS)]]**, and their privileges must be minimal.”

### 🧠 **Registry Authentication Tokens**

NPM registry tokens are used by the `npm` client and build systems (like CI/CD) to perform authenticated operations, such as publishing, installing private packages, or running **`npm audit fix`**.

- **Access Risk:** A stolen token provides an attacker with the ability to impersonate the user or service account, which can be used to either steal proprietary code or inject malicious code into the organization's private registry.
    
- **Token Storage Mandate:** Tokens **must never** be stored in:
    
    - Plaintext files on the local machine (except for temporary use in protected environments).
        
    - Source code or configuration files in version control (Git).
        
    - Build logs or environment variables visible in the CI/CD pipeline.
        

### 💡 **Mandatory Defense: Key Management and Environment Secrets**

All registry tokens must be managed as secure secrets:

1. **Use a [[Key Management System (KMS)]]:** For CI/CD environments, tokens must be injected as secured environment variables, preferably fetched at runtime from a **[[Key Management System (KMS)]]** (like HashiCorp Vault, AWS Secrets Manager, etc.).
    
2. **[[Principle of Least Privilege]] for Tokens:** Tokens should be created with the **absolute minimum permissions** required. A token used for _installing_ packages should **not** have the permission to _publish_ packages. This minimizes the impact of a token breach.
    
3. **Token Lifespan:** Tokens must be given short expiry times and rotated frequently.
    

### 🎯 **Secure Registry Configuration**
![[Secure Registry Configuration.png]]

The **`.npmrc`** configuration file dictates how the NPM client communicates with registries. Securing this file is critical:

- **No Secrets in File:** The file should only contain configuration settings, **not** plaintext tokens. Tokens should be stored separately (in the OS credential store or environment variables).
    
- **Using Scopes:** To defend against **[[Dependency Confusion]]**, organizations must use **scoped private registries** (e.g., `@mycorp:registry=https://private.registry.url`). This forces NPM to look at the private URL for any package starting with `@mycorp`, overriding the public registry default.
    
- **Mandatory TLS:** All communication with both public and private registries must use **[[TLS Protocol]]** (HTTPS) to protect token credentials in transit.
    

---

### 🧩 **Mini Quiz – Chapter 2.1**

**Q:** What two mandatory security practices must be implemented for an NPM **registry token** used by a CI/CD pipeline to upload a new package?

A) Store the token in a `.txt` file and give it only read-only privileges.

B) **Store the token in a [[Key Management System (KMS)]] and configure it with short expiry and only the publish privilege (Principle of Least Privilege).** 

C) Hardcode the token in the `package.json` file and use **[[Data Masking]]** on the token.

D) Use **[[Stored Procedures]]** and **[[Data Encryption]]** on the token.

Click here to view the answer : [[Chapter 2.1 - Answer - Secure NPM]]

---

### 🎯 **Learning Objectives – Chapter 2.1**

By the end of this sub-chapter, you should be able to:

- Explain the **[[Confidentiality]]** risk associated with NPM registry tokens.
    
- Justify why tokens must be managed by a **[[Key Management System (KMS)]]** and never checked into version control.
    
- Describe how **token privileges** and **scopes** enforce the **[[Principle of Least Privilege]]** and mitigate **[[Dependency Confusion]]**.