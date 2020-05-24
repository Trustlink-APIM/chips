---
tags: [Authorization]
---

# Demo Authentication on the Storefront

The Trustlink API Marketplace allows mocked up demo calls to APIs available on the [Storefront](06-how-it-works.md). These demo APIs allows you to get familiar with the basic flows of the API without signing up for a Trustlink API Marketplace account.

To access the demo APIs you will be using the demo marketplace API key and [basic HTTP authentication](https://en.wikipedia.org/wiki/Basic_access_authentication). For the basic auth just use ```DEMO``` instead of ```Basic```

The basic authentication details are as follows.

<!-- title: HTTP Basic Authentication Details -->
| Username | Password |
|---|---|
|21702aef-a902-4be4-8155-69799c5f4273 | b27026fa-9dae-4709-9341-1baac8be3774 |

The resulting base64(username:password) is ```MjE3MDJhZWYtYTkwMi00YmU0LTgxNTUtNjk3OTljNWY0MjczOmIyNzAyNmZhLTlkYWUtNDcwOS05MzQxLTFiYWFjOGJlMzc3NA==```

Thus to successful call a Storefront API you need the following headers.

<!-- title: Storefront Headers -->

| Header           | Value                                                                                                     |
| ---------------- | --------------------------------------------------------------------------------------------------------- |
| markteplaceKeyId | cc8d4f9b-bda5-4025-9b95-a0896242edb1                                                                      |
| Authorization    | DEMO MjE3MDJhZWYtYTkwMi00YmU0LTgxNTUtNjk3OTljNWY0MjczOmIyNzAyNmZhLTlkYWUtNDcwOS05MzQxLTFiYWFjOGJlMzc3NA== |




