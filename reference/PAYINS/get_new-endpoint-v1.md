---
title: Cancelar un pago con QR en Argentina
api:
  file: prontopaga-api.json
  operationId: get_new-endpoint-v1
hidden: true
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

<br />

Con este _endpoint_ puedes cancelar un pago con QR en Argentina buscando la transacción por su `uid`. Esto evita que un cliente conserve la imagen del QR e intente realizar el pago posteriormente.

Los pagos con estado final `SUCCESS` o `REJECTED` no pueden ser cancelados.
