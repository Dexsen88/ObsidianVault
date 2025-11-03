### 🧠 **Definition and Mechanism 🔗**

**Cross-Field Validation** is a form of **Semantic Validation** that checks the validity of one input field based on the value or presence of one or more other input fields in the same form or data submission.

- **Goal:** To enforce complex business constraints and logical dependencies between different pieces of data.
    
- **Examples:**
    
    - The `Confirm Password` field must match the `Password` field.
        
    - The `End Date` must occur after the `Start Date`.
        
    - The `Shipping Address` is mandatory _if_ the `Delivery Method` is 'Physical Shipment'.
        
- **Security Importance:** Failure to perform this check can lead to illogical system states, data entry errors, or security bypasses where an attacker provides valid-looking data that, when combined, violates core system rules, impacting **[[Integrity]]**.