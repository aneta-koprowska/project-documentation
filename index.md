# Payment process documentation


## Payment processing outline
1. Involved components:
   
__Platform__ (*internal*) → __external API__ (*public*) → __payment provider__ (*external*)

2. Keywords: 

- __payments statuses in platform__ (*new*, *approved*, *scheduled*, *in flight*, *processed*)

- __external API endpoints, payment provider API endpoints__

- __payment statuses in payment provider__ (*success*, *query*, *fail*)

- __status mapping__ between platform and payment provider

cron jobs, database objects, synchronization

1. Process
scheduled payments are sent from platform to payment provider via company external API

correct payments are approved by the provider and paid out to workers, updated to status success

payments with questionable status are marked as query

unsuccessful payments are marked as fail

payment statuses are synchronized between systems by consistent updating of payment statuses on the side of the platform

 