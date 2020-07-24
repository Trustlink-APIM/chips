---
tags: [Reference, Errors]
---

# CHIPS Error Codes

| Code | Key | Description | Resolution |
|--- |--- |--- | --- |
|91001| rc.91001.apim.missing.refuuid.or.bssiauth | Register person requires merchant UUID as referrer UUID or BSSI Authentication with SSI UUID as username | If you are integrating as a Subscribed Service Intermediary, please use [Basic Subscribed Service Intermediary (BSSI)][chips-auth-bssi] when calling the [POST /chips/register/person][chips-api-post-register-person] endpoint. If integrating as a Merchant Referrer, please specify your [Merchant UUID][chips-mib-merchantuuid] in the *referrerUuid* field in the payload to [POST /chips/register/person][chips-api-post-register-person]. |




[chips-auth-bssi]: ../1-CHIPS-Authorization/20-CHIPS-Basic-Subscribed-Service-Intermediary-Authentication.md
[chips-api-post-register-person]: ../../reference/sandbox-chips-register/swagger.json/paths/~1person/post
[chips-mib-merchantuuid]: ./