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


'
                     ┌────────────────────────┐
                     │ 1. You (Cardholder)    │
                     │ Enter UOB Card Details │
                     └───────────┬────────────┘
                                 │
                                 ▼
                     ┌────────────────────────┐
                     │ 2. Merchant Website    │
                     │    (Checkout Page)     │
                     └───────────┬────────────┘
                                 │
                                 ▼
                     ┌────────────────────────┐
                     │ 3. Payment Gateway     │
                     │ (Stripe / Adyen / etc.)│
                     └───────────┬────────────┘
                                 │ Encrypted Payment Data
                                 ▼
                     ┌────────────────────────┐
                     │ 4. Card Network        │
                     │ (Visa / Mastercard)    │
                     └───────────┬────────────┘
                                 │ Authorization Request
                                 ▼
                     ┌────────────────────────┐
                     │ 5. UOB (Issuer Bank)   │
                     │ - Check funds          │
                     │ - Fraud check          │
                     │ - 3DS verification     │
                     └───────────┬────────────┘
                                 │ Authorization Result
                                 ▼
                     ┌────────────────────────┐
                     │ 6. Card Network        │
                     └───────────┬────────────┘
                                 │
                                 ▼
                     ┌────────────────────────┐
                     │ 7. Payment Gateway     │
                     └───────────┬────────────┘
                                 │
                                 ▼
                     ┌────────────────────────┐
                     │ 8. Merchant Website    │
                     │ Shows “Payment Success”│
                     └───────────┬────────────┘
                                 │
                                 ▼
                     ┌────────────────────────┐
                     │ 9. Settlement Later    │
                     │ (Clearing & Funding)   │
                     └────────────────────────┘
'
