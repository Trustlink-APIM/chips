---
tags: [CHIPS]
---

# CHIPS API Release Notes

## 4 November 2020

### CHIPS Money API Subscribed Service Intermediary Plugin
![Enhancement][relnotes-enhancement-logo]

We have extended the number of supported banks. As a result, we needed another way to identify a bank in the APIs. The previous method of passing in the *branchCode* is still valid with a caveat that some banks operate under the same *branchCode*. You now have the option to pass in *branchCode* OR *bankCode* as bank identifier in the following API calls:
* [GET /bank/payments/fees][chips-money-ssi-bank-payments-fees]
* [POST /bank/payments][chips-money-ssi-bank-payments]

![New Feature][relnotes-new-feature-logo]
We exposed a new end-point to get a list of banks. The list will have the *bankCode* values required for the above end-points.
* [GET /banks][chips-money-ssi-banks]

![Documentation][relnotes-documentation-logo]
Please see some more info on the *bankCode* in the [GET /bank/payments/fees][chips-money-ssi-bank-payments-fees] end-point.

### CHIPS Money API

![New Feature][relnotes-new-feature-logo]
We exposed the [POST /payments/purchases/multi-payments][chips-money-payments-purchases-multi-payments] end-point. The end-point facilitates splitting up a single payment between multiple receivers. The feature is good for implementing immediate payment splits between the reseller, commission earners, delivery service, franchiser, franchisee etc., at the time of the purchase.

<!-- documentation icons -->
[relnotes-enhancement-logo]: https://marketplace.trustlinkhosting.com/images/Trustlink/RelNotesEnhancement.png
[relnotes-new-feature-logo]: https://marketplace.trustlinkhosting.com/images/Trustlink/RelNotesNewFeature.png
[relnotes-documentation-logo]: https://marketplace.trustlinkhosting.com/images/Trustlink/RelNotesDocs.png


<!-- API Links -->
[chips-money-ssi-bank-payments-fees]: ../../reference/sandbox-chips-money-ssi/swagger.json/paths/~1bank~1payments~1fees/get
[chips-money-ssi-bank-payments]: ../../reference/sandbox-chips-money-ssi/swagger.json/paths/~1bank~1payments~1/post
[chips-money-ssi-banks]: ../../reference/sandbox-chips-money-ssi/swagger.json/paths/~1banks/get
[chips-money-payments-purchases-multi-payments]: ../../reference/sandbox-chips-money/swagger.json/paths/~1payments~1purchases~1multi-payments/post









