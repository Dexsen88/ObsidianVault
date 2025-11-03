### 🧠 **Definition and Mechanism 🪙**

**Tokenization** is a **Privacy Enhancing Technology (PET)** that replaces a sensitive data element (such as a credit card number or bank account number) with a non-sensitive equivalent called a **token**.

- **Goal:** To minimize the compliance scope and security risk associated with handling financial data (e.g., reducing the scope of **PCI DSS**).
    
- **Mechanism:** The original sensitive number is stored in a highly secured, isolated system (the **Token Vault**). The token, which has no mathematical relationship to the original number, is used by all public-facing and less-secure systems for transactions.
    
- **Security Benefit:** The token is useless to an attacker if stolen; they must breach the separate, highly-protected Token Vault to recover the original number.