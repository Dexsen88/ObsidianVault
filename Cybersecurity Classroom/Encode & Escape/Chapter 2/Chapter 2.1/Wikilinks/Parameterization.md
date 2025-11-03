### 🧠 **Definition and Mechanism 📐**

**Parameterization** (or Prepared Statements) is the mandatory defense technique against **[[SQL Injection]]**. It works by structurally separating the SQL command from all user-supplied data.

- **Goal:** To ensure the database engine treats all user input as literal data values, rather than executable code.
    
- **Mechanism:** The developer sends the SQL query template (with placeholders) to the database first. The database pre-compiles this template. User data is then sent separately, ensuring the data is processed only as values.
    
- **Security:** This method is the strongest defense because it fixes the underlying structural flaw, making it impervious to injection attacks regardless of the characters the user inputs.