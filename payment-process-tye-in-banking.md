⭐ **How UOB Cards Work on a Merchant Website (Online Payment Flow)**

When you pay on an e-commerce site with a UOB Visa/Mastercard, multiple systems work together:

1.	You enter card details on the merchant’s checkout page.  
2.	The merchant’s payment gateway encrypts the card data.  
3.	The gateway sends the data to the card network (Visa/Mastercard).  
4.	The card network routes it to UOB (issuer bank) for authorization.  
5.	UOB checks: card validity **|** available credit/balance **|** fraud risk **|** 3-D Secure (e.g., UOB Mighty Secure) authentication.  
6.	UOB sends approve/decline back through the network.  
7.	Merchant receives confirmation and completes the order.  
8.	The financial settlement happens later (batch clearing).  

Sample: :: UOB Card Payment Flow on Merchant Website ::

<img width="276" height="801" alt="image" src="https://github.com/user-attachments/assets/087a7267-5be3-46d7-bada-b68156d665c7" />

🔍 **Detailed Step-by-Step Breakdown**  
1. Customer enters card details

✔ Card number

✔ Expiry date

✔ CVV

✔ Name on card

The merchant shouldn’t store raw card details due to PCI compliance rules.

2. Payment gateway encrypts the card information

Examples: Stripe, Adyen, PayPal, WorldPay.

They:

✔ tokenize the card

✔ send it securely to the network

3. Visa/Mastercard routes the authorization

The card scheme checks:

✔ card format

✔ fraud signals

✔ routing to UOB

4. UOB authorizes the transaction

UOB checks:

✔ card is active

✔ sufficient credit/balance

✔ no fraud alerts

✔ correct 3-D Secure authentication (OTP / UOB Mighty Secure)

Result: Approved or Declined.

5. Merchant receives response

If approved:

✔ Merchant accepts the order

✔ Order is confirmed

If declined:

✔ Merchant displays “card declined”

6. Clearing & Settlement (T+1 or T+2 days)

✔ Funds move from UOB → Visa/Mastercard → Merchant’s bank → Merchant.

⭐ **What Is 3-D Secure?**
3-D Secure (3DS) adds an additional identity verification step during online card payments.  
It involves 3 “domains” (hence “3-D”):  
  1.	Merchant / Acquirer Domain (seller + payment gateway)
  2.	Issuer Domain (UOB)
  3.	Interoperability Domain (Visa/Mastercard Directory Server)

📊 Detailed 3-D Secure 2.0 Flow (UOB Card)

_Below is the modern 3DS 2.0 sequence with risk scoring, frictionless flow, and challenge flow._

📦 **Summary: Authentication vs. Authorization**

_3-D Secure = proving identity_  
_Authorization = checking funds + approving the payment_  

📊 **3-D Secure 2.0 Detailed Architecture Diagram**
>
                    ┌────────────────────────────────┐
                    │ 1. Customer                    │
                    │ Enters UOB Card on Checkout    │
                    └──────────────┬─────────────────┘
                                   │
                                   ▼
                    ┌────────────────────────────────┐
                    │ 2. Merchant Website            │
                    │  (Payment Gateway)             │
                    └──────────────┬─────────────────┘
                                   │ 3DS Auth Request
                                   ▼
                    ┌────────────────────────────────┐
                    │ 3. Card Network Directory      │
                    │    Server (Visa/Mastercard)    │
                    └──────────────┬─────────────────┘
                                   │ Routes to Issuer ACS
                                   ▼
                    ┌─────────────────────────────────┐
                    │ 4. UOB Access Control Server    │
                    │    (ACS – Authentication)       │
                    └──────────────┬──────────────────┘
                                   │
                    Risk Assessment│
                                   │
                 ┌─────────────────┴─────────────────┐
                 ▼                                   ▼
     ┌─────────────────────────┐        ┌──────────────────────────┐
     │ 5A. Frictionless Flow   │        │ 5B. Challenge Flow       | 
     │ No OTP Needed           │        │ OTP / App Approval Shown │
     └───────────┬─────────────┘        └──────────┬───────────────┘
                 │                                 │
                 ▼                                 ▼
     ┌─────────────────────────┐        ┌──────────────────────────┐
     │ 6A. Auth Result         │        │ 7B. Customer Completes   │
     │ Returned to Network     │        │ Challenge                │
     └───────────┬─────────────┘        └──────────┬───────────────┘
                 │                                 │
                 ▼                                 ▼
             ┌──────────────────────────────────────────┐
             │ 7. Directory Server Sends Auth Result    │
             │    Back to Merchant                      │
             └─────────────────┬────────────────────────┘
                               │
                               ▼
             ┌──────────────────────────────────────────┐
             │ 8. Merchant Performs Authorization       │
             │    (Normal Payment Flow)                 │
             └─────────────────┬────────────────────────┘
                               │
                               ▼
             ┌──────────────────────────────────────────┐
             │ 9. UOB (Issuer)                          │
             │ Approves / Declines Transaction          │
             └──────────────────────────────────────────┘


sdfsdfsdf
