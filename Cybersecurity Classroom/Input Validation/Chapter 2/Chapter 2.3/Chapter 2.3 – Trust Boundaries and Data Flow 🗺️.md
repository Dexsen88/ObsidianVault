🌟 **Aisha’s Hidden API** 
![[Aisha's Hidden API.png]]
Aisha had a public web form that fed data into a primary API, which then called a separate, internal **Microservice** to process the data. She assumed that since the data was validated once by the public API, the internal service didn't need to check it again.

Elena: “That’s a common, dangerous assumption, Aisha. You introduced a break in your **[[Defense in Depth]]**. Every time data moves from a less-trusted component to a more-trusted component, it crosses a **Trust Boundary**. The rule is: **Revalidate upon entry into a trusted component.**"

### 🧠 **Defining the Trust Boundary**

A **Trust Boundary** is an imaginary line that separates code and components that operate at different levels of privilege or security. The most obvious boundary is the perimeter between the public internet and your private server (**[[Client-Side Validation]]** vs. **[[Server-Side Validation]]**).

However, internal boundaries are just as important:
![[Trusted vs Less Trusted components.png]]

### 💡 **The Data Flow Principle: Validate and Sanitize**

The validation process should be modeled based on the data flow, not just the entry point. Every time data crosses a **Trust Boundary**, two actions must occur:

1. **Validation (The Check):** Use **Whitelisting** and **[[Canonicalization]]** to ensure the data is safe, correctly formatted, and adheres to **[[Semantic Validation]]** rules. If it fails, **[[Log the Failure]]** and reject the request.
    
2. **Sanitization (The Clean-up):** After validation, **Sanitization** cleans the input by transforming unsafe characters or removing them entirely, ensuring the data is harmless before it's used. This process protects the **[[Integrity]]** of your system.
    

- _Example:_ A comment field that allows basic formatting (like bold tags `<b>`) can be sanitized to remove all other HTML tags (`<script>`) before storage. This differs from **[[Output Encoding]]**, which only prepares the data for safe display.
    

### 🎯 **The Revalidation Rule**
![[The Revalidation Rule.png]]

The fundamental rule of **[[Defense in Depth]]** in service-oriented architectures is **Revalidation**:

> If a service receives data from _any_ source—even another internal, trusted service—it must treat that data as untrusted and perform **[[Input Validation]]** again before using it.

This protects the final, most sensitive components (like the database) from internal bugs or a single compromised microservice.

### 🧩 **Mini Quiz – Chapter 2.3**

**Q:** Why is it a security risk for a backend Microservice (a trusted component) to skip validation on data received from the primary API Gateway (another trusted component)?

A) It causes unnecessary **[[Denial of Service (DoS)]]** attacks due to large payload sizes.

B) It creates a potential vulnerability if the API Gateway component is compromised or if there is a programming bug that allows malformed data to enter the trusted zone. 

C) It violates the principle of **[[Cross-Field Validation]]**.

D) It prevents the application from using **[[Regular Expressions]]**.

Click here to view the answer : [[Chapter 2.3 - Answer]]

### 🎯 **Learning Objectives – Chapter 2.3**

By the end of this sub-chapter, you should be able to:

- Define a **[[Trust Boundary]]** and identify when data crosses one.
    
- Explain the critical difference between **Validation** (the check) and **[[Sanitization]]** (the clean-up).
    
- Apply the **Revalidation** rule to data flows in multi-tiered applications.