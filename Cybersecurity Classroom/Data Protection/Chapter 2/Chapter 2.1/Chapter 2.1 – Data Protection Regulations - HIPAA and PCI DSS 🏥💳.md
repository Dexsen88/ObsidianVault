🌟 **Aisha’s Compliance Check** 
![[Aisha's Compliance Check.png]]
Aisha's company handles both patient health records (PHI) and processes credit card payments. She quickly realized that compliance with **[[GDPR]]** alone was not enough; she needed to meet specific standards for the health and finance sectors, which are regulated by two different authorities.

Elena: "You need a multi-layered approach. **HIPAA** dictates how you protect health information, and **PCI DSS** dictates how you protect payment card data. Both require robust **[[Confidentiality]]** and **[[Integrity]]** controls, but they focus on different types of **[[Personally Identifiable Information (PII)]]**."

### 🧠 **HIPAA: Protecting Patient Data**

The **[[HIPAA]]** (Health Insurance Portability and Accountability Act) standard in the U.S. sets rules for safeguarding **Protected Health Information (PHI)**.

- **Scope:** Applies to covered entities (e.g., hospitals, clinics) and their business associates.
    
- **Key Requirement: Security Rule:** Mandates the implementation of administrative, physical, and technical safeguards to ensure the **Confidentiality**, **Integrity**, and **[[Availability]]** of PHI.
    
    - _Technical Safeguards Example:_ Requiring **[[Encryption]]** for all electronic PHI (ePHI) when it is **[[Data at Rest]]** and **[[Data in Transit]]**.
        

### 💡 **PCI DSS: Protecting Cardholder Data**

The **[[PCI DSS]]** (Payment Card Industry Data Security Standard) is a set of mandatory security standards that apply to _all entities_ that store, process, or transmit cardholder data (CHD).

- **Scope:** Governed by the major payment card brands (Visa, Mastercard, etc.), making it a global requirement for e-commerce and retail.
    
- **Key Requirement:** Its core focus is on minimizing the environment that stores Cardholder Data. This is often achieved through **[[Tokenization]]** to replace the primary account number (PAN) with a non-sensitive value.
    
- **Mandatory Controls:** Includes requirements for robust firewall configuration, protection against **[[Malware]]**, strict **[[Access Control]]**, and the use of secure coding practices.
    

### 🎯 **Regulatory Overlap**
![[Regulatory Overlap.png]]

Both **[[HIPAA]]** and **[[PCI DSS]]** reinforce the same fundamental cryptographic principles we covered:

- **Encryption:** Mandatory use of **[[TLS Protocol]]** (for **Data in Transit**) and strong **[[Symmetric Encryption]]** (for **Data at Rest**).
    
- **Access Control:** Enforcing the **[[Principle of Least Privilege]]** for all systems that touch sensitive data.
    
- **Auditing:** Both require extensive logging, monitoring, and regular auditing to prove compliance.
    

---

### 🧩 **Mini Quiz – Chapter 2.1**

**Q:** Why is **[[Tokenization]]** the preferred security control for organizations that must comply with **[[PCI DSS]]**?

A) **[[Tokenization]]** provides **[[Non-Repudiation]]** for financial transactions.

B) **[[Tokenization]]** is an efficient way to implement **[[Symmetric Encryption]]** on the payment card number.

C) **[[Tokenization]]** provides irreversible **[[Anonymization]]** of the cardholder's identity.

D) **[[Tokenization]]** replaces the sensitive card data with a non-sensitive placeholder, greatly reducing the scope and compliance cost of the [[PCI DSS]] requirements. 

Click here to view the answer : [[Chapter 2.1 - Answer - Data Protection]]

---

### 🎯 **Learning Objectives – Chapter 2.1**

By the end of this sub-chapter, you should be able to:

- Identify the scope and primary focus of **[[HIPAA]]** (PHI) and **[[PCI DSS]]** (Cardholder Data).
    
- Explain how both regulations mandate the use of cryptographic controls (e.g., **[[Encryption]]**).
    
- Understand the role of **[[Tokenization]]** as a crucial risk-reduction strategy in a **[[PCI DSS]]** environment.