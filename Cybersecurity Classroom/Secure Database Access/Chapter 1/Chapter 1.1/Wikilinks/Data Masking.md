### 🧠 **Definition and Purpose 🎭**

**Data Masking** is a **[[Data Protection]]** technique that obfuscates, scrambles, or substitutes sensitive data with realistic, but non-sensitive, data.

- **Goal:** To ensure that non-production environments (like development, testing, or training) contain realistic data for testing without exposing genuine **[[Personally Identifiable Information (PII)]]** or confidential secrets. This enforces the **[[Confidentiality]]** principle.
    
- **Mechanism:** The masked data maintains its original format (e.g., a phone number remains 10 digits), but the values are fabricated and cannot be reversed to reveal the original data.
    
- **Contrast:** Differs from **[[Data Encryption]]**, which is a reversible process intended to secure production data.