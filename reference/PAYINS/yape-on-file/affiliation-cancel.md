---
title: Cancelar una afiliación
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: affiliation-cancel
deprecated: false
hidden: false
metadata:
  title: Cancelar una afiliación | ProntoPaga Docs
  description: >-
    This endpoint is used to cancel a Yape customer affiliation using the
    ProntoPaga API. This process disables automatic charges to the customer’s
    wallet and removes their consent for future payments. Includes endpoint
    details, parameters, and expected responses. 
  image: >-
    https://files.readme.io/040eb89f8a48d04dc11a674aae752ffa8d7525d9d640d92b568c8a8d7014887c-Prontopaga_logotipo.png
  keywords:
    - endpoint yape
    - yape prontopaga
    - Yape on File
    - One Click Payment
    - cancelar una afiliación Yape
    - cancelar afiliaciones en Yape
  robots: index
next:
  description: ''
---
Prueba este endpoint directamente en Postman haciendo clic en el siguiente botón:

<HTMLBlock>{`
<!DOCTYPE html>
<html>
<body>

<p><a href="https://www.postman.com/prontopaga-api/workspace/prontopaga-docs/request/34607190-bed0cae9-d9ea-4dbe-bdbe-b25f95be4156?action=share&source=copy-link&creator=45976681" target="_blank">
  <img src="https://run.pstmn.io/button.svg" alt="Run in Postman" style="width: 160px;">
</a></p>

</body>
</html>
`}</HTMLBlock>

***

Endpoint para cancelar la afiliación de la wallet de un cliente con tu comercio (ya sea de tipo One Click Payment o de Recurrencia). Una vez finalizado el proceso de cancelación de forma exitosa, el cliente recibirá una notificación push de Yape, confirmando el proceso.