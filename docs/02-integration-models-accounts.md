# Integration Models for CHIPS Accounts

CHIPS Payment Network Integrators can create an ecosystem of CHIPS Accounts under one of the following models.

## Mediator Model
Mediators onboard CHIPS Accounts into an ecosystem that is primarily focused on building a cashless ecosystem. The main aim of this model is to facilitate transactions. 

Mediated accounts have the following features and capabilities:
Mediators can deposit funds into Trustlink's bank account and notify the CHIPS Payment Network to allocate the funds to a specific CHIPS Account. See [CHIPS Money SSI Account Funding][post-chips-money-ssi-bank-deposits-notifications]
Mediators can manage user authentication in their system and use the CHIPS Payment Network as a transaction engine. Instructions from the users are thus proxies to CHIPS. 
Mediators have a generic API to enable transfers between accounts in the CHIPS Payment Network. See [CHIPS Money SSI Account Transfer][post-chips-money-ssi-transfers]. T&Cs apply.
Mediators can initiate EFT payments to most of the South African Banks. See [CHIPS Money SSI Bank Payments][post-chips-money-ssi-bank-payments]. T&Cs apply.

The documentation also refers to Mediators as SSI Integrators. SSI refers to the authentication method used. See [CHIPS Basic Secured System Interface][docs-chips-bssi-auth].
Regarding transaction authorization, there is also a [BSSI Hybrid] model that a Mediator can implement. 

## Referrer Model
Referrers are CHIPS Merchants, registered on the [CHIPS miBusiness platform][web-chips-mibusiness-landingpage], that want to build a CHIPS Accounts ecosystem to support digital payments for their services and strengthen their brand.

Referrer accounts are the same as any other [CHIPS Money Manager][web-chips-individual-landigpage] account. Being a referrer integrator allows embedding CHIPS Payments features into your mobile app and digital channels, allowing your referred ecosystem accounts to pay for your services.

## Point of Sale Model
[CHIPS Merchants][web-chips-mibusiness-landingpage], can build point of sale solutions into their payment channel.


[post-chips-money-ssi-bank-deposits-notifications]: ../reference/sandbox-chips-money-ssi/swagger.json/paths/~1bank~1deposits~1notifications/post
[post-chips-money-ssi-transfer]: ../reference/sandbox-chips-money-ssi/swagger.json/path/~1transfers/post
[post-chips-money-ssi-bank-payments]: ../reference/sandbox-chips-money-ssi/swagger.json/paths/~1bank~1payments/post
[docs-chips-bssi-auth]: ./1-CHIPS-Authentication-and-Authorization/20-CHIPS-Basic-Secured-System-Interface-Authentication.md

[web-chips-mibusiness-landingpage]: https://chips.co.za/payment-network/index.php/businesses
[web-chips-individual-landigpage]: https://www.chips.co.za/payment-network/index.php/chips-for-individuals
