### 🧠 **Definition and Purpose 📄**

An **X.509 Certificate** (or Digital Certificate) is a cryptographically signed document used to verify a public key's ownership. It is the digital equivalent of an ID or passport for a server or individual.

- **Content:** It contains the subject's identity (e.g., website domain name) and the subject's **[[Public Key]]**.
    
- **Trust Mechanism:** The certificate is **[[Digital Signature]]**d by a trusted third party, the **[[Certificate Authority (CA)]]**. This signature allows the client to confirm the server's identity and trust the **[[Public Key]]** provided.
    
- **Role in TLS:** It is presented by the server during the **[[TLS Protocol]]** Handshake to establish the server's **Authenticity**.