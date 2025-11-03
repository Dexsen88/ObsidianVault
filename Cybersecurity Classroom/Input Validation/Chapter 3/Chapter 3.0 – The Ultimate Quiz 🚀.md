This quiz contains five questions covering all material from Chapters 1.1 through 2.3.

### 🧩 **Quiz Question 1 (The Core Principle)**

**Q:** An attacker successfully enters the string `' OR 1=1; --` into a login form, bypassing authentication. Which foundational security principle was violated, and which core security defense should have prevented this?

A) Principle violated: **[[Availability]]**; Defense missed: **[[Output Encoding]]**.

B) Principle violated: **[[Integrity]]**; Defense missed: **[[Canonicalization]]**.

C) Principle violated: **[[Never Trust User Input]]**; Defense missed: **[[Server-Side Validation]]** using **Parameterized Queries**. 

D) Principle violated: **[[Confidentiality]]**; Defense missed: **[[Cross-Field Validation]]**.

Click here to view the answer: [[Chapter 3.0 - Answer 1]]

---

### 🧩 **Quiz Question 2 (Validation Timing and Location)**

**Q:** Data is accepted by a public API Gateway, which performs **[[Client-Side Validation]]** checks. The data is then passed to an internal, sensitive **Microservice** for storage in the database. Where must the second, security-critical validation take place, and what is the principle that mandates this check?

A) In the database, using SQL constraints; Principle: **[[Principle of Least Privilege]]**.

B) In the API Gateway, using **[[Canonicalization]]**; Principle: **[[Availability]]**.

C) In the browser, using JavaScript; Principle: **Defense in Depth**.

D) **In the internal Microservice (before use); Principle: The Trust Boundary Rule (Revalidation).** 

Click here to view the answer: [[Chapter 3.0 - Answer 2]]

---

### 🧩 **Quiz Question 3 (Whitelisting vs. Blacklisting)**

**Q:** A developer implements a security rule that blocks all known malicious HTML tags like `<script>`, `<iframe>`, and `<object>` from a comment field. An attacker bypasses this check by submitting the payload using URL encoding. What two validation techniques were implemented incorrectly or missed entirely?

A) **[[Cross-Field Validation]]** and **[[Semantic Validation]]**.

B) **Blacklisting** (used incorrectly) and **[[Output Encoding]]** (missed).

C) **Blacklisting** (used incorrectly) and **[[Canonicalization]]** (missed). 

D) **[[Domain Whitelisting]]** and **[[Denial of Service (DoS)]]** protection.

Click here to view the answer: [[Chapter 3.0 - Answer 3]]

---

### 🧩 **Quiz Question 4 (The Role of Sanitization)**

**Q:** What is the primary functional difference between **Validation** and **[[Sanitization]]** when dealing with user input for a rich-text comment field?

A) Validation is done on the client-side, and Sanitization is done on the server-side.

B) Validation only applies to numeric inputs, and Sanitization only applies to text inputs.

C) **Validation is the "check" that accepts or rejects the input, while Sanitization is the "clean-up" that transforms unsafe elements into safe elements.** ✅

D) Validation prevents **[[XSS]]**, while Sanitization prevents **[[SQL Injection]]**.

Click here to view the answer: [[Chapter 3.0 - Answer 4]]

---

### 🧩 **Quiz Question 5 (Error vs. Exposure)**

**Q:** A function designed to read a file based on user input crashes and displays a full **stack trace** including file paths and database connection details. This scenario primarily violates which two security principles?

A) **[[Integrity]]** and **[[Availability]]**.

B) **[[Denial of Service (DoS)]]** and **[[Principle of Least Privilege]]**.

C) **[[Availability]]** and **[[Information Leakage]]**. ✅

D) **[[Cross-Field Validation]]** and **[[Semantic Validation]]**.

Click here to view the answer: [[Chapter 3.0 - Answer 5]]