---
title: Crear un nuevo retiro - Brasil PIX
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: payout-brazil-pix
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
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