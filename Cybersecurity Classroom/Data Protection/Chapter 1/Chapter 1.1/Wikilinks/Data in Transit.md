### 🧠 **Definition and Protection 🌐**

**Data in Transit** (or Data in Motion) refers to data that is actively moving from one location to another across a network. This includes transfers over the public internet, internal networks, or across a wide area network (WAN).

- **Goal:** To protect the **[[Confidentiality]]** and **[[Integrity]]** of the data from eavesdropping and tampering while it travels across untrusted network boundaries.
    
- **Standard Control:** The mandatory security control for Data in Transit over the internet is the **[[TLS Protocol]]** (Transport Layer Security, used with HTTPS). TLS provides **[[Symmetric Encryption]]** for speed and uses **[[Digital Signature]]**s (via **[[X.509 Certificate]]**s) for server **Authenticity**.
    
- **Risk:** The most common threat is network eavesdropping or Man-in-the-Middle attacks if the connection is not properly encrypted.