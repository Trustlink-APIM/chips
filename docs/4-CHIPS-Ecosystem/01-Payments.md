# CHIPS Payments 

Let us look under the hood of a CHIPS Payment. There are several methods to facilitate payments in the CHIPS ecosystem.


# Payment Methods
## Pay a CHIPS merchant
Facilitated by a standard wallet to wallet transfer, you can make a person/merchant to merchant payment using the 'payerAccountUuid' of the digital cash user and the 'payeeAccountUuid' of the merchant.

# Payment Fields
There are many fields in a payment request that have inherent features relating to their usage. For the most part, the payment fields documentation in the API request details the 'there and then' function of the field. Here we highlight some of the elements regarding the business level usage of these fields.

## payeeRefInfo
The 'payeeRefInfo' field carries the same meaning as an Internet Banking beneficiary reference. It will indicate to the payee what the payment is for and will typically be something like an order or invoice number. For merchants using the Trustlink miBusiness Portal, their Transaction History will display the 'payeeRefInfo' as the Reference column.