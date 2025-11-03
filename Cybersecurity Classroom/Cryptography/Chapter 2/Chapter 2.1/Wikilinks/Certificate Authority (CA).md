### 🧠 **Definition and Role 🏛️**

A **Certificate Authority (CA)** is a trusted entity that issues, manages, and revokes **[[X.509 Certificate]]**s. They are the core component of the **Public Key Infrastructure (PKI)**.

- **Goal:** To establish a chain of trust between unknown parties on the internet.
    
- **Mechanism:** When a server requests a certificate, the CA verifies the server's identity and then uses its own highly protected **[[Private Key]]** to create a **[[Digital Signature]]** on the **[[X.509 Certificate]]**.
    
- **Trust:** Browsers and operating systems maintain a list of trusted root CAs. If a certificate is signed by a trusted CA, the client implicitly trusts the server's identity and its **[[Public Key]]** for use in the **[[TLS Protocol]]** Handshake.