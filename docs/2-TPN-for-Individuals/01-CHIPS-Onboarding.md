---
tags: [Onboarding]
---

# Trustlink Payment Network Onboarding of Individuals

![Onboarding Sequence Diagram](https://marketplace.trustlinkhosting.com/images/Providers/CHIPS/OnboardingAPI/Onboarding-SequenceDiagram.png)

Onboarding of individuals into Trustlink Payment Network follows the sequence diagram as above. 

# Requirements 
## Sandbox and Storefront API Calls
You will require
* Trustlink marketplaceKeyId linked to the following API bundles
  * CHIPS Onboarding API
  * CHIPS Authentication API (Optional for some use cases)

As a minimum the CHIPS Money API should the linked to the marketplaceKeyId as well to enable transactions capabilities.

## Production API Calls
* In order to integrate securely to the Trustlink Payment Network there should be a backend system that issues the APIs through to the Trustlink API Gateway.
* The backend should be authenticated with the a production marketplaceKeyId link to the production versions of the CHIPS Onboarding API and if required the CHIPS Authentication API.
* The backend should further be authentication via Static IPs and/or mTLS using a recognized CA.

<!-- theme: info -->
> ### Note
>
> We require either Static IP OR mTLS. Both are preferred, but Static IPs can not always be guaranteed by some cloud based backend systems

# Flow
## User sign up
*Full Documentation:* [*GET /chips/register/status/get*](../../reference/sandbox-chips-register/swagger.json/paths/~1status/get)

Once the user indicates that they want to sign up for a CHIPS&reg; profile and account, a check is done to see if the mobile number has been registered before or not.

<!--
type: tab
title: Mobile number not registered
-->

```json http
{
  "method": "get",
  "url": "https://apim.trustlinkhosting.com:8165/sandbox/chips/register/status",
  "query": {
    "mobileNumber": "+27851112233",
    "version": "1.0"
  },
  "headers": {
    "marketplaceKeyId": "dddb67f4-22d0-4ee8-a441-91966950bd9f",
    "Content-Type": "application/json"
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
  "url": "https://apim.trustlinkhosting.com:8165/sandbox/chips/register/status",
  "query": {
    "mobileNumber": "+27853453456",
    "version": "1.0"
  },
  "headers": {
    "marketplaceKeyId": "dddb67f4-22d0-4ee8-a441-91966950bd9f",
    "Content-Type": "application/json"
  }
}
```

<!-- type: tab-end -->


## Confirm the user's mobile number with OTP

### Request an OTP for the mobile number
*Full Documentation:* [*POST /chips/register/mobile/otp*](../../reference/sandbox-chips-register/swagger.json/paths/~1mobile~1otp/get)

```json http
{
  "method": "get",
  "url": "https://apim.trustlinkhosting.com:8165/sandbox/chips/register/mobile/otp",
  "query": {
    "mobileNumber": "+27852223334",
    "version": "1.0"
  },
  "headers": {
    "marketplaceKeyId": "dddb67f4-22d0-4ee8-a441-91966950bd9f",
    "Content-Type": "application/json"
  }
}
```

### Verify the OTP 
*Full Documentation:* [*POST /chips/register/mobile/otp*](../../reference/sandbox-chips-register/swagger.json/paths/~1mobile~1otp/post)


<!--
type: tab
title: Successful OTP verification
-->
```json http
{
  "method": "post",
  "url": "https://apim.trustlinkhosting.com:8165/sandbox/chips/register/mobile/otp",
  "query": {
    "version": "1.0"
  },
  "headers": {
    "marketplaceKeyId": "dddb67f4-22d0-4ee8-a441-91966950bd9f",
    "Content-Type": "application/json"
  },
  "body": {
    "mobileNumber": "+27852223334",
    "otp": "45678"
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
  "url": "https://apim.trustlinkhosting.com:8165/sandbox/chips/register/mobile/otp",
  "query": {
    "version": "1.0"
  },
  "headers": {
    "marketplaceKeyId": "dddb67f4-22d0-4ee8-a441-91966950bd9f",
    "Content-Type": "application/json"
  },
  "body": {
    "mobileNumber": "+27852223334",
    "otp": "45231"
  }
}
```

<!-- type: tab-end -->

## Register User Profile and Account
[*POST /chips/register/persons*](../../reference/sandbox-chips-register/swagger.json/paths/~1mobile~1otp/post)

Mockup exmaple coming soon.

## Setup Authentication 

### Request PIN set OTP
Note that the OTP that you received as part of the onboarding can still be used here unless it already expired. OTPs are valid for 15 minutes.

[*POST /chips/auth/pin/otp*](https://trustlink.stoplight.io/docs/chips/b3A6NTY2Nzgx-request-pin-reset-otp)

More information regarding OTPs during testing can be found [here](https://trustlink.stoplight.io/docs/chips/ZG9jOjQ3Nzg3NzI2-ot-ps-for-the-authentication)

### Set PIN

[*POST /chips/auth/pin*](https://trustlink.stoplight.io/docs/chips/b3A6NTY2Nzgy-set-chips-account-pin)

### Login

For details on authenticating see 

* [Authenticating User](https://trustlink.stoplight.io/docs/chips/b3A6ODc2MzE2-authenticate-chips-user)



# Also See 
See [How it works] for more details on Storefront and Sandbox testing.

Get the [Storefront marketplaceKeyId] here.

[How it works]: https://trustlink.stoplight.io/docs/chips/ZG9jOjQ3Nzg3NzI4-how-it-works
[Storefront marketplaceKeyId]: https://trustlink.stoplight.io/docs/chips/ZG9jOjQ3Nzg3NzI1-demo-authentication-on-the-storefront
[Trustlink API Marketplace]: https://marketplace.trustlinkhosting.com
