---
title: Detalles de un pago (UID)
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: payment-details-uid
deprecated: false
hidden: false
metadata:
  title: Payment details (UID)
  description: >-
    Endpoint to obtain the details of a payment. The uid identifier must be sent
    in the path.
  image: >-
    https://files.readme.io/6cf08e0959db2c2fc76a52d9b5c5fff075a8319c00aa367b6c6928ba2c230892-Prontopaga_logotipo.png
  keywords:
    - payment details Prontopaga
    - details of a payment
    - endpoint Prontopaga
    - api
    - path
    - body params
    - request
    - detalles de pago Prontopaga
  robots: index
next:
  description: ''
---
Prueba este endpoint directamente en Postman haciendo clic en el siguiente botón:

<HTMLBlock>{`
<!DOCTYPE html>
<html>
<body>

<p><a href="https://www.postman.com/prontopaga-api/workspace/prontopaga-docs/request/34607190-0b5d0624-2cad-4cee-9d41-2fe259b81d6e?action=share&source=copy-link&creator=45976681" target="_blank">
  <img src="https://run.pstmn.io/button.svg" alt="Run in Postman" style="width: 160px;">
</a></p>

</body>
</html>
`}</HTMLBlock>

***

Endpoint para buscar y obtener los detalles de un pago por medio del identificador único del pago (UID). Se debe enviar el valor `uid` en la ruta.