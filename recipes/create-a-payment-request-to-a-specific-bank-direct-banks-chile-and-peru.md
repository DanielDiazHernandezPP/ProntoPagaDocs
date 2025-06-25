---
title: Create a payment request to a specific bank (Direct Banks - Chile and Peru)
description: Recipe Description
hidden: false
recipe:
  color: '#018FF4'
  icon: 🦉
---
```json JSON
{
    "currency": "CLP",
    "country": "CL",
    "amount": 1000,
    "clientName": "John Doe",
    "clientEmail": "johndoe@example.com",
    "clientPhone": "999999999",
    "clientDocument": "12345678912",
    "paymentMethod": "PagaConTuBanco",
    "bankCode": "CL_490",
    "urlConfirmation": "Webhook",
    "urlFinal": "example.com/successful",
    "urlreject": "example.com/declined",
    "order": "1234",
    "sing": "Signature of the parameters"
  }
```

```json Response Example
{
    "urlPay"= [string] // Link to process the payment
    "uid"= [string] // Payment identifier in the system
    "reference"= [string] //Reference in our services
}
```

# Send bankCode in the payment request

<!-- json@10 -->

First query the <a href="https://docs.prontopaga.com/reference/bank-codes">Bank Code List</a> endpoint and take the value of the `code` field of the bank of your choice.

Place that code in the `bankCode` field of the <a href="https://docs.prontopaga.com/reference/create-payment">Create a new payment</a> endpoint, as shown in this example.