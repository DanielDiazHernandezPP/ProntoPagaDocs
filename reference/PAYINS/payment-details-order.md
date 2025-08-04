---
title: Detalles de un pago (order)
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: payment-details-order
deprecated: false
hidden: false
metadata:
  title: Detalles de un pago (order) | ProntoPaga Docs
  description: >-
    Endpoint to obtain details of a payment using the payment identifier, where
    the order field must be included in the path.
  image: >-
    https://files.readme.io/f4e1f1ce7c0e2f687a7d23c137cbe846822009df6eadba65a01e3cc684c3e570-Prontopaga_logotipo.png
  keywords:
    - payment details
    - Prontopaga
    - Prontopaga api
    - payment details api
    - payment detail Prontopaga
    - endpoint Prontopaga
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

<p><a href="https://www.postman.com/prontopaga-api/workspace/prontopaga-docs/request/34607190-23977bd5-db16-473e-8bd4-e5a4800e28d9?action=share&source=copy-link&creator=45976681" target="_blank">
  <img src="https://run.pstmn.io/button.svg" alt="Run in Postman" style="width: 160px;">
</a></p>

</body>
</html>
`}</HTMLBlock>

***

Endpoint para buscar y obtener los detalles de un pago por medio del número de orden del pago (order number). Se debe enviar el valor de `order` en la ruta.

***