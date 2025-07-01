---
title: Crear un nuevo pago - Chile Webpay Mall
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: create-payment-chile-webpay-mall
deprecated: false
hidden: false
metadata:
  title: ''
  description: Endpoint to create a new card payment with ProntoPaga in Chile (Webpay).
  keywords:
    - create a payment in chile
    - ' create a webpay payment'
    - ' webpay payment'
    - ' card payment'
    - ' prontopaga'
    - ' endpoint'
    - ' api'
    - ' request'
    - ' body params'
    - ' examples'
    - ' response'
  robots: index
next:
  description: ''
---
> 📘 Datos del cliente
>
> Como recomendación, la información que se envía en los parámetros del body debería proceder del perfil del cliente.

La respuesta de ProntoPaga a la solicitud de pago es el UID de la transacción y la URL a la que debe redirigir al usuario.

> ❗️ Transacción cancelada
>
> Si el código de comercio no esta registrado en el comercio, o no existe, esto va a cancelar la transacción.

## Logos de los métodos de pago

Antes de finalizar tu integración, recuerda agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu front-end. Puedes [descargarlos aquí.](https://drive.google.com/uc?export=download\&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr)