# Integration Models for CHIPS Accounts

CHIPS Payment Network Integrators can create an ecosystem of CHIPS Accounts under one of the following models.

## Mediator Model
Mediators onboard CHIPS Accounts with the following features and capabilities:
* Mediators can deposit funds into Trustlink's bank account and notify the CHIPS Payment Network to allocate the funds to a specific CHIPS Account. See [CHIPS Money SSI Account Funding][post-chips-money-ssi-bank-deposits-notifications]
* Mediators can manage user authentication in their system and use the CHIPS Payment Network as a transaction engine. Instructions from the users are thus proxies to CHIPS. See []

Mediators are also referred to as SSI Integrators. SSI refers to the authentication method used. See [CHIPS Basic Secured System Interface][docs-chips-bssi-auth]


## Referrer Model



[post-chips-money-ssi-bank-deposits-notifications]: ../reference/sandbox-chips-money-ssi/swagger.json/paths/~1bank~1deposits~1notifications/post
[docs-chips-bssi-auth]: ./1-CHIPS-Authentication-and-Authorization/20-CHIPS-Basic-Secured-System-Interface-Authentication.md