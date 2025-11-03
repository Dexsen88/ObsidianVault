### 🧠 **Definition and Mechanism 🌐**

**Domain Whitelisting** is a highly restrictive form of **Whitelisting** that is applied specifically to Uniform Resource Identifiers (URIs) or URLs submitted by a user. It only allows the application to process or link to domains that are explicitly approved and trusted.

- **Goal:** To prevent users from inputting links that redirect visitors to malicious sites (phishing) or that cause the application to load untrusted resources.
    
- **Security Defense:** This is a crucial defense against certain types of **[[XSS]]** and Open Redirect vulnerabilities. By only allowing **trusted protocols** (like `https`) and **trusted domains** (e.g., yourcompany.com), the application protects **[[Confidentiality]]** and user safety.
    
- **Procedure:** The application must parse the URL, extract the protocol and domain name, and check both against an explicit, hardcoded list of allowed values on the **[[Server-Side Validation]]**.