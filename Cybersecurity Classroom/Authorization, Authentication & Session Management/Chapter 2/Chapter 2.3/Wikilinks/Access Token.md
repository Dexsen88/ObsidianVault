### 🧠 **Definition and Purpose 🗝️**

The **Access Token** is a credential issued to a client application in the **[[OAuth 2.0]]** flow. It is used to access protected resources on behalf of the user from the resource server.

- **Authorization Role:** This token represents the specific **[[Authorization]]** grant—it dictates the actions (scopes) the client can perform and for how long.
    
- **Format:** It is typically a opaque string or a signed JWT.
    
- **Security:** It should have a short expiration time and be protected by the client application as it grants direct access to the user's data. It is not used for **[[Authentication]]** itself; it is only for accessing resources.