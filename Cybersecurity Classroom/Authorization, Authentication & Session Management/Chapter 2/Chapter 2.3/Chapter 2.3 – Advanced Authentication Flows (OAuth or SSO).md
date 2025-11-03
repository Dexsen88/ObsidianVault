🌟 **Aisha’s Third-Party Login** 
![[Aisha's Third-Party Login.png]]
Aisha wanted to allow users to sign in using their Google or GitHub accounts instead of creating a new password. This shift requires understanding how to securely delegate **[[Authentication]]** to a third-party service while still managing **[[Authorization]]** locally.

Elena: "You need a standard protocol for delegated identity. We use **OAuth 2.0** for **Authorization** and **OpenID Connect (OIDC)**, which layers on top of OAuth, for **Authentication**. These are key for Single Sign-On (SSO) and trusting external identity providers."

### 🧠 **OAuth 2.0: Delegation, Not Authentication**

**[[OAuth 2.0]]** is an authorization framework that allows a user to grant a third-party application **limited access** to their resources (like their photos or contact list) without sharing their credentials.

- **Purpose:** It issues an **[[Access Token]]** that is specific to the application and the requested scope (permissions).
    
- **Crucial Point:** OAuth 2.0 is designed for **Authorization** (What you can do), not **Authentication** (Who you are). You cannot log a user in based on an OAuth Access Token alone.
    

### 💡 **OpenID Connect (OIDC): The Identity Layer**

**[[OpenID Connect (OIDC)]]** is a simple identity layer built on top of **[[OAuth 2.0]]**. It adds the necessary components to perform secure user **[[Authentication]]** and identity transfer.

- **Key Component:** OIDC introduces the **[[ID Token]]**. This is a cryptographically signed JSON Web Token (JWT) that contains claims about the authenticated user (e.g., name, email, user ID).
    
- **Flow:** The client application receives the **[[ID Token]]**, which it can verify cryptographically. If the signature is valid, the application can trust the identity and establish a local **[[Session Token]]**.
    

### 🎯 **Single Sign-On (SSO)**
![[SSO.png]]

These protocols enable **Single Sign-On (SSO)**, which is an **[[Authentication]]** scheme that allows a user to log in with a single set of credentials to multiple, independent software systems.

- **Benefit:** It improves **[[Availability]]** and user experience while centralizing password management at a dedicated, high-security **Identity Provider** (IdP), reducing the risk of users having weak passwords across multiple applications.

### 🧩 **Mini Quiz – Chapter 2.3**

**Q:** When using Google to sign in to a third-party app, which component is strictly required to verify the user's _identity_ and establish a local session?

A) The **[[Access Token]]** (provided by **[[OAuth 2.0]]**).

B) The **[[Session Token]]** (provided by the user's browser).

C) The [[ID Token]] (provided by [[OpenID Connect (OIDC)]]). 

D) The **[[Hardware Token]]** (required by **[[Multi-Factor Authentication (MFA)]]**).

Click here to view the answer : [[Chapter 2.3 - Answer AAS]]

### 🎯 **Learning Objectives – Chapter 2.3**

By the end of this sub-chapter, you should be able to:

- Distinguish the primary functions of **[[OAuth 2.0]]** (Authorization) and **[[OpenID Connect (OIDC)]]** (Authentication).
    
- Identify the **[[Access Token]]** and the **[[ID Token]]** as the two critical tokens in a delegated flow.
    
- Define **Single Sign-On (SSO)** and explain its benefits to security and **[[Availability]]**.