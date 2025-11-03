### 🧠 **Definition and Purpose 📝**

The **ID Token** is a security token introduced by the **[[OpenID Connect (OIDC)]]** protocol. It is specifically designed to prove the identity of the user.

- **Authentication Role:** This token is the proof of successful **[[Authentication]]**. It is a signed JSON Web Token (JWT) that contains verifiable **claims** about the end-user, such as their unique identifier (`sub`), name, and email.
    
- **Security:** Because the token is signed by the identity provider, the client application can cryptographically verify its authenticity and trust the identity claims within.
    
- **Usage:** After validating the **ID Token**, the client application uses the identity claims to create a local **[[Session Token]]** and grant access to the user based on their verified identity.