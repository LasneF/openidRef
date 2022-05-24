
# Authorization CodeFlow

## Context , usage , purpose 



> The definitive challenges of client credentials , is how do I to grant access to a 3rd party to my data owned in without sharing my password 


> Solution is based on bi mutual trust.
> End user must have access to the data owner (here bank)  via a secret (login / password ) 
> 3rd party (here coolLoan ) must be registered to data owner (bank) via a client id / secret for a given scope  
> End user knows both party bank and cool loan and allows exchange of information for a given scope for doing that he must be known (ie logged)


![buildingblocks http](comicsClientCredential.png)

### Scenario 


https://api.fusionfabric.cloud/login/v1/sandbox-consumer/oidc/authorize?scope=openid&state=kikhqU7DI78YStQa77ugtfAMzwugM0noG5xmcQ5TtA0.s7_3WtmDNWs.9a185488-fbae-4a28-8e87-13fd348c8755&response_type=code&client_id=sandbox-broker&redirect_uri=https%3A%2F%2Fapi.fusionfabric.cloud%2Flogin%2Fv1%2Fsandbox%2Foidc%2Fbroker%2Fconsumer%2Fendpoint&nonce=qmhr_WrJ0QStNiHlhwsLsA


### Usage 


[RFC6749 section 4.4](https://datatracker.ietf.org/doc/html/rfc6749#section-4.1)


## Flow Diagram 

![ClientFlow](https://)

[edit in plan UML](https://

## Explanation 

### 1. request token 


## plan UML source code of the flow

