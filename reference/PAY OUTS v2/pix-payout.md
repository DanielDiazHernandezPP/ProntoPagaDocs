---
title: Crear un nuevo retiro por PIX - Brasil
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: pix-payout
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    Endpoint to create a new payout request with PIX. To create a payout, the
    request must be constructed with the following parameters.
  keywords:
    - pix payout
    - ' how to make a pix payout'
    - ' endpoint'
    - ' api'
    - ' request'
    - ' brazil payout'
    - ' brazil pix payout'
    - ' examples'
    - ' prontopaga'
  robots: index
next:
  description: ''
---
Endpoint para crear una nueva solicitud de retiro con PIX. 

> 📘 Webhook
>
> Una vez que el usuario haya completado el proceso de retiro, ProntoPaga devolverá los datos a la URL que hayas especificado en la `confirmationURL`.

## Tipos de cuentas

Estos son los posibles tipos de cuentas que se pueden enviar en el campo `accountType`.

| Tipo de cuenta | Descripción  |
| :------------- | :----------- |
| 1              | Corrente     |
| 2              | Salario      |
| 3              | Poupança     |
| 4              | Transacional |