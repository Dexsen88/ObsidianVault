🌟 **Aisha’s Chained Error** 
![[Aisha's Chained Error.png]]
Aisha’s application, Service A, called an external component, Service B. When Service B failed, it returned a **[[Verbose Error Message]]** containing its internal IP address. Service A didn't properly catch this error and simply logged the _entire_ upstream error message, including the internal IP, to the shared **[[Security Logging]]** system.

Elena: "That's a **Chained Error** security risk. While Service A didn't have a bug, its failure to **Cleanse** the upstream error before logging or propagating it caused **[[Information Leakage]]** across a **[[Trust Boundary]]**. This is a major failure of **[[Confidentiality]]** in a microservices environment."

### 🧠 **Chained Errors and Trust Boundaries**

A **[[Chained Error]]** occurs when an exception is thrown in one service (A) because a downstream service (B) failed, and the original error details from B are included in the new exception thrown by A.

- **Vulnerability:** If the application doesn't sanitize the external service's error, a **[[Verbose Error Message]]** from the external service can leak internal details of the _entire_ architecture to the user or to a shared logging system accessible by low-privilege staff.
    
- **Mandatory Control:** Any service that communicates with another service (especially external or lower-trust ones) must sanitize or cleanse the response before propagating a new, localized error.
    

### 💡 **Error Cleansing and Sanitization**

**Error Cleansing** is the practice of selectively removing sensitive or verbose information from an exception object before it is logged or passed to a component outside the immediate **[[Trust Boundary]]**.

- **Goal:** To enforce **[[Confidentiality]]** and prevent **[[Information Leakage]]** from internal systems, while preserving enough information in the **[[Security Logging]]** system for forensic analysis.
    
- **Implementation:** The service should catch the external error, strip out sensitive data (like connection strings, full stack traces, or internal server names), and re-throw a **[[Custom Exceptions]]** object that only contains a safe, internal correlation ID.
    

### 🎯 **Logging and Correlation IDs**
![[Logging & Correlation IDS.png]]

When handling errors across multiple services, a **Correlation ID** is a mandatory, unique identifier generated at the start of a request and passed through every service call.

- **Purpose:** If a user reports a generic error, the user-facing message provides the Correlation ID. This allows an administrator to quickly look up the _full, internal, verbose_ error details within the secured **[[Security Logging]]** system, without ever exposing those details to the user. This balances security (**[[Confidentiality]]**) with operational effectiveness.
    

---

### 🧩 **Mini Quiz – Chapter 2.3**

**Q:** When Service A receives a **[[Verbose Error Message]]** from Service B (a **[[Trust Boundary]]** violation), what mandatory action must Service A take before logging or passing the error to the user?

A) Apply **[[Parameterization]]** to the error message content.

B) **Sanitize or cleanse the error message to remove all internal details (like IP addresses), and then log the clean error with a Correlation ID.** 

C) Ensure the error message uses **[[Contextual Output Encoding]]** for the HTML context.

D) Immediately trigger a **[[Denial of Service (DoS)]]** response via **[[Rate Limiting]]**.

Click here to view the answer : [[Chapter 2.3 - Answer - Error & Exceptions Handling]]

---

### 🎯 **Learning Objectives – Chapter 2.3**

By the end of this sub-chapter, you should be able to:

- Define a **[[Chained Error]]** and its security implications in distributed systems.
    
- Explain the process of **Error Cleansing** to prevent **[[Information Leakage]]**.
    
- Understand the role of the **Correlation ID** in balancing security and debugging.