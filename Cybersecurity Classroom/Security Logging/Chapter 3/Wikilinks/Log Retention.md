### 🧠 **Definition and Mandate 📅**

**Log Retention** is the mandatory policy that defines the minimum duration for which security logs must be stored in a secure, tamper-proof repository.

- **Goal:** To satisfy legal and regulatory compliance requirements (e.g., GDPR, PCI DSS) and ensure sufficient data is available for long-term forensic investigations.
    
- **Drivers:** The policy is driven by two factors: **Forensic Need** (covering the estimated **Dwell Time** of a typical breach, usually 90 days to 1 year) and **Compliance Need** (often multi-year).
    
- **Integrity:** Logs must maintain their **[[Integrity]]** throughout the retention period, often requiring them to be moved from a primary **[[Security Information and Event Management (SIEM)]]** system to a secured archival storage tier.