---
tags: [CHIPS]
---

# CHIPS API Release Notes

## 4 November 2020

### CHIPS Money API Subscribed Service Intermediary Plugin
We have extented the number of extended banks. As a result we need another way to identify a bank in the APIs. The previous method of passing in the *branchCode* is still valid with a caveat that some banks operate under the same *branchCode*. 

You can now use *bankCode* as a bank identifier in the following calls:
* [GET /bank/payments/fees][chips-money-ssi-bank-payment-fees]


[chips-money-ssi-bank-payment-fees]: ../../reference/sandbox-chips-money-ssi/swagger.json/paths/~1bank~1payments~1fees/get



