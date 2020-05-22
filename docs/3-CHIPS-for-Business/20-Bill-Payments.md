# CHIPS&reg; Bill Payments 


The CHIPS Bill Payments API utilizes the CHIPS&reg; Payment Network that allowing for bill payments via different channels like EFT, Zapper, SnapScan, Masterpass and CHIPS&reg;.

Test

# Overview

## Bill Payment Token

Bill payment can be initiated based on a CHIPS&reg; token.

![Bill Payment Token](https://marketplace.trustlinkhosting.com/images/Providers/CHIPS/BillPaymentToken-SequenceDiagram.png)
1. Exchanges between the App and the 3rd party backend server is done to get the correct billing details, account number and amount ready for the token request.
2. Once all the details have been finalize the App initiats the token request to the 3rd party backend. 
3. The 3rd party integrator calls the [*POST /chips/bills/payments/tokens*][post-chips-bills-payments-tokens] on the Trustlink API Marketplace.
4. The bill payment request is registered with the bill payments provider.
5. A payment token in registered with Masterpass
6. The token and fees per payment method is returned to the 3rd party backend.
7. The backend returns the token as the response to the request in step 2. The app should now prompt the user for the method of payment and confirm the fees that are to be paid.

## Credit card payment

The app can allow the user to pay with their credit card in several ways.
* The token can be entered into a Masterpass enables applications like CHIPS Money Manager [[Android]](https://play.google.com/store/apps/details?id=com.chips.ewallet&gl=ZA) [[iOS]](https://apps.apple.com/us/app/chips-ewallet/id1402727891?ls=1), Masterpass banking apps, Zapper or SnapScan.
* The application can embed the Masterpass SDK.

![Bill Payment Card](https://marketplace.trustlinkhosting.com/images/Providers/CHIPS/BillPaymentCardPayment-SequenceDiagram.png)

1. The Masterpass enabled app or Masterpass SDK will send the token directly to Masterpass for payment.
2. Masterpass will notify the Trustlink API Gateway of the transaction result on a webhook.
3. The Trustlink API Gateway will forward the notification to the webhook as provided in step 3 on the token process.
4. The Masterpass app or SDK will be notified of the transaction result. 

> **Note**
>
> No API calls to the Trustlink API Gateway is required for this payment method.

## EFT payment 

For this payment method, the API Gateway will facilitate the transaction through an EFT payment provider.

![Bill Payment EFT](https://marketplace.trustlinkhosting.com/images/Providers/CHIPS/BillPaymentEFTPayment-SequenceDiagram.png)

1. The app will send the [*GET /chips/bills/payments/eft/{token}*][post-chips-bills-payments-eft] to the Trustlink API Gateway.
2. The payment request is registered with the EFT provider, which results in a URL being return. 
3. The API Gateway responds to step 1 with a 307 redirect.
4. The application is redirected to a web frame hosted on the EFT provider system.
5. The payment web frame is returned.
6. The user interacts with the webframe to complete the EFT.
7. The EFT Provider will notify the Trustlink API Gateway of the transaction result on a webhook.
8. The Trustlink API Gateway will forward the notification to the webhook as provided in step 3 on the token process.
9. The app is also notified of the transaction status


