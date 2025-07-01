---
title: Métodos de pago por moneda
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: payment-methods-per-currency
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    Endpoint to know the payment methods per currency associated with your
    company in ProntoPaga.
  keywords:
    - payment methods
    - ' currency'
    - ' payment methods per currency'
    - ' prontopaga'
    - ' api'
    - ' endpoint'
    - ' body params'
    - ' request'
  robots: index
next:
  description: ''
---
Muestra todos los métodos asignados al comercio según la moneda enviada. 

## Monedas

Se debe enviar en la URL el código ISO 4217 de la moneda.

| País    | Código    |
| :------ | :-------- |
| Brasil  | BRL / USD |
| Chile   | CLP / USD |
| Ecuador | USD       |
| Perú    | PEN / USD |