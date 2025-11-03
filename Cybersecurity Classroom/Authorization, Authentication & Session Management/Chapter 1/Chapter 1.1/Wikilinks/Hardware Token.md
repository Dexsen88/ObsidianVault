A **Hardware Token** is a physical device used to prove the **Possession Factor** of authentication. It generates or stores cryptographic information required to authenticate a user.

- **Mechanism:** It often generates a **One-Time Password (OTP)** using an algorithm synchronized with the server's clock. This code is only valid for a short period (typically 30-60 seconds).
    
- **Security Benefit:** It is much stronger than a mobile app or email code because it is a dedicated, tamper-resistant device. It enforces **[[Multi-Factor Authentication (MFA)]]**, making it extremely difficult for an attacker who only has a stolen password to gain access.
    
- **Example:** A Yubikey, which can use protocols like FIDO2 or generate OTPs.