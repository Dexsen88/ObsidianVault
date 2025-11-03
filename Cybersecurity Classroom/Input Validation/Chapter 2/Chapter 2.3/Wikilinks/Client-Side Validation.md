### 🧠 **Definition and Role 🧑‍💻**

**Client-Side Validation** refers to the validation checks performed on the user's machine (in their web browser) using technologies like JavaScript or HTML5 form attributes.

- **Primary Purpose:** **User Experience (UX)**. It provides immediate feedback to the user, reducing errors, and prevents the submission of obviously malformed data, which can reduce unnecessary load on the server.
    
- **Security Risk:** It is **NOT** a security control and should **NEVER** be relied upon for enforcing **[[Confidentiality]]** or **[[Integrity]]**. An attacker can easily bypass this step by disabling JavaScript or using tools to send raw requests directly to the server.
    
- **Dependency:** This form of validation must **always** be duplicated and rigorously enforced by **[[Server-Side Validation]]** to comply with the **[[Never Trust User Input]]** principle.