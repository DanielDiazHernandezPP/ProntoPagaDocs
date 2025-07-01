---
title: Devolución de un pago
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: refunds
deprecated: false
hidden: false
metadata:
  title: ''
  description: Endpoint to refund payments with ProntoPaga.
  keywords:
    - refund
    - ' refund a payment'
    - ' refund payments'
    - ' prontopaga'
    - ' api'
    - ' endpoint'
    - ' request'
    - ' body params'
    - ' response'
    - ' examples'
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