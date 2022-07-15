# API Principles to release API

  

-   **Business Driven / Usefull**
    -   API must comes with use cases
    -   API must come with a purpose : a 3 / 4 lines moto of the API products
    -   API should comes with some key features
    -   Address a clear personna, and population
    -   Defines KPI in term of performance (call duration) , number of call expected
    -   Best if API is sponsored by 1 client ... or even better 2

-   **Documented**
    -   API must be readable , explained , well documented
        -   Marketing high level architecture
        -   Tell me What is it, tell me what it does , but not how it works inside . Describe behaviour only
        -   **Sequence diagram beeing a key element**
            -   Who is Calling What with a high level content
            -   How call are done B2B / B2C
            -   It is synchronous , Asynchronous , Does a call can get notification of progress
            -   Contains all personna of the use cases from end to end (not only including the involve client and server but all persona involved in the interaction )
    -   Follow industry standard , either informal either formal one like ISO20022, RFC x for country / currency / time , etc . Any term should be Google searchable , and so be main stream
    -   avoid accronym , in field name , enumeration etc
    -   keep the mindset How do a SP provider would do to make it happen , does he has all the mandatory pieces

  

-   Following  **Keep it Simple**  paradigm. The successful adoption of APIs is determined by API developers’ experience. The more simple the more adoption.
    
    _Implications_
    
    Open API designers MUST assume that the API audience are:
    
    -   NOT product experts - do NOT use product specific vocabulary.
    -   NOT Business experts - do use known Business terminology.
    -   NOT Technical experts - do NOT use technical jargon.
    -   The less the Better , expose the Minimal required set

-   **Testable**
    -   API must be testable => Sandbox / mock

  

-   Follow Ingenico API  **Guide lines**  / Style Guide
    -   Follow HTTP principle and semantics (, http methods , headers , error code )
    -   Should follow REST model targetting leve 2 of the Richarson Maturity level
        -   Ressource driven : path Host / domain / version / Resource

  

-   **Decoupled**  
    -   API must not contains client specific content or be design for a given client, need to think about the next one
    -   API must not contains implementation specific details , think that API client and implementation can be replaced
    -   API should not be IHM driven
    -   not be linked to a given implementation language / support

  

-   **Easy to us**e as stand alone as well in conjonction to others API
    -   Consistent with other API , lowering overalap at its minimal
    -   Coherent
        -   Re use existing building block over and over, do not duplicate structure => Modular
    -   Unambiguous
    -   Intuitive to use
    -   Consistent (in behaviour , in description)
    -   API need to be "fully" discoverable (all the endpoint are reachable with calling another one, i can create a resource, i can discover all required ids , values for string and so on)

  

-   **Designed to handle Confidential Data**
    -   All confidential data (for PCI DSS or GDPR for example) should be identified during the design phase
    -   An explicit notation should identify these data in the API documentation so that the caller or the implementer knows he is handling sensitive information with an obligation to follow specific rules.
    -   The data flow documents required for PCI or GDPR certifications are updated with the corresponding data flow when the API is approved

  

-   **Ready for future**
    -   API definition should be in the spirit of evolution (using array instead of single value for instance , string vs enum etc )
    -   Compliant with Customization paradigm

  

-   **Versionned**
    -   semantic versionning , with major as breaking change for client

-   **Compliant** : clearly identify compliance concern such as copyright , GDPR , PCI

  

-   **Auditable :** defines metrics to measure to bill , to validate correct behaviour, defines alerts threshold

  

-   **Supported**  : defines SLAcceptance , SLObjective ( in term of performance / support etc, process of escalation, proper contact defined

  

-   **Secured** : define B2B , B2C , Device only etc security definition , Threat model analysis , compliant with OWASP top 10 especially limiting the exposure`enter code here`
