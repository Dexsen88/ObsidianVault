**🌟 Aisha’s Data Mountain**
![[Aisha's Data Mountain.png]]

Aisha was tasked with securing all the company’s data, but she was overwhelmed. Some data was public, some was financial, and some contained personal information. Treating all data the same was inefficient and ineffective.

Elena: “You can't protect what you don't classify. **Data Classification** is the mandatory first step. It allows you to apply the appropriate security controls, adhering to the fundamental principle that data should be protected based on its sensitivity and regulatory requirements.”

### 🧠 **The Three Data States**

Data security controls must be applied consistently across the entire **data lifecycle**, which includes three states:

1. **[[Data at Rest]] (Storage):** Data residing on physical media (databases, hard drives, backups).
    
    - _Control:_ **[[Symmetric Encryption]]** (e.g., AES-256) and **[[Key Management]]**.
        
2. **[[Data in Transit]] (Movement):** Data actively moving over a network (LAN, WAN, Internet).
    
    - _Control:_ **[[TLS Protocol]]** (HTTPS) for **[[Confidentiality]]** and **[[Integrity]]**.
        
3. **Data in Use (Processing):** Data being actively processed by a computer system (in CPU registers, RAM).
    
    - _Control:_ Secure coding, secure operating systems, and specialized hardware protections.
        

### 💡 **Data Classification**

**[[Data Classification]]** is the process of categorizing information based on its level of sensitivity and the legal impact if it is compromised.

|**Classification Level**|**Example Data**|**Security Impact**|
|---|---|---|
|**Public**|Press releases, marketing materials.|Minimal **[[Confidentiality]]** required.|
|**Internal/Private**|Internal memos, non-public procedures.|Moderate protection.|
|**Confidential/Sensitive**|Financial records, trade secrets, **[[Personally Identifiable Information (PII)]]**.|High protection, often regulated (e.g., through **[[GDPR]]**).|

### 🎯 **The Principle of Data Minimization**
![[The Principle of Data Minimalization.png]]

A foundational principle of modern data protection is **[[Data Minimization]]**.

- **Definition:** Organizations should limit the collection of personal data to what is directly relevant and necessary to accomplish a specified purpose.
    
- **Security Benefit:** By not collecting or storing unnecessary sensitive data, the attack surface is dramatically reduced, minimizing the potential impact of a data breach. This is a core tenant of privacy regulations like **[[GDPR]]**.
    

---

### 🧩 **Mini Quiz – Chapter 1.1**

**Q:** A company is logging all user activity, including IP addresses, for a period of five years, even though its regulatory requirement for logs is only three months. Which core data principle is being violated, and what is the associated security benefit of adhering to it?

A) Principle violated: **[[Availability]]**; Benefit: Faster log file parsing.

B) Principle violated: **[[Defense in Depth]]**; Benefit: Stronger **[[Authentication]]**.

C) **Principle violated: [[Data Minimization]]; Benefit: Reducing the attack surface and potential breach impact by not storing unnecessary sensitive data.** 

D) Principle violated: **[[Non-Repudiation]]**; Benefit: Easier implementation of **[[Digital Signature]]**s.

Click here to view the answer : [[Chapter 1.1 - Answer - Data Protection]]

---

### 🎯 **Learning Objectives – Chapter 1.1**

By the end of this sub-chapter, you should be able to:

- Identify the three states of the data lifecycle: At Rest, In Transit, and In Use.
    
- Explain the process of **[[Data Classification]]** and its impact on control selection.
    
- Define **[[Data Minimization]]** and its security benefits.
    
- Recognize **[[Personally Identifiable Information (PII)]]** and the need for regulation like **[[GDPR]]**.