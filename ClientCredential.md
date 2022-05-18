
# Client Credential


## Context , usage , purpose 

Client credential flow is designed handling machine to machine communication. 
Client must be able have access securely to sentive information such as the clientId and client secret 
those used to to store in a key vault. 

Client Credential flow is describe in this [RFC6749 section 4.4](https://datatracker.ietf.org/doc/html/rfc6749#section-4.4)

This flow does not suits for Web client, or mobile interaction as those sentitive credentials can be stolen. 



## Flow Diagram 

![ClientFlow](https://www.plantuml.com/plantuml/png/VP4zImGn48Rx_8h1Gkx0k-iFb3jIMGaviH6BCHamk9kioSJ2N-ya-u6hu3IxONYUDoyvPSR4fU_K85zl_O21GSEp0fbRq9sdmEsmasa_LpBgHQs81opyjb1dESJalv1z372Xz4dfjmC7lwzGRjkzZVqXUcSF7Dyf_0qmYznGpYLP-iVhaB4QcqP2OYZzAoMbTtVJJOzWwADGPZXRAq9uhB6m6VlUExYPgaCccuYtQkH-29wmyn94i33NCtDfp8m8e-6u2bAwcWoqUw2hdMBhjE6wtYepKdK_hsmCND_YHC79Wtq3)

## Explanation 

### 1. request token 
1st request is done on the **token url**. This URL can be found as part of the OIDC discovery in the field 'token_url'. 
the discovery URL is available for an OIDC server against this [https://authorizationServer/**.well-known/openid-configuration**]() for instance here is the google one 
https://accounts.google.com/.well-known/openid-configuration 

the request must set 
   - grant_type : "client_credential"
   - scope : "openid" is recommended but not mandatory

clientId and client secret can be passed in 2 ways either as basic Oauth2 headers , either as body 

   - as Body : it must use the application/x-www-form-urlencoded Content-type , and set the payload as this content type set meaning grant_type=client_credentials&scope=openid&client_id=openapi-cicd&client_secret=262c6759-fe49-49a5-a5db-a5dfa9d15914

*curl * 
curl --location --request POST 'https://oauth2.sample.com/oidc/token' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-raw 'grant_type=client_credentials&client_id=myClientId&client_secret=myClientSecret'

* HTTP equivalent request *
POST https://oauth2.sample.com/oidc/token
Header
Content-Type: application/x-www-form-urlencoded
grant_type: "client_credentials"
scope: "openid"
client_id: "myClientId"
client_secret: "myClientSecret"

### 2. validating and Issuing a token 

The authorization server validate the matching between clientId, client secret , grant type. The for the given client application if the requested scopes matches (or sub matches) the one declared during the creation of the client application. 

### 3. send the access token

The authorization server return a Json with the content at least below 


   token_type
         REQUIRED.  The type of the token issued as described in
         Section 7.1.  Value is case insensitive.

   expires_in

{
	"access_token": "a JWTAccess Token",
	"expires_in": 300,
	"token_type": "Bearer",
}

### 4. Do API call with the access token

GET api.core.com/account
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
    ""oauth2.sample.com/oidc/token""
]

participant R [
    = Ressurce Server
    ----
    ""api.data.com""
]
autonumber
C-> Oauth : Request Access Token (ClientId , Client secret)
Oauth -> Oauth : Validate ClientId & Client Secret
Oauth --> C : Access Token + meta data 
C -> R  : Read Resource (token)
R--> C  : Resource content
@enduml

```

## Code library and sample

* Java Spring Security : https://www.baeldung.com/spring-webclient-oauth2 





