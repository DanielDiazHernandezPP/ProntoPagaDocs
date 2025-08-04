---
title: Cancelar un pago con QR - Perú
api:
  file: prontopaga-api.json
  operationId: post_peqrcancel{uid}
deprecated: false
hidden: false
metadata:
  title: Cancel a QR code payment - Peru
  description: >-
    This page describes an endpoint that allows to cancel a QR payment in Peru
    if it was not made immediately, preventing a customer from using the QR
    image to try to pay later.
  image: >-
    https://files.readme.io/3caae967b464b2c702e2e6f0298c1dafe6a5ed8ae83762a97ba5c4a156e2e88e-Prontopaga_logotipo.png
  keywords:
    - endpoint Prontopaga
    - cancel a QR
    - cancel a payment
    - qr peru prontopaga
    - api prontopaga
    - cancelar un pago con QR Perú
  robots: index
---
Prueba este endpoint directamente en Postman haciendo clic en el siguiente botón:

<HTMLBlock>{`
<!DOCTYPE html>
<html>
<body>

<p><a href="https://www.postman.com/prontopaga-api/workspace/prontopaga-docs/request/34607190-d2d5b910-f670-4750-9292-4bbad03fc7b4?action=share&source=copy-link&creator=45976681" target="_blank">
  <img src="https://run.pstmn.io/button.svg" alt="Run in Postman" style="width: 160px;">
</a></p>

</body>
</html>
`}</HTMLBlock>

***

Con este endpoint podrás cancelar un pago con QR en Perú (cuando no se realizó al momento). De este modo, se evitará que un cliente guarde la imagen del QR e intente pagar tiempo después.

***