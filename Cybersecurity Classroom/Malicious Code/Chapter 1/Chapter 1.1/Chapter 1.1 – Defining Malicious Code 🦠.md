**🌟 Aisha’s Phishing Attack**
![[Aisha's Phising Attack.png]]
Aisha received an email attachment labeled "Invoice.exe." Thinking it was a legitimate bill, she opened it. The file immediately began encrypting all the files on her hard drive, demanding a Bitcoin ransom to decrypt them.

Elena: “That was a **[[Ransomware]]** attack delivered via a **[[Trojan Horse]]**. It’s a classic example of **[[Malware]]**. Understanding the different types of malicious code is the first step in building a defense-in-depth strategy, as each requires a slightly different mitigation.”

### 🧠 **Malware: The Umbrella Term**

**[[Malware]]** (Malicious Software) is the overarching term for any software intentionally designed to cause damage to, gain unauthorized access to, or perform unwanted actions on a computer system. All specific types (like viruses, worms, and ransomware) fall under this category.

- **Goal:** To violate the security pillars, primarily **[[Confidentiality]]** (data theft), **[[Integrity]]** (data modification), and **[[Availability]]** (**[[Denial of Service (DoS)]]** or system crash).
    
- **Delivery:** Often delivered via social engineering (**[[Phishing]]**), exploiting software vulnerabilities, or piggybacking on legitimate software.
    

### 💡 **Core Types of Malicious Code**

Malware is typically categorized by its behavior and method of spreading:

|**Type**|**Spreading Mechanism**|**Primary Goal**|
|---|---|---|
|**[[Virus]]**|Requires a host file/program; requires human execution (e.g., clicking an infected .exe) to spread.|Data corruption, system damage.|
|**[[Worm]]**|**Self-propagating**; actively scans networks and spreads without human interaction.|Network saturation, **[[Denial of Service (DoS)]]**.|
|**[[Trojan Horse]]**|Disguised as legitimate software; tricks the user into installing it.|Creating a backdoor, delivering a payload (like **[[Ransomware]]**).|
|**[[Ransomware]]**|Encrypts files/systems and demands a ransom for the decryption key.|Financial extortion.|

### 🎯 **Defense-in-Depth for Malware**
![[Defense-inDepth for Malware.png]]

No single defense works against all **[[Malware]]**. A layered approach is mandatory:

1. **Prevent Delivery:** Use email filters against **[[Phishing]]** and update firewalls.
    
2. **Prevent Execution:** Use up-to-date anti-malware (anti-virus) software.
    
3. **Minimize Damage:** Implement the **[[Principle of Least Privilege]]** for user accounts to limit where the malware can spread, and enforce a robust backup/recovery plan (for **[[Ransomware]]**).
    

---

### 🧩 **Mini Quiz – Chapter 1.1**

**Q:** An attacker successfully infects a network by exploiting a vulnerability in an unpatched server. The malicious code then actively scans and propagates itself to hundreds of other systems _without_ any user interaction. What specific type of **[[Malware]]** is this?

A) **[[Trojan Horse]]**.

B) **[[Virus]]**.

C) **[[Ransomware]]**.

D) **[[Worm]]**. 

Click here to view the answer : [[Chapter 1.1 - Answer - Malicious Code]]

---

### 🎯 **Learning Objectives – Chapter 1.1**

By the end of this sub-chapter, you should be able to:

- Define **[[Malware]]** as the umbrella term for malicious code.
    
- Differentiate the spreading mechanisms and goals of a **[[Virus]]**, **[[Worm]]**, and **[[Trojan Horse]]**.
    
- Understand how **[[Ransomware]]** violates the **[[Availability]]** pillar.