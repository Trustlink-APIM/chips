---
tags: [CHIPS Money]
---

# CHIPS&reg; Money Cash Sends ATM API

![CHIPS&reg; Cashsends Flow](https://marketplace.trustlinkhosting.com/images/Providers/CHIPS/Cash_send_atm_voucher.png)

This API allows a CHIPS® user to send money for withdrawal at a supported ATM.

This document will show API calls relevant to the interactions between the 3rd Party system and the [Trustlink API Marketplace](https://marketplace.trustlinkhosting.com)

For full details on the complete business flow can be found [here.](https://marketplace.trustlinkhosting.com/api-documentation/api-publishers/chips-open-banking-platform/chips-money-basic)

## Flow

### Get the fees for sending the ATM voucher

Fees depend on the amount that will be sent in the ATM voucher.

```json http
{
  "method": "get",
  "url": "https://apim.trustlinkhosting.com:8065/sandbox/chips/money/cashsends/atm/fees",
  "query": {
    "amount": "300"
  },
  "headers": {
    "Authorization": "DEMO MjE3MDJhZWYtYTkwMi00YmU0LTgxNTUtNjk3OTljNWY0MjczOmIyNzAyNmZhLTlkYWUtNDcwOS05MzQxLTFiYWFjOGJlMzc3NA==",
    "marketplaceKeyId": "cc8d4f9b-bda5-4025-9b95-a0896242edb1"
  }
}
```
> **Note on Fees**
>
> The 'totalAmount' returned by GET /cashsends/atm/fees will be deducted from the CHIPS&reg; account in addition to the ammount specified for the withdrawal



