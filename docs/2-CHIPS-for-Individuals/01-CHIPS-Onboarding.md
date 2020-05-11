---
tags: [Onboarding]
---

# CHIPS® Onboarding of Individuals

![CHIPS Onboarding Sequence Diagram](https://marketplace.trustlinkhosting.com/images/Providers/CHIPS/Onboarding-SequenceDiagram.png)

Onboarding of individuals into CHIPS&reg; follows the sequence diagram as above. 

# Requirements 
In order to integrate securely to the CHIPS&reg; Payment Platform via the [Trustlink API Marketplace] there should be a backend system that issues the APIs through to the API Gateway in the Marketplace.

You can start to test with the Storefront APIs below (See [How it works](../06-how-it-works.md)). Before [signing up](https://marketplace.trustlinkhosting.com/component/apiportal/registration) for Sandbox access on the [Trustlink API Markteplace].

# Flow
## User sign up
[*/chips/register/status/get*](../../reference/sandbox-chips-register/swagger.json/paths/~1status/get)

Once the user indicates that they want to sign up for a CHIPS&reg; profile and account, a check is done to see if the mobile number has been registered before or not.

<!--
type: tab
title: Mobile number not registered
-->

```json http
{
  "method": "get",
  "url": "https://apim.trustlinkhosting.com:8065/sandbox/chips/register/status",
  "query": {
    "mobileNumber": "+27852223333",
    "version": "1.0"
  },
  "headers": {
    "marketplaceKeyId": "cc8d4f9b-bda5-4025-9b95-a0896242edb1"
  }
}
```

<!--
type: tab
title: Mobile number already registered 
-->

Testing with a mobile number that is register to George MacDonald.

```json http
{
  "method": "get",
  "url": "https://apim.trustlinkhosting.com:8065/sandbox/chips/register/status",
  "query": {
    "mobileNumber": "+27853453456",
    "version": "1.0"
  },
  "headers": {
    "marketplaceKeyId": "cc8d4f9b-bda5-4025-9b95-a0896242edb1"
  }
}
```

<!-- type: tab-end -->


## Confirm the user's mobile number with OTP

### Request an OTP for the mobile number
[*POST /chips/register/mobile/otp*](../../reference/sandbox-chips-register/swagger.json/paths/~1mobile~1otp/get)

```json http
{
  "method": "get",
  "url": "https://apim.trustlinkhosting.com:8065/sandbox/chips/register/mobile/otp",
  "query": {
    "mobileNumber": "+27852223334",
    "version": "1.0"
  },
  "headers": {
    "marketplaceKeyId": "cc8d4f9b-bda5-4025-9b95-a0896242edb1"
  }
}
```

### Verify the OTP 
[*POST /chips/register/mobile/otp*](../../reference/sandbox-chips-register/swagger.json/paths/~1mobile~1otp/post)

<!--
type: tab
title: Successful OTP verification
-->
```json http
{
  "method": "post",
  "url": "https://apim.trustlinkhosting.com:8065/sandbox/chips/register/mobile/otp",
  "query": {
    "version": "1.0"
  },
  "headers": {
    "marketplaceKeyId": "cc8d4f9b-bda5-4025-9b95-a0896242edb1",
    "Content-Type": "application/json"
  },
  "body": {
    "mobileNumber": "+27852223334",
    "otp": "45361"
  }
}
```
<!--
type: tab
title: Failed OTP verification
-->
```json http
{
  "method": "post",
  "url": "https://apim.trustlinkhosting.com:8065/sandbox/chips/register/mobile/otp",
  "query": {
    "version": "1.0"
  },
  "headers": {
    "marketplaceKeyId": "cc8d4f9b-bda5-4025-9b95-a0896242edb1",
    "Content-Type": "application/json"
  },
  "body": {
    "mobileNumber": "+27852223334",
    "otp": "45678"
  }
}
```
<!-- type: tab-end -->




[Trustlink API Marketplace]: https://marketplace.trustlinkhosting.com