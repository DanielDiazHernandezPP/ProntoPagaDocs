---
title: Cancelar un pago con QR - Argentina
api:
  file: prontopaga-api.json
  operationId: get_new-endpoint-1
deprecated: false
hidden: true
metadata:
  title: Cancelar un pago con QR - Argentina | ProntoPaga Docs
  description: >-
    This page describes an endpoint that allows to cancel a QR payment in
    Argentina if it was not made immediately, preventing a customer from using
    the QR image to try to pay later.
  image: >-
    https://files.readme.io/a19c236b1675b7716c6e4b3bd9044497340e00420d7f90cae9fc9665ce4dbb84-Prontopaga_logotipo.png
  keywords:
    - endpoint Prontopaga
    - cancel a QR
    - cancel a payment
    - qr argentina prontopaga
    - api prontopaga
    - cancelar un pago con QR Argentina
  robots: index
---
Prueba este _endpoint_ directamente en Postman haciendo clic en el siguiente botón:

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

Con este _endpoint_ podrás cancelar un pago con QR en Argentina, cuando tiene el estado **pendiente**. De este modo, se evitará que un cliente intente pagar tiempo después.
