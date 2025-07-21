---
title: Crear un nuevo pago - Chile Webpay Mall
api:
  file: prontopaga-api.json
  operationId: create-payment-chile-webpay-mall
deprecated: false
hidden: true
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
<HTMLBlock>{`
<!DOCTYPE html>
<html>
<body>

<p><a href="https://www.postman.com/prontopaga-api/workspace/prontopaga-docs/request/34607190-f4af4947-106e-4346-916a-e54c2d266f7a?action=share&creator=45976681&ctx=documentation" target="_blank">
  <img src="https://run.pstmn.io/button.svg" alt="Run in Postman" style="width: 160px;">
</a></p>

</body>
</html>
`}</HTMLBlock>

> 📘 Datos del cliente
>
> Como recomendación, la información que se envía en los parámetros del body debería proceder del perfil del cliente

La respuesta de ProntoPaga a la solicitud de pago es el UID de la transacción y la URL a la que debe redirigir al usuario.

> ❗️ Transacción cancelada
>
> Si el código de comercio no esta registrado en el comercio, o no existe, esto va a cancelar la transacción.

## Logos de los métodos de pago

Antes de finalizar tu integración, recuerda agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu front-end. Puedes [descargarlos aquí.](https://drive.google.com/uc?export=download\&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr)