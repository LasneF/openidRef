
# Client Credential


## Context , usage , purpose 

Client credential flow is designed handling machine to machine communication. 
client must be able have access securely to sentive information such as the clientId and client secret 
those used to to store in a key vault. 

This flow does not suits for Web client, or mobile interaction as those sentitive credentials can be stolen. 



## Flow Diagram 

![ClientFlow](https://www.plantuml.com/plantuml/png/VP4zImGn48Rx_8h1Gkx0k-iFb3jIMGaviH6BCHamk9kioSJ2N-ya-u6hu3IxONYUDoyvPSR4fU_K85zl_O21GSEp0fbRq9sdmEsmasa_LpBgHQs81opyjb1dESJalv1z372Xz4dfjmC7lwzGRjkzZVqXUcSF7Dyf_0qmYznGpYLP-iVhaB4QcqP2OYZzAoMbTtVJJOzWwADGPZXRAq9uhB6m6VlUExYPgaCccuYtQkH-29wmyn94i33NCtDfp8m8e-6u2bAwcWoqUw2hdMBhjE6wtYepKdK_hsmCND_YHC79Wtq3)

## Explanation 

### 1. request token 
1st request is done on the token url. This URL can be found as part of the OIDC discovery in the field 'token_url'.


*curl * 

* HTTP equivalent request *
POST https://api.Auth.com/oidc/token
Header
Content-Type: application/x-www-form-urlencoded
grant_type: "client_credentials"
scope: "openid"
client_id: "myClientUd"
client_secret: "a secret"

### 2. validating and Issuing a token 

### 3. send the access token

as JWT 
{
	"access_token": "a JWTAccess Token",
	"expires_in": 300,
	"scope": "openid Read Write",
	"token_type": "Bearer",
	"id_token": "a JWT Id Token"
}

### 4. Do API call with the access token

GET api.bank.com/account
Header
Authorization: "Bearer JWT Id Token"

### 5. Result of API call

## Flow plan UML flow Code

```
@startuml
participant C [
    = Client
    ----
    """"
]

participant Oauth [
    = Authorization Server
    ----
    ""api.authserver.com/oidc/token""
]

participant R [
    = Ressurce Server
    ----
    ""api.data.com""
]
autonumber
C-> Oauth : Request Access Token (ClientId , Client secret)
Oauth -> Oauth : Validate ClientId & Client Secret
Oauth --> C : Access Token
C -> R  : Read Resource (token)
R--> C  : Resource content
@enduml

```






