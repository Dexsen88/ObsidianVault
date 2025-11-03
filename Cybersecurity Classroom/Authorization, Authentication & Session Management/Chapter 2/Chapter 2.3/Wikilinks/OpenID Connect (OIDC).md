**OpenID Connect (OIDC)** is an identity layer built on top of the **[[OAuth 2.0]]** framework. It uses the authorization flow of OAuth to provide verifiable user **[[Authentication]]**.

- **Goal:** To perform secure, delegated **[[Authentication]]** and simplify the implementation of **Single Sign-On (SSO)**.
    
- **Key Component:** OIDC introduces the **[[ID Token]]**. This token is a cryptographically signed JSON Web Token (JWT) that carries essential user identity claims (like user ID, email, name).
    
- **Process:** The client application uses the **[[ID Token]]** to verify the user's identity and then establishes a local **[[Session Token]]** to maintain the user's state.