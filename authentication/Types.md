| Authentication Method  | Description                                                                 | Use Case                                                        | Where to Send Token/API Key |
|------------------------|-----------------------------------------------------------------------------|-----------------------------------------------------------------|-----------------------------|
| **Basic Authentication** | Sends a username and password with each request (Base64 encoded).          | Suitable for simple, low-security applications or testing.      | **Header**: `Authorization: Basic <Base64_encoded_credentials>` |
| **OAuth 2.0**            | Delegated authorization, allowing third-party apps to access resources on behalf of a user. | Ideal for applications requiring user authentication with third-party services (e.g., Google, Facebook). | **Header**: `Authorization: Bearer <OAuth_token>` |
| **JWT (JSON Web Token)** | Token-based authentication where users receive a token after logging in.  | Common for stateless API services and Single Page Applications (SPA). Typically sent as a **Bearer token** in the **Authorization header**: `Authorization: Bearer <JWT_token_here>`. | **Header**: `Authorization: Bearer <JWT_token>` |
| **API Key**              | A unique key given to the client for authenticating API requests.           | Used in public or semi-public APIs, like weather or payment gateway APIs. | **Header**: `Authorization: ApiKey <API_key>` or **Query Params**: `?apikey=<API_key>` |
| **Bearer Token**         | A token sent in the Authorization header to authenticate requests.         | Often used with OAuth 2.0 or JWT for secure API access.         | **Header**: `Authorization: Bearer <Token>` |
| **Digest Authentication**| A more secure method where the password is hashed and sent with each request. | Used in environments where HTTPS is not possible or for higher security than Basic Authentication. | **Header**: `Authorization: Digest <digest_info>` |
| **HMAC (Hash-based Message Authentication Code)** | Uses a secret key and hash function to verify both the authenticity of the message and its integrity. | Used for secure communication between trusted servers or APIs. | **Header**: Usually in a custom header like `X-Signature` along with other signature-related information. |
| **LDAP Authentication**  | Uses the Lightweight Directory Access Protocol to authenticate against a directory service. | Common in enterprise environments for centralized user authentication. | **Body**: Typically sent as part of the LDAP request payload. |
| **SAML (Security Assertion Markup Language)** | XML-based protocol for exchanging authentication data between identity providers and service providers. | Often used in Single Sign-On (SSO) systems in enterprise environments. | **Body**: SAML tokens are sent within the body of the SAML request/response. |
| **OAuth 1.0a**           | An older version of OAuth that involves more complex signatures for API authentication. | Legacy systems or services still using OAuth 1.0a.               | **Header**: `Authorization: OAuth <oauth_params>` |


### Notes:
- **OAuth 2.0** and **JWT** are among the most common methods in modern APIs, especially for RESTful services that require scalability and user authentication.
- **API Keys** are often used for non-user-specific, public APIs.
- **HMAC** is useful for ensuring message integrity and security without revealing the secret key.
