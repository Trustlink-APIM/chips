# Basic Secured System Interface (BSSI) Authentication

BSSI uses Basic HTTP Authentication using the SSI UUID as username and SSI APIKey as password.  The Basic HTTP authentication should use ```BSSI``` instead of ```Basic```. As per Basic HTTP authenication the username + ':' + password should be base64 encoded.

For example

* SSI UUID: d6ff131d-2e64-4e3a-a36c-30c3fe0fde8d
* SSI API Key: 0d627bf1-1c4b-4da1-bfac-f394411512f3 

The resulting header to be send will be
```
Authorization: BSSI ZDZmZjEzMWQtMmU2NC00ZTNhLWEzNmMtMzBjM2ZlMGZkZThkOjBkNjI3YmYxLTFjNGItNGRhMS1iZmFjLWYzOTQ0MTE1MTJmMw==
```


