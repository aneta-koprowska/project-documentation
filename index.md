# Payment process documentation

## Persona

__Name__: John Goodson

![dev](/img/dev.jpeg) 

__Position__: Developer   

__Experience level__: mid  

__Pain points__: doesn't like using documentation


## Potential documents

| Document        | Format           | Distribution  |
| ------------- |:-------------:| -----:|
| Inhouse knowledgebase      | online | Cloud-based confluence |


- Confluence page in cloud-based Confluence space
- part of inhouse software documentation knowledgebase
  


### Table of Contents
1. System Overview
2. Involved Components
3. Process
4. Glossary



## Payment processing outline
1. ### Involved components:
   
        Platform (internal) → external API (public) → payment provider (external)

2. ### Keywords: 

- __payments statuses in platform__ (*new*, *approved*, *scheduled*, *in flight*, *processed*)

- __external API endpoints, payment provider API endpoints__

- __payment statuses in payment provider__ (*success*, *query*, *fail*)

- __status mapping__ between platform and payment provider

    cron jobs, database objects, synchronization

3. ### Process

- scheduled payments are sent from platform to payment provider via company external API

- correct payments are approved by the provider and paid out to workers, updated to status success

- payments with questionable status are marked as query

- unsuccessful payments are marked as fail

- payment statuses are synchronized between systems by consistent updating of payment statuses on the side of the platform

 