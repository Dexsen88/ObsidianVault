🌟 **Aisha’s Compliance Audit**
![[Aisha's Compliance Audit.png]]
A regulatory body conducted a compliance audit on Aisha's application, specifically asking for evidence of all privileged account activity from 10 months ago. Aisha discovered her **[[Security Logging]]** system was only configured to keep logs for 90 days, leading to an automatic failure of the compliance requirement.

Elena: “Compliance laws like **GDPR, HIPAA, and PCI DSS** are very specific about how long you must retain security logs. If you delete logs too soon, you lose the ability to prove **[[Non-Repudiation]]** for the required audit period. **Log Retention** is a legal and security mandate, not just an operational one.”

### 🧠 **Mandatory Log Retention**

**Log Retention** is the mandatory policy that dictates how long security logs must be kept in the secure, immutable **[[Security Information and Event Management (SIEM)]]** system.

- **Forensic Need:** Logs must be retained for at least the expected **Dwell Time** (the time before an attacker is detected). Since breaches often go unnoticed for months, a minimum 90-day to 1-year retention is standard practice for immediate access.
    
- **Compliance Need:** Regulatory requirements often dictate **multi-year retention** (e.g., 6 years for financial data in some jurisdictions). Longer-term, less-accessible archival storage is mandatory for compliance.
    
- **Defense Mandate:** The **Retention Policy** must be actively enforced in the **SIEM** to ensure data is deleted when necessary (**[[Data Minimization]]**), but never before the mandatory compliance window expires.
    

### 💡 **Compliance and Non-Repudiation**

Secure, tamper-proof logs are the foundation of legal and regulatory compliance.

- **Audit Trail:** Logs provide the **Audit Trail** necessary to prove to regulators that controls (like **[[Principle of Least Privilege]]** or data access restrictions) were functioning as designed.
    
- **[[Non-Repudiation]] Assurance:** For any regulatory breach investigation, the logs must be able to irrefutably answer: _Was the security incident caused by a malicious third party, or was it a privileged employee acting inappropriately?_ The protected log (**Immutability**) is the only source of truth.
    
- **Key Data Points:** Compliance often requires long-term retention of access logs related to **[[Personally Identifiable Information (PII)]]** and financial transactions.
    

### 🎯 **Protecting Archival Logs**
![[Protecting Archival Logs.png]]

While primary **SIEM** logs are used for real-time analysis, older logs needed for compliance often move to cheaper, **archival storage** (like cold storage in the cloud).

- **Integrity:** Even in archival storage, the logs must be protected by cryptographic **hashing** and access controls to ensure their **[[Integrity]]**—they must not be modified in storage.
    
- **Accessibility:** Archived logs must still be reasonably accessible for retrieval during an audit or a long-running forensic investigation, which is why a well-organized index is crucial.
    

---

### 🧩 **Mini Quiz – Chapter 2.3**

**Q:** Why do compliance standards (like PCI DSS or GDPR) require security logs to be retained for a mandatory period, and what two security principles does this policy support?

A) To enforce **[[Buffer Overflow]]** defense; Principles: **[[Data Minimization]]** and **[[Data Masking]]**.

B) To enable **[[Lateral Movement]]** analysis; Principles: **[[Verbose Error Message]]** and **[[Determinism (Dependency)]]**.

C) **To provide the necessary audit trail for legal/regulatory proof; Principles: [[Non-Repudiation]] and [[Integrity]] of the evidence.** 

D) To facilitate **[[Software Composition Analysis (SCA)]]**; Principles: **[[Separation of Duties]]** and **[[Pinning (Dependency)]]**.

Click here to view the answer : [[Chapter 2.3 - Answer - Security Logging]]

---

### 🎯 **Learning Objectives – Chapter 2.3**

By the end of this sub-chapter, you should be able to:

- Explain the two core drivers (forensic and compliance) for **Log Retention** policies.
    
- Justify how mandatory log retention supports **[[Non-Repudiation]]** in legal and compliance contexts.
    
- Identify the need for **long-term archival storage** and its necessary protection measures.