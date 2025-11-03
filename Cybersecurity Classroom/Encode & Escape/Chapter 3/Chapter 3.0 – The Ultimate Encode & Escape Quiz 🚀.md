This quiz contains five questions covering all material from Chapters 1.1 through 2.3.

### 🧩 **Quiz Question 1 (The Core Difference)**

**Q:** What is the fundamental difference in purpose between **[[Encoding]]** (like Base64) and **[[Escaping]]** (like HTML Entity Encoding)?

A) **[[Encoding]]** prevents **[[SQL Injection]]**; **[[Escaping]]** prevents **[[XSS]]**.

B) **[[Encoding]]** is a defense against **[[Command Injection]]**; **[[Escaping]]** is a defense against **[[CSRF]]**.

C) **[[Encoding]]** is for **data representation** and reliable transmission; **[[Escaping]]** is for **injection prevention** and destroying a character's special meaning in a specific context. 

D) **[[Encoding]]** is a **[[Key Derivation Function (KDF)]]**; **[[Escaping]]** is for **[[Data Sanitization]]**.

Click here to view the answer : [[Chapter 3.0 - Answer 1 - Encode & Escape]]

---

### 🧩 **Quiz Question 2 (Defense for XSS)**

**Q:** When displaying user input in the main body of an HTML document, what is the _mandatory, last-line-of-defense_ technique that must be applied to prevent **[[Cross-Site Scripting (XSS)]]**?

A) **[[Input Validation]]** using **Allow-Listing** on the client-side.

B) **[[Parameterization]]** of the HTML tag structure.

C) **[[Contextual Output Encoding]]** (HTML Entity Escaping) applied to the user input. 

D) Using a **[[Data Retention Policy]]** for the input.

Click here to view the answer : [[Chapter 3.0 - Answer 2 - Encode & Escape]]

---

### 🧩 **Quiz Question 3 (Defense for SQLi)**

**Q:** An application is vulnerable to **[[SQL Injection]]** because it concatenates user input into its database queries. What is the **mandatory structural fix** that separates code from data to eliminate this vulnerability?

A) Using **[[Symmetric Encryption]]** on the user's password input.

B) Applying **[[Data Minimization]]** to the query string length.

C) **[[Parameterization]]** (Prepared Statements). 

D) Using a **[[Cryptographic Hash]]** of the user input before inserting it.

Click here to view the answer : [[Chapter 3.0 - Answer 3 - Encode & Escape]]


---

### 🧩 **Quiz Question 4 (The Trust Boundary Rule)**

**Q:** The single most important principle governing **[[Input Validation]]**, **[[Sanitization]]**, and **[[Contextual Output Encoding]]** is the **[[Never Trust User Input]]** rule. When and why must **[[Input Validation]]** be performed on the server?

A) Validation must be performed client-side to be fast, using the **[[SameSite]]** cookie attribute.

B) Validation must be performed on the server (**[[Server-Side Validation]]**) because client-side logic can be bypassed by an attacker sending arbitrary data across the **[[Trust Boundary]]**. 

C) Validation is only necessary for **[[Data at Rest]]** and not for **Data in Transit**.

D) Validation is performed to verify the **[[Digital Signature]]** of the incoming data stream.

Click here to view the answer : [[Chapter 3.0 - Answer 4 - Encode & Escape]]


---

### 🧩 **Quiz Question 5 (Defense for Command Injection)**

**Q:** To prevent **[[Command Injection]]**, a developer must execute the external OS command `ping 192.168.1.1` where the IP address is user-supplied. What is the safest, mandatory technique to use?

A) Strip all digits from the input using a **[[Sanitization]]** filter.

B) **Avoid using shell functions like `system()` and instead use safe, array-based APIs that pass the user input as a literal argument.** 

C) Apply **[[Contextual Output Encoding]]** to the user input before executing the command.

D) Store the command in a **[[Key Management System (KMS)]]** before execution.

Click here to view the answer : [[Chapter 3.0 - Answer 5 - Encode & Escape]]
