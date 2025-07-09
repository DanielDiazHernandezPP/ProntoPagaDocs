---
title: Crear un nuevo retiro - Brasil PIX
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: payout-brazil-pix
deprecated: false
hidden: false
metadata:
  title: Create a new payout in Brasil with Pix
  description: >-
    This endpoint is used to create a new payout using the ProntoPaga API. This
    guide covers required parameters, the use of bank code, and webhook
    confirmation.
  image: >-
    https://files.readme.io/f51cda7b4cef2b27a541983c989c232b6ac1f6c9a55a3e1c726dc0a04428d481-Prontopaga_logotipo.png
  keywords:
    - create payout API Brazil
    - ProntoPaga payout Brazil
    - ProntoPaga Brazil withdrawal
    - bank transfer Brazil
    - crear retiro ProntoPaga
    - endpoint retiro Brasil Pix
    - Pix Brasil
  robots: index
next:
  description: ''
---
Endpoint para crear una nuevo retiro. Para crear una nueva solicitud de retiro, la solicitud debe construirse con los siguientes parámetros.

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