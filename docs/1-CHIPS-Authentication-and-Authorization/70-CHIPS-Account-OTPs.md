---
tags: [Security]
---

# OTPs for the CHIPS Authentication

In the CHIPS ecosystem OTPs serves 

- to validate the mobile number or email address for a CHIPS account holder.
- enable PIN resets, if forgotten or on initial account creation.

# Notes on integration

## Testing on Sandbox

The OTP sent to mobile numbers does incur costs. For testing to the sandbox, the number of calls to the endpoint is rate limited. 

## Mobile Number Mocked Responses

You can test with mobileNumbers starting with '+2785' to trigger a mockup success response. Note that there is no OTP associated with the mocked response.

### Examples

<!--
type: tab
title: Mobile Verification during Onboarding 
-->

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

<!--
type: tab
title: Mobile OTP for PIN reset 
-->

Coming soon!

<!-- type: tab-end -->

### Valid Test OTPs

In order to test OTP functionality the in sandbox environment, you have the following options:

- Use a mobileNumber which you have access to.
- Use a '+999' number which will always have 11111 as OTP
- Use an email address which you have access to.

<!--
theme: info
-->

> _Note_
>
> In all 3 cases the mobileNumber or email address must be associated with the CHIPS account.

#### Examples

Coming soon !
