**🌟 Aisha’s Secret Message**
![[Aisha's Secret Message.png]]
Aisha wanted to send a secret message to Elena, but she was worried that their communications channel might be monitored. She knew she needed to scramble the data using [[Encryption]], but she didn't know which method to choose.

Elena: “You have two main choices. One is fast, but requires a secret key exchange; the other is slower, but uses two public keys and solves the key exchange problem. Security depends on the strength of the algorithm and the secrecy of the key.”

### 🧠 **Symmetric Encryption (Secret-Key)**

**[[Symmetric Encryption]]** uses a **single, shared secret key** for both the encryption of plaintext (readable data) and the decryption of ciphertext (scrambled data).

- **Mechanism:** The same key ($K$) is used by both the sender and the receiver. The algorithm is often fast and efficient. The most common standard is **AES (Advanced Encryption Standard)**.
    
- **Challenge:** The sender and receiver must agree on and securely exchange the secret key beforehand. If the key is intercepted, all communications are compromised. This is the **key exchange problem**.
    
- **Use Case:** Ideal for encrypting bulk data, such as large files or the entire contents of a hard drive (**Data at Rest**).
    

### 🧠 **Asymmetric Encryption (Public-Key)**

**[[Asymmetric Encryption]]** (also known as Public-Key Cryptography) uses a **pair of mathematically related keys**: a **[[Public Key]]** and a **[[Private Key]]**.

- **Mechanism:**
    
    - The **[[Public Key]]** is shared widely and is used _only_ for **encryption**.
        
    - The **[[Private Key]]** is kept secret by the owner and is used _only_ for **decryption**.
        
    - Data encrypted with the public key can _only_ be decrypted with the matching private key.
        
- **Advantage (Solves Key Exchange):** Elena shares her **[[Public Key]]** openly. Aisha uses it to encrypt the message. Only Elena, who possesses the matching **[[Private Key]]**, can decrypt it.
    
- **Disadvantage:** Asymmetric algorithms (like **RSA**) are significantly slower and more computationally intensive than symmetric ones.
    

### 💡 **Hybrid Cryptography (Best of Both)**

![[Hybrid Cryptography.png]]
In practice, a **[[Hybrid Cryptosystem]]** is used for secure communications (like TLS/HTTPS):

1. **Asymmetric** is used first to securely exchange a **[[Symmetric Key]]**.
    
2. **Symmetric** is then used to encrypt the actual bulk data, leveraging its speed.

### 🧩 **Mini Quiz – Chapter 1.1**

**Q:** An application needs to encrypt millions of customer records stored on a hard drive. Which encryption type is the most appropriate for this task, and why?

A) **[[Asymmetric Encryption]]** because the **[[Public Key]]** can be stored publicly.

B) **[[Symmetric Encryption]]** because it is significantly faster and more efficient for encrypting bulk data. 

C) **[[Hybrid Cryptosystem]]** because it provides maximum **[[Defense in Depth]]**.

D) **[[Public Key]]** encryption because it solves the key exchange problem.

Click here to view the answer : [[Chapter 1.1 Answer - Cryptography]]

### 🎯 **Learning Objectives – Chapter 1.1**

By the end of this sub-chapter, you should be able to:

- Define and distinguish between **[[Symmetric Encryption]]** and **[[Asymmetric Encryption]]**.
    
- Understand the key exchange challenge inherent in symmetric cryptography.
    
- Explain the role of the **[[Public Key]]** and **[[Private Key]]** pair.
    
- Describe how a **[[Hybrid Cryptosystem]]** combines the speed and security of both methods.