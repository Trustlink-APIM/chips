---
tags: [Reference, Errors]
---

# CHIPS Error Codes

| Code | Key | Description | Resolution |
|--- |--- |--- | --- |
|91001| rc.91001.apim.missing.refuuid.or.bssiauth | Register person requires merchant UUID as referrer UUID or BSSI Authentication with SSI UUID as username | If you are integrating as a Subscribed Service Intermediary, please use [Basic Subscribed Service Intermediary (BSSI)][chips-auth-bssi] when calling the [POST /chips/register/person][chips-api-post-register-person] endpoint. If integrating as a Merchant Referrer, please specify your [Merchant UUID][chips-mib-merchantuuid] in the *referrerUuid* field in the payload to [POST /chips/register/person][chips-api-post-register-person]. |
| 91002 | rc.91002.apim.missing.identity |Register person requires identity node | Add identity node to [POST /chips/register/person][chips-api-post-register-person] |
| 91003 | rc.91003.apim.selfie.id.photo.equal | $.photo must be a selfie and $.identity.photo must be a photo of your id book / id card. | The two photos sent in the [POST /chips/register/person][chips-api-post-register-person] call should be a selfie and a photo of the id card/book. This is in order to do validations against Home Affairs and face matches between the user and the id card/book) |
| 91004 | rc.91004.apim.duplicate.person | Person with same ID Number or Mobile Number has already been registered | |
| 91005 | rc.91005.apim.missing.mobilenumber.or.emailaddress | Requires mobileNumber or emailAddress | Add mobileNumber or emailAddress to the payload for [POST /chips/auth/pin/otp][chips-api-post-auth-pin-otp] |
| 91006 | rc.91006.apim.missing.pin.or.otp | Requires PIN and OTP | Add pin and otp to the payload for [POST /chips/auth/pin][chips-api-post-auth-pin]. The otp is obtained with [POST /chips/auth/pin/otp][chips-api-post-auth-pin] |
| 91900 | rc.91900.apim.bad.mobilenumber.and.amount | Requires mobileNumber and amount. Amount must be a number. | |


[chips-auth-bssi]: ../1-CHIPS-Authorization/20-CHIPS-Basic-Subscribed-Service-Intermediary-Authentication.md
[chips-api-post-register-person]: ../../reference/sandbox-chips-register/swagger.json/paths/~1person/post
[chips-mib-merchantuuid]: ./
[chips-api-post-register-person]: ./
[chips-api-post-auth-pin-otp]: ./
[chips-api-post-auth-pin]: ./