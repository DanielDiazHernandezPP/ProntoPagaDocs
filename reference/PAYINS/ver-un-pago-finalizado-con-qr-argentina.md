---
title: Ver un pago finalizado con QR - Argentina
api:
  file: prontopaga-api.json
  operationId: get_paymentarqrcomplete{uid}
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  robots: index
---
Prueba este _endpoint_ directamente en Postman haciendo clic en el siguiente botón

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

Este _endpoint_ se utiliza para visualizar el flujo final de **pago con QR en Argentina**. Redirige a la página HTML final de ProntoPaga. Busca el pago mediante su `uid` y no realiza validaciones adicionales ni modifica el estado de la transacción.