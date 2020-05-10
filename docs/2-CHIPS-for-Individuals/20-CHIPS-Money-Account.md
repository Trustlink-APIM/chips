---
tags: [Account]
---

# CHIPS&reg; Account Details

| | |
|:---:|---|
|![Account Details Icon](https://marketplace.trustlinkhosting.com/images/Providers/CHIPS/AccountDetails.png)  | CHIPS&reg; APIs that allows for checking account balances, limits and transactions history.  |

# Get Account Details
[*GET /chips/money/account/{uuid}*][api-get-chips-money-account-uuid]

This API is normally called to retrieve the current account balance. 

```json http
{
  "method": "get",
  "url": "https://apim.trustlinkhosting.com:8065/sandbox/chips/money/accounts/fbb9f3a7-402f-432d-8293-d3c0f63d3c4d",
  "query": {
    "version": "1.0"
  },
  "headers": {
    "Authorization": "DEMO MjE3MDJhZWYtYTkwMi00YmU0LTgxNTUtNjk3OTljNWY0MjczOmIyNzAyNmZhLTlkYWUtNDcwOS05MzQxLTFiYWFjOGJlMzc3NA==",
    "marketplaceKeyId": "cc8d4f9b-bda5-4025-9b95-a0896242edb1"
  }
}
```

[api-get-chips-money-account-uuid]: https://marketplace.trustlinkhosting.com/api-chips-money-accounts-uuid-get
