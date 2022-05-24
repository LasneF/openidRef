
# Authorization CodeFlow

## Context , usage , purpose 


### Scenario 


> The challenges , is how do I to grant access to a 3rd party to my data owned.

here is one solution 
![buildingblocks http](comicsAuthCodeFlowPirate.png)


Here as John gives its credential to PirateLoan , PirateLoan has then full access to his bank, it s definitely not a good solution. 

Topic is now to be able to share an 'scoped' access to a specified 3rd party , in a secure maner. 
Authorization code flow solves this by introducing a trusted party . 

![buildingblocks http](comicsAuthCodeFlowExplained.png)


> Solution is based on bi mutual trust : 
> * End user must have access to the data owner (here bank)  via a secret (login / password ) 
> * 3rd party (here coolLoan ) must be registered to data owner (bank) via a client id / secret for a given scope  
> * End user knows both party bank and cool loan and allows exchange of information for a given scope for doing that he must be known (ie logged)

Notice that most of the time the *identity provider* and the *provider 

### Mapping with OpenIdConnect Authorization Code flow.  



### Usage 


[RFC6749 section 4.4](https://datatracker.ietf.org/doc/html/rfc6749#section-4.1)


## Flow Diagram 

![ClientFlow](https://www.plantuml.com/plantuml/png/TP91Qnin48Nl-XMFFSLqJG-z6MhYcb9I0WvhkvTIYYnDRE6rj1rf4znVtrc99TsqsPDcvxrFRoJTngGvzPTMAMrIO5GDnT2p8MoUFJ7Uusiu-GewejceJiJEk4xxX6eVfRywaa-vlLyfDH5yOFjTGRwFmn93wvhhkNnvKLNh4Dhxe7rLgHzJzwfF9up-eGZiVklaWiUM-8duDOgilHRCXBCBP_8Z9nSF79wS_HTma1tYVmWDHljuDcyaE6X_BX5qduBlBmVHgFqAysKPPu58ta9Ffc7wrLDCk66oZica6gPrvDDFPsj44ph2J0t--R9GKAhvKj0BjE7elEYOoAjc8tlbtv4IZ205v7GhALv2T7qyeO_4q7wubnYV0zj2nUXV1n_5Y-q87ZjO6KDTcixLKEm60y8ZJ76-5Nc1SL2a8EkZYuda5unksuCsP-2TC2pbpCFBMUJMYstVtAD8eAGlAVAzYkvXiztXfXpVdKMDTLvkoJ0br7yZxkf2g75aBOUThXrDRoRtPogp9JbA56qCnLXsb1GDFJB5KwdL815b8xeldtUGJdamhnxm9z9CZ88gf1bKCryEnc-wTLOdGih81kFUM32bdZtIYS1Ko4gfM_AslxH_0000)

[edit in plan UML](https://www.plantuml.com/plantuml/uml/TP91Qnin48Nl-XMFFSLqJG-z6MhYcb9I0WvhkvTIYYnDRE6rj1rf4znVtrc99TsqsPDcvxrFRoJTngGvzPTMAMrIO5GDnT2p8MoUFJ7Uusiu-GewejceJiJEk4xxX6eVfRywaa-vlLyfDH5yOFjTGRwFmn93wvhhkNnvKLNh4Dhxe7rLgHzJzwfF9up-eGZiVklaWiUM-8duDOgilHRCXBCBP_8Z9nSF79wS_HTma1tYVmWDHljuDcyaE6X_BX5qduBlBmVHgFqAysKPPu58ta9Ffc7wrLDCk66oZica6gPrvDDFPsj44ph2J0t--R9GKAhvKj0BjE7elEYOoAjc8tlbtv4IZ205v7GhALv2T7qyeO_4q7wubnYV0zj2nUXV1n_5Y-q87ZjO6KDTcixLKEm60y8ZJ76-5Nc1SL2a8EkZYuda5unksuCsP-2TC2pbpCFBMUJMYstVtAD8eAGlAVAzYkvXiztXfXpVdKMDTLvkoJ0br7yZxkf2g75aBOUThXrDRoRtPogp9JbA56qCnLXsb1GDFJB5KwdL815b8xeldtUGJdamhnxm9z9CZ88gf1bKCryEnc-wTLOdGih81kFUM32bdZtIYS1Ko4gfM_AslxH_0000)

## Explanation 

### 1. request token 


## plan UML source code of the flow

