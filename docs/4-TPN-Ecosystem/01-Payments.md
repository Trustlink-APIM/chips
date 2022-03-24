# CHIPS Payments 

Let us look under the hood of a CHIPS Payment. There are several methods to facilitate payments in the CHIPS ecosystem.

# Payment Methods
## Pay a CHIPS merchant
Facilitated by a standard wallet to wallet transfer, you can make a person/merchant to merchant payment using the 'payerAccountUuid' of the digital cash user and the 'payeeAccountUuid' of the merchant.

# Payment Fields
There are many fields in a payment request that have inherent features relating to their usage. For the most part, the payment fields documentation in the API request details the 'there and then' function of the field. Here we highlight some of the elements regarding the business level usage of these fields.

## payeeAccountUuid and payerAccountUuid
Any person or merchant in the CHIPS Payment Network has a 'memberUuid' to identify them in the system. Associated with each person and merchant is a primary account. The primary account has the same UUID as the entity in the payment network. Thus your 'memberUuid' is in most case the same as your 'accountUuid'. 

These fields are searchable on the /transactions API end-point as 'memberUuid', 'contraMemberUuid', 'accountUuid' or 'contraAccountUuid'.

## payeeRefInfo
The 'payeeRefInfo' field carries the same meaning as an Internet Banking beneficiary reference. It will indicate to the payee what the payment is for and will typically be something like an order or invoice number. The 'payeeRefInfo' can be payee provided, but can also be generated in the application to reflect an order or invoice number.

For merchants using the Trustlink miBusiness Portal, their Transaction History will display the 'payeeRefInfo' as the Reference column. 

The field is searchable on the /transactions API end-point as 'txRefInfo'. The query parameter, in this case, is called 'txRefInfo', because it also filters the 'payerRefInfo' data. 
