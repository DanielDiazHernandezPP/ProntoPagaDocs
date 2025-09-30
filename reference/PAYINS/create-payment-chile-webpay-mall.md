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
Prueba este endpoint directamente en Postman haciendo clic en el siguiente botón:

<HTMLBlock>{`
<!DOCTYPE html>
<html>
<body>

<p><a href="https://www.postman.com/prontopaga-api/prontopaga-docs/request/ibrclgw/create-a-new-payment-card-webpay?action=share&source=copy-link&creator=45976681" target="_blank">
  <img src="https://run.pstmn.io/button.svg" alt="Run in Postman" style="width: 160px;">
</a></p>

</body>
</html>
`}</HTMLBlock>

***

<br />

> 📘 Datos del cliente
>
> Como recomendación, la información que se envía en los parámetros del body debería proceder del perfil del cliente

La respuesta de ProntoPaga a la solicitud de pago es el UID de la transacción y la URL a la que debe redirigir al usuario.

> ❗️ Transacción cancelada
>
> Si el código de comercio no esta registrado en el comercio, o no existe, esto va a cancelar la transacción.

## Logos de los métodos de pago

Antes de finalizar tu integración, recuerda agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu front-end. Puedes [descargarlos aquí.](https://prontopagalatam-my.sharepoint.com/:u:/g/personal/tahbet_reategui_prontopaga_com/EWC1ijJHq5JKnjpIH9qH0ncB42rHOzcbXWdiOlyQQHciCA?e=3taLCb\&download=1)
