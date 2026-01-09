🌟 **Aisha’s Checkpoint** 
![[Aisha's Checkpoint.png]]
Aisha has implemented all the necessary controls—**[[Encryption]]**, **[[Data Minimization]]**, and a **[[Data Retention Policy]]**. Now, a new legal requirement mandates that she prove the company's compliance before collecting any new data.

Elena: “You need to document your risks and prove your controls work. This requires a formal, pre-emptive review process called a **Privacy Impact Assessment (PIA)** and a continuous verification system, which is **Auditing**.”

### 🧠 **Privacy Impact Assessment (PIA) / Data Protection Impact Assessment (DPIA)**

A **[[Privacy Impact Assessment (PIA)]]** (or **DPIA** under **[[GDPR]]**) is a formal process for identifying, analyzing, and documenting the privacy risks associated with collecting, using, or disclosing **[[Personally Identifiable Information (PII)]]** in a new system, project, or process.

- **When Required:** A **DPIA** is mandatory under **[[GDPR]]** when a data processing activity is likely to result in a "high risk" to the rights and freedoms of individuals (e.g., using new tracking technology or processing sensitive data on a large scale).
    
- **Goal:** To mitigate risks _before_ data processing begins, ensuring **[[Data Protection]]** controls are designed into the system (Privacy by Design).
    

### 💡 **Auditing and Logging**

After controls are implemented, **Auditing** is the continuous process of verification and evidence collection. Security policies require that all systems and applications generate detailed, tamper-proof records of security-relevant events, known as **Audit Logs**.

- **Audit Logs:** These logs must track all **[[Authentication]]** attempts, **[[Authorization]]** failures, changes to **[[Access Control]]** lists, and access to sensitive **[[Data at Rest]]** (e.g., records in the **[[Session Store]]**).
    
- **Tamper-Proofing:** Logs must be protected with strong **[[Integrity]]** controls (e.g., **[[Cryptographic Hash]]**ing and read-only storage) to ensure that an attacker cannot erase their tracks.
    

### 🎯 **Accountability and Remediation**
![[Accountability & Remendiation.png]]

Auditing and assessments are ultimately about **Accountability**. If a **PIA** identifies a high risk, a remediation plan must be created and executed. If an audit reveals a policy violation (e.g., a **[[Data Retention Policy]]** failure), corrective action must be taken immediately. This cyclical process ensures the continued **[[Availability]]** and trustworthiness of the system.

---

### 🧩 **Mini Quiz – Chapter 2.3**

**Q:** Under **[[GDPR]]**, when is a **Data Protection Impact Assessment (DPIA)** explicitly mandatory?

A) Only when implementing a **[[Key Derivation Function (KDF)]]** for new passwords.

B) Only when the data is being disposed of using **[[Data Sanitization]]**.

C) **When a data processing activity is likely to result in a "high risk" to the rights and freedoms of individuals.** 

D) When switching a website from HTTP to the **[[TLS Protocol]]** (HTTPS).

✅ **Correct Answer: C) When a data processing activity is likely to result in a "high risk" to the rights and freedoms of individuals.**

💡 **Explanation:** The DPIA is a proactive regulatory requirement under **[[GDPR]]** to assess and mitigate risks tied to new, potentially invasive processing activities _before_ they are launched.

---

### 🎯 **Learning Objectives – Chapter 2.3**

By the end of this sub-chapter, you should be able to:

- Define and explain the purpose of a **[[Privacy Impact Assessment (PIA)]]**/**DPIA**.
    
- Understand the importance of continuous **Auditing** and tamper-proof **Audit Logs**.
    
- Explain how **PIA** and **Auditing** enforce organizational **Accountability** and drive remediation.