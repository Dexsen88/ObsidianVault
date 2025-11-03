### 🧠 **Definition and Role 🎯**

**Semantic Validation** is the process of checking input data against the application's **Business Logic** and current system state to ensure the data is meaningful, logical, and adheres to all application rules.

- **Goal:** To enforce data integrity beyond simple formatting. While **Syntactic Validation** ensures the data _looks_ correct (e.g., a number), Semantic Validation ensures the data _makes sense_ (e.g., the number is positive or within a specific range).
    
- **Procedure:** This often requires querying the database or interacting with other services. Examples include checking if a start date precedes an end date, ensuring a unique ID is not already registered, or confirming a withdrawal amount does not exceed the account balance.
    
- **Importance:** A failure in Semantic Validation results in corrupted data or illogical system states, directly impacting the **[[Integrity]]** of the application and potentially leading to **[[Error and Exception Handling]]** failures. It is a key part of **[[Server-Side Validation]]**.