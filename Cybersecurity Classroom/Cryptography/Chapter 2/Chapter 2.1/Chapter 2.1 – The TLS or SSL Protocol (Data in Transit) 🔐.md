🌟 **Aisha’s Unlocked Data** 
![[Aisha's Unlocked Data.png]]
Aisha set up a new website but forgot to enable HTTPS, leaving a visible "Not Secure" warning. Elena pointed out that without HTTPS, any login credentials or credit card numbers sent by users were being transmitted as plaintext, violating **[[Confidentiality]]**.

Elena: "HTTPS is the web's standard for securing **Data in Transit**. It uses the **[[TLS Protocol]]** (Transport Layer Security), which is a **[[Hybrid Cryptosystem]]** that solves the key exchange problem and protects against eavesdropping."

### 🧠 **The TLS Handshake: Key Exchange**

The **[[TLS Protocol]]** establishes a secure session through a process called the **Handshake**. This process leverages **[[Asymmetric Encryption]]** to securely exchange a key for **[[Symmetric Encryption]]**:

1. **Identity Verification:** The server first presents its **[[X.509 Certificate]]** (which contains its **[[Public Key]]**) to the client. The client verifies this certificate with a **[[Certificate Authority (CA)]]** to confirm the server's identity. This establishes **Authenticity**.
    
2. **Key Agreement:** The client and server agree on a random **[[Symmetric Key]]** (the session key) and securely exchange it using the server's **[[Public Key]]**.
    
3. **Session Start:** Once the **Symmetric Key** is established, the secure channel is open.
    

### 💡 **Data Transfer and Security**

Once the Handshake is complete, all subsequent data transfer is protected by three cryptographic mechanisms:

- **[[Confidentiality]]**: Achieved via high-speed **[[Symmetric Encryption]]** using the exchanged session key (e.g., AES-256).
    
- **[[Integrity]]**: Achieved by using a **[[Cryptographic Hash]]** (e.g., HMAC-SHA256) on every packet to ensure the data has not been modified in transit.
    
- **Authenticity**: Ensured by the initial verification of the **[[X.509 Certificate]]** and its **[[Digital Signature]]**.
    

### 🎯 **Encryption in Transit**

![[Encryption In Transit.png]]
The protection of **Data in Transit** (data actively moving over a network) is often considered the most critical application of cryptography, as networks are fundamentally untrusted spaces. The **[[TLS Protocol]]** is the **Mandatory Security Control** for all public web traffic.

### 🧩 **Mini Quiz – Chapter 2.1**

**Q:** What is the primary security function of the **[[X.509 Certificate]]** during the **[[TLS Protocol]]** Handshake?

A) It contains the **[[Symmetric Key]]** used for encrypting the bulk data.

B) **It verifies the server’s identity using a [[Certificate Authority (CA)]] and contains the [[Public Key]] needed to start the key exchange.** 

C) It contains the **[[Private Key]]** that the client uses to decrypt the session key.

D) It is a **[[Cryptographic Hash]]** of the client's credentials for **[[Authentication]]**.

View the answer here : [[Chapter 2.1 - Answer - Cryptography]]

### 🎯 **Learning Objectives – Chapter 2.1**

By the end of this sub-chapter, you should be able to:

- Explain the role of the **[[TLS Protocol]]** in securing **Data in Transit**.
    
- Describe the function of the **TLS Handshake** as a **[[Hybrid Cryptosystem]]** key exchange.
    
- Identify the **[[X.509 Certificate]]** and **[[Certificate Authority (CA)]]** as core components of trust.