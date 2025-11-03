This quiz contains five questions covering all material from Chapters 1.1 through 2.3.

### 🧩 **Quiz Question 1 (Authentication Factors and Hashing)**

**Q:** A secure system requires a user to enter their password, a fingerprint scan, and a unique code from a **[[Hardware Token]]**. After a successful login, the system verifies the password against a stored **[[Password Hash]]**. What are the three authentication factors used, and what is the security purpose of the **[[Salt]]** in the hashing process?

A) Factors: Knowledge, Possession, and Knowledge; Purpose: To enforce **[[Session Timeout]]**.

B) Factors: Knowledge, Inherence, and Inherence; Purpose: To prevent **[[Denial of Service (DoS)]]** attacks.

C) Factors: Knowledge, Inherence, and Possession; Purpose: To prevent [[Rainbow Table]] attacks by making each password hash unique. 

D) Factors: Knowledge, Possession, and Possession; Purpose: To enable **[[OpenID Connect (OIDC)]]** flows.

Click here to view the answer : [[Chapter 3.0 - Answer 1 - AAS]]

---

### 🧩 **Quiz Question 2 (Authorization vs. IDOR)**

**Q:** An authenticated user with a 'Basic' **[[Role]]** successfully changes the URL parameter from `doc_id=50` to `doc_id=51` and views a sensitive document belonging to the 'Admin' role. Which component failed, and what is the name of this specific vulnerability?

A) Failed Component: **[[Authentication]]**; Vulnerability: **[[Session Hijacking]]**.

B) Failed Component: **[[Input Validation]]**; Vulnerability: **[[Path Traversal]]**.

C) **Failed Component: [[Authorization]] (Access Control); Vulnerability: [[Insecure Direct Object Reference (IDOR)]].** 

D) Failed Component: **[[Sanitization]]**; Vulnerability: **[[Cross-Site Request Forgery (CSRF)]]**.

Click here to view the answer : [[Chapter 3.0 - Answer 2 - AAS]]


---

### 🧩 **Quiz Question 3 (Session Token Security)**

**Q:** A web application correctly implements the **Secure** and **HttpOnly** cookie flags for its **[[Session Token]]**. Which two separate, unrelated attack vectors are mitigated by these flags, and what security pillar is primarily protected?

A) Mitigated: **[[CSRF]]** and **[[Denial of Service (DoS)]]**; Pillar: **[[Availability]]**.

B) Mitigated: Network eavesdropping (Man-in-the-Middle) and [[XSS]] token theft; Pillar: [[Confidentiality]]. 

C) Mitigated: **[[Session Hijacking]]** via guessing and **[[IDOR]]**; Pillar: **[[Integrity]]**.

D) Mitigated: **[[Path Traversal]]** and weak **[[Password Hash]]**es; Pillar: **[[Authentication]]**.

Click here to view the answer : [[Chapter 3.0 - Answer 3 - AAS]]

---

### 🧩 **Quiz Question 4 (Delegated Authentication Flows)**

**Q:** An application uses a third-party provider to allow users to sign in. The third-party sends back two tokens: an **[[Access Token]]** and an **[[ID Token]]**. Which one is used to verify the user's identity, and which security framework specifically provided the identity proof?

A) **[[Access Token]]**; provided by **[[OAuth 2.0]]**.

B) **[[Access Token]]**; provided by **[[OpenID Connect (OIDC)]]**.

C) **[[ID Token]]**; provided by **[[OAuth 2.0]]**.

D) **[[ID Token]]**; provided by **[[OpenID Connect (OIDC)]]**. 

Click here to view the answer : [[Chapter 3.0 - Answer 4 - AAS]]

---

### 🧩 **Quiz Question 5 (Session Management Lifecycle)**

**Q:** Why must the server perform **[[Session Revocation]]** (invalidating the token in the **[[Session Store]]**) immediately after a user successfully changes their password, even if the **[[Session Timeout]]** hasn't expired?

A) To enforce **[[Defense in Depth]]** against **[[Denial of Service (DoS)]]** attacks.

B) To prevent the new **[[Password Hash]]** from being exposed to the client.

C) To prevent a recently stolen or compromised [[Session Token]] from remaining valid, minimizing the risk of [[Session Hijacking]] under the old security context. 

D) To prepare the system for **[[Cross-Site Request Forgery (CSRF)]]** defense.

Click here to view the answer : [[Chapter 3.0 - Answer 5 - AAS]]

---

This concludes the **Authentication, Authorization & Session Management** module. You've demonstrated a strong understanding of MFA, access control models, and secure session management principles.