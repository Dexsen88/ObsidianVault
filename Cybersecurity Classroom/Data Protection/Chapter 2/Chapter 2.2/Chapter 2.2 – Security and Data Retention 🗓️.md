**🌟 Aisha’s Legacy Data**
![[Aisha's Legacy Data.png]]

Aisha discovered that the company was holding credit card transaction logs from seven years ago. The records were well past the legal and [[PCI DSS]] requirements. Every day this legacy data was stored unnecessarily increased the company's risk exposure.

Elena: "Indefinite storage is a major security liability. A **Data Retention Policy** is a mandatory security control that enforces **[[Data Minimization]]**. It dictates that data must be securely destroyed when it's no longer legally required or business-useful. The security of data disposal is as important as the security of storage."

### 🧠 **Data Retention and Disposal**

The **[[Data Retention Policy]]** manages the data lifecycle's end stages. This policy must balance legal requirements (e.g., financial audit laws) with the security principle of **[[Data Minimization]]**.

- **Goal:** To ensure that sensitive **[[Personally Identifiable Information (PII)]]** is kept only for the minimum necessary period, minimizing the target for attackers.
    
- **Disposal:** Data must be made unrecoverable through **[[Data Sanitization]]** methods (not just simple file deletion).
    

### 💡 **Data Sanitization Techniques**

**[[Data Sanitization]]** is the process of permanently and irreversibly destroying or rendering data unrecoverable from a storage medium. Simple deletion often leaves data fragments that can be recovered with forensic tools.

|**Technique**|**Mechanism**|**Use Case**|**Security Level**|
|---|---|---|---|
|**Degaussing**|Uses a strong magnetic field to completely erase data from _magnetic media_ (e.g., hard drives, tapes).|High-security magnetic media disposal.|High|
|**Purging/Overwrite**|Overwriting data with random or fixed patterns multiple times (e.g., with specific **[[Key Derivation Function (KDF)]]**s).|Suitable for re-using media within the organization.|Moderate-High|
|**Physical Destruction**|Shredding, melting, or pulverizing the storage media (e.g., burning a CD, shredding a hard drive).|Highest security for sensitive data, ensuring no fragments remain.|Maximum|

### 🎯 **Regulatory Mandate for Disposal**
![[Regulatory Mandate for Disposal.png]]

Regulations like **[[GDPR]]** grant the data subject the "right to be forgotten," which is a legal mandate for **[[Data Sanitization]]**. When a user exercises this right, the organization must prove that their data has been securely and irreversibly destroyed according to a strict, auditable procedure.

---

### 🧩 **Mini Quiz – Chapter 2.2**

**Q:** Why is simply deleting sensitive transaction logs from a database (marking the storage space as "available") an insufficient and dangerous practice under a **[[Data Retention Policy]]**?

A) It violates the **[[SameSite]]** cookie attribute, exposing the user to **[[CSRF]]**.

B) It requires the use of **[[Asymmetric Encryption]]**, which is too slow for bulk disposal.

C) **The underlying data remains physically on the storage medium and is easily recoverable by forensic tools, failing the requirement for [[Data Sanitization]].** 

D) It forces the system to require a **[[Hardware Security Module (HSM)]]** for future log entries.

Click here to view the answer : [[Chapter 2.2 - Answer - Data protection]]

---

### 🎯 **Learning Objectives – Chapter 2.2**

By the end of this sub-chapter, you should be able to:

- Define the **[[Data Retention Policy]]** and its connection to **[[Data Minimization]]**.
    
- Explain why simple file deletion is not secure data disposal.
    
- Identify the three primary methods of **[[Data Sanitization]]** (Degaussing, Purging/Overwrite, Physical Destruction).
    
- Understand the regulatory drive for secure disposal (e.g., the "right to be forgotten").