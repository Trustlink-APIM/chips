---
tags: [Account]
---

# CHIPS&reg; Account Details

| | |
|:---:|---|
|![Account Details Icon](https://marketplace.trustlinkhosting.com/images/Providers/CHIPS/AccountDetails.png)  | CHIPS&reg; APIs that allows for checking account balances, limits and transactions history.  |

# Get Account Details

*Full Documentation:* [*GET /chips/money/account/{uuid}*](../../reference/sandbox-chips-money/swagger.json/paths/~1accounts~1%7Buuid%7D/get)

This API is called to retrieve the current account balance as well as details of any limits applicable. 

```json http
{
  "method": "get",
  "url": "https://apim.trustlinkhosting.com:8165/sandbox/chips/money/accounts/fbb9f3a7-402f-432d-8293-d3c0f63d3c4d",
  "query": {
    "version": "1.0"
  },

  "headers": {
    "marketplaceKeyId": "dddb67f4-22d0-4ee8-a441-91966950bd9f"
  }
}
```

[api-get-chips-money-account-uuid]: ../../reference/sandbox-chips-money/swagger.json/paths/~1accounts~1%7Buuid%7D/get
