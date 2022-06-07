

OpenID connect defines a  URL that allow to retreive the configuration 

it is accessible on this normalized endpoint using HTTP GET, and will reply a JSON 

GET www.example.com/.well-known/openid-configuration 
  

this configuration contains  

* issuer : that represents which domain is the issuer of the security 
* token-endpoint : the end point used in the Oauth2 flow to manage token 




https://accounts.google.com/.well-known/openid-configuration 




```
{
    issuer: "https://accounts.google.com",
    authorization_endpoint: "https://accounts.google.com/o/oauth2/v2/auth",
    device_authorization_endpoint: "https://oauth2.googleapis.com/device/code",
    token_endpoint: "https://oauth2.googleapis.com/token",
    userinfo_endpoint: "https://openidconnect.googleapis.com/v1/userinfo",
    revocation_endpoint: "https://oauth2.googleapis.com/revoke",
    jwks_uri: "https://www.googleapis.com/oauth2/v3/certs",
    response_types_supported: [  "code" , "token",  "id_token",  "code token",  "code id_token", "token id_token", "code token id_token", "none" ],
    subject_types_supported: [ "public" ],
    id_token_signing_alg_values_supported: [ "RS256" ],
    scopes_supported: [ "openid", "email", "profile"],
    token_endpoint_auth_methods_supported: [ "client_secret_post", "client_secret_basic" ],
    claims_supported: [ "aud", "email", "email_verified", "exp",  "family_name", "given_name", "iat", "iss", "locale", "name", "picture", "sub" ],
    code_challenge_methods_supported: [ "plain", "S256" ],
    grant_types_supported: [ "authorization_code", "refresh_token", "urn:ietf:params:oauth:grant-type:device_code", "urn:ietf:params:oauth:grant-type:jwt-bearer"]
}
```
