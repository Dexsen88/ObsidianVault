### 🧠 **Definition and Purpose 🌐**

**CORS (Cross-Origin Resource Sharing)** is a browser mechanism that allows a web page running JavaScript from one domain to interact with resources (APIs) from another domain.

- **Goal:** To enforce a secure **[[Trust Boundary]]** for APIs. The API uses the `Access-Control-Allow-Origin` header to tell the browser which origins (domains) are explicitly permitted to read the response.
    
- **Security:** Improper configuration (e.g., allowing `*` for all origins) can lead to **[[Information Leakage]]** and allows attackers to read the response of sensitive API calls made by the victim's browser.
    
- **Mandate:** Must be configured using a strict **Allow-Listing** of trusted origins only.