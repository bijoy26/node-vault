## Suggested Materials

- ### Generate, decode and verify JSON Web Tokens - [jwt.io](https://jwt.io/)
- ### RFC 7519 - [link](https://tools.ietf.org/html/rfc7519)
- ### JSON Web Token Claims - [Auth0 Docs](https://auth0.com/docs/tokens/json-web-tokens/json-web-token-claims)
- ### Package jsonwebtoken for NodeJS - [Github Repo](https://github.com/auth0/node-jsonwebtoken)

## JWT Claims

JSON web tokens (JWTs) claims are pieces of information asserted about a subject.
Generally, when we talk about a claim in the context of a JWT, we are referring to the **name (or key).** For example, the following JSON object contains three claims (sub, name, admin) -

```
 {
      "sub": "1234567890",
      "name": "John Doe",
      "admin": true
 }
```

Two types of JWT claims: 1. **Reserved:** Claims defined by the JWT specification to ensure interoperability with third-party, or external, applications. 2. **Custom:** Claims that you define yourself. Name these claims carefully, such as through namespacing (which Auth0 requires), to avoid collision with reserved claims or other custom claims.

## Reserved Tokens

The JWT specification defines _seven reserved claims_ that are not required, but are recommended to allow interoperability with third-party applications. These are:

1. iss (issuer): Issuer of the JWT
1. sub (subject): Subject of the JWT (the user)
1. aud (audience): Recipient for which the JWT is intended
1. exp (expiration time): Time after which the JWT expires
1. nbf (not before time): Time before which the JWT must not be accepted for processing
1. iat (issued at time): Time at which the JWT was issued; can be used to determine age of the JWT
1. jti (JWT ID): Unique identifier; can be used to prevent the JWT from being replayed (allows a token to be used only once)

### JWT Token need to be send on request header using the format "Authorization: Bearer [token]" or else it will return UnauthorizedError
