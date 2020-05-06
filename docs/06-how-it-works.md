---
tags: [Info]
---

# How it works

The [Trustlink API Marketplace] exposes APIs in 3 versions.

- Storefront - Mocked up APIs
- Sandbox - Simulated APIs
- Production - The real deal

# Storefront APIs

The storefront APIs are demonstration APIs that return static mocked up responses.
They can be accessed with the following headers

<!-- title: Storefront Headers -->

| Header           | Value                                                                                                     |
| ---------------- | --------------------------------------------------------------------------------------------------------- |
| markteplaceKeyId | cc8d4f9b-bda5-4025-9b95-a0896242edb1                                                                      |
| Authorization    | DEMO MjE3MDJhZWYtYTkwMi00YmU0LTgxNTUtNjk3OTljNWY0MjczOmIyNzAyNmZhLTlkYWUtNDcwOS05MzQxLTFiYWFjOGJlMzc3NA== |

In the Stoplight Docs these values are prepopulated in most of the example flows.

<!-- theme: warning -->

> **Storefront Mocking**
> All results for a Storefront API calls are static non-functional mockups. 

You can identify a mocked up result by looking at the `apimStatus.marketplaceMocked` value returned.

**Example**

    {
      "externalAmount": 8.7,
      "internalAmount": 2.5,
      "totalAmount": 12.88,
      "vatAmount": 1.68,
      "apimStatus": {
        "marketplaceId": "Id-cfbdb25ef35fb9cd72ad0b08",
        "statusCode": 200,
        "marketplaceCode": 200,
        "providerCode": "200",
        "marketplaceMocked": true
      }
    }

# Sandbox APIs

The sandbox APIs test through to sandbox versions of the APIs at the back of the [Trustlink API Marketplace]. These sandbox environments are clones of the production environment with fictious data and attempt to simulate production as close as possible. 

In some example cases static mocked results are used to demonstrate certain use cases. In other cases the mockups are due to cost or security considerations. 

Mocked up results can be identified, as per the Storefront APIs, by the `apimStatus.marketplaceMocked` value.

To gain access to the Sandbox APIs please [register on the API Markteplace](https://marketplace.trustlinkhosting.com/component/apiportal/registration)

Send an email to apisales@trustlink.co.za providing us with 

- Organization name.
- APIs your are interested in.
- Usage purpose of the APIs.
- Some details on your system architecture.

We need the above details to complete the provisioning of you account and to assist in choosing the correct Authenication and Authorization model to operate under. 

You will be then be provisioned and issued a _Organization_ Sandbox API Application in the [Trustlink API Marketplace] Portal, where you can generate marketplace API Keys to access the APIs. 

# Production

Once you have signed up for the Sandbox APIs and successfully integrated them into you development environment, you can apply for access to the official Production APIs. 

You will then be given access to the Production APIs in the Marketplace which you can group and secure under the Applications tab.

[Trustlink API Marketplace]: https://marketplace.trustlinkhosting.com
