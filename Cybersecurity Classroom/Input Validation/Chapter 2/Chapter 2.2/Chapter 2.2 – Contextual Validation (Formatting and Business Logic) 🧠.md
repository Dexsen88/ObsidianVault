🌟 **Aisha’s Price Problem** 
![[Aisha's Price problem.png]]
Aisha successfully used **[[Regular Expressions]]** to ensure a product price field contained only digits and a single decimal point. However, a customer managed to input "$0.00." The application accepted it, but the database threw an error because the price had to be greater than zero.

Elena: “You fixed the **Syntactic** problem (the format), but not the **Semantic** one (the meaning). The input was validly formatted, but it violated a core **Business Logic** rule. Validation must ensure the data is safe _and_ makes sense within the application’s context. This is **Contextual Validation**.”

### 🧠 **Semantic Validation: The Business Rules**

**Semantic Validation** is the process of checking if the input data aligns with the application’s business rules and is meaningful within the current system state. It usually requires accessing the database or other system resources.
![[Semantic Validation.png]]

### 💡 **Cross-Field Validation**
![[Cross-Field Validation.png]]

Sometimes, the validity of one field depends on the value of another field—this is **[[Cross-Field Validation]]**.

- **Example:** If a user selects 'Credit Card' as the payment method, the `Card Number` and `Expiry Date` fields become mandatory.
    
- **Security Risk:** Failing this check can lead to incomplete transactions or bypasses of required data, potentially violating **[[Confidentiality]]** by not enforcing proper data collection rules.
    

### 💡 **Special Case: URI Whitelisting**

When accepting input that is intended to be a link (**URI** or URL), strict **Whitelisting** is mandatory to prevent attackers from redirecting users to malicious sites or injecting code that fetches external resources.

- **Protocol Check:** Only allow safe protocols like `http`, `https`, or relative paths. **Explicitly forbid** dangerous protocols like `javascript:` or `data:`, which are used in **[[XSS]]** attacks.
    
- **Domain Check:** If the URI must point to a domain you control, enforce a strict **[[Domain Whitelisting]]** rule, preventing an attacker from linking to external phishing sites.
    

---

### 🧩 **Mini Quiz – Chapter 2.2**

**Q:** A user tries to transfer $5,000, but their account balance is only $1,000. Which type of validation is violated by this request?

A) **Syntactic** Validation (Incorrect format).

B) **[[Cross-Field Validation]]** (Inter-field dependency).

C) **Semantic** Validation (Violation of business rules). 

D) **[[Canonicalization]]** (Encoding failure).

Click here to view the answer : [[Chapter 2.2 - Answer]]

### 🎯 **Learning Objectives – Chapter 2.2**

By the end of this sub-chapter, you should be able to:

- Differentiate between **Syntactic** (format) and **Semantic** (meaning) validation.
    
- Explain the role of **Semantic Validation** in enforcing business rules and **[[Integrity]]**.
    
- Understand the concept and importance of **[[Cross-Field Validation]]**.
    
- Apply strict **[[Domain Whitelisting]]** for inputs intended to be URIs or links.