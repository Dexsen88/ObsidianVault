🌟 Aisha’s Analytics Conflict
![[Aisha's Analytics Conflict.png]]

Aisha’s analytics team needed to study customer purchase patterns, but the data contained [[Personally Identifiable Information (PII)]] like names and addresses, which was too risky to share raw. The team needed a way to use the data without knowing who the data belonged to.

Elena: “This is where **Privacy Enhancing Technologies (PETs)** are mandatory. They allow you to retain the _utility_ of the data for analysis while destroying or obscuring the _identity_ of the data subject. This enforces **[[Data Minimization]]** at the usage stage.”

### 🧠 **Core Privacy Enhancing Techniques**

PETs transform sensitive data to make it usable for non-privacy-invasive purposes. The goal is to obscure identity while preserving analytical value.

|**Technique**|**Mechanism**|**Security Benefit**|
|---|---|---|
|**[[Anonymization]]**|Data elements are altered or destroyed to make it impossible to re-identify the data subject.|Highest level of privacy; removes data from **[[GDPR]]** scope.|
|**[[Pseudonymization]]**|Replacing direct identifiers (e.g., name) with a consistent, reversible pseudonym (e.g., a random ID).|Allows re-identification only with the key; maintains analytical utility.|
|**Tokenization**|Replacing sensitive data (e.g., credit card number) with a non-sensitive placeholder (token).|High security; token is useless without the secure **Token Vault**.|

### 💡 **The Risk of Re-identification**

The key risk in techniques like **[[Pseudonymization]]** is the possibility of **Re-identification**. If an attacker combines the pseudonymized data with external, publicly available information, they may be able to link the data back to the original individual.

- **Defense:** Effective privacy requires removing sufficient **quasi-identifiers** (e.g., ZIP code + age + gender) that, in combination, might uniquely identify an individual.
    

### 🎯 **Tokenization for Payment Data**
![[Tokenization for Payment Data.png]]

**[[Tokenization]]** is the mandatory technique for handling sensitive financial data, such as credit card numbers, which are regulated by standards like **PCI DSS**.

- **Process:** The original sensitive value is stored in a highly secured, isolated **Token Vault**. The application then uses the useless, non-sensitive token placeholder for all processing, storage, and billing tasks. This dramatically reduces the scope of the systems that must comply with strict financial regulations.
    

---

### 🧩 **Mini Quiz – Chapter 1.2**

**Q:** What is the critical difference between **[[Anonymization]]** and **[[Pseudonymization]]**, especially in the context of compliance with **[[GDPR]]**?

A) **[[Anonymization]]** is irreversible; **[[Pseudonymization]]** is reversible with a key.

B) **[[Anonymization]]** allows analysis; **[[Pseudonymization]]** does not.

C) **[[Anonymization]]** is the irreversible destruction of identity, taking the data out of **[[GDPR]]**'s scope; **[[Pseudonymization]]** is reversible and keeps the data within **[[GDPR]]**'s scope. 

D) **[[Pseudonymization]]** protects **[[Data at Rest]]**; **[[Anonymization]]** protects **[[Data in Transit]]**.

Click here to view the answer : [[Chapter 1.2 - Answer - Data Protection]]

---

### 🎯 **Learning Objectives – Chapter 1.2**

By the end of this sub-chapter, you should be able to:

- Define **Privacy Enhancing Technologies (PETs)** and their role in data usage.
    
- Differentiate between **[[Anonymization]]** and **[[Pseudonymization]]** and their regulatory impact.
    
- Explain the process and security benefits of **[[Tokenization]]** for financial data.