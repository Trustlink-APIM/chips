---
tags: [Security]
---

# OTPs for the CHIPS Authentication

In the CHIPS ecosystem OTPs serves 

- to validate the mobile number or email address for a CHIPS account holder during onboarding.
- enable PIN resets, if forgotten or on initial account creation.

# Notes on integration

## Testing on Sandbox

The OTP sent to mobile numbers does incur costs. For testing to the sandbox, the number of calls to the endpoint is rate limited. 

## Mobile Number Mocked Responses

You can test with mobileNumbers starting with '+2785' to trigger a mockup success response. You will find examples of this in the CHIPS Onboarding and Authentication APIs. 

## Valid Test OTPs

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

