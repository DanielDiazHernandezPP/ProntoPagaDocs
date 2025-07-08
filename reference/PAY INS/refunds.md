---
title: Devolución de un pago
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: refunds
deprecated: false
hidden: false
metadata:
  title: 'Refund a payment '
  description: Endpoint to refund payments with ProntoPaga.
  image: >-
    https://files.readme.io/8ad86258e65f9cb3b9ff72521a49dab4c1babd0254a641d9151edfe49108e884-Prontopaga_logotipo.png
  keywords:
    - refund a payment prontopaga
    - refund payments endpoint
    - prontopaga api
    - request
    - body params Prontopaga
    - devolver un pago prontopaga
  robots: index
next:
  description: ''
---
> 🚧 Importante
>
> Solo los pagos con estado exitoso pueden ser rembolsados.

Endpoint para realizar la devolución de un pago. Actualmente, este servicio está operativo solamente para los siguientes métodos de pago:

* Tarjeta Perú
* QR 
* Botón Yape
* Servicios de Yape On File (One Click Payment y Recurrencia)

> ❗️ Número de documento
>
> Para que la devolución sea exitosa, en el campo `clientDocument` debe enviarse el mismo número de documento que el cliente utilizó para realizar la afiliación.