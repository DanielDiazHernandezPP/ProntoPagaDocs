---
title: Cancelar un pago con QR - Argentina - Opción B
api:
  file: prontopaga-api.json
  operationId: get_paymentarqr_2cancel{uid}
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  robots: index
---
Prueba este _endpoint_ en la colección de Postman de ProntoPaga haciendo clic en el siguiente botón:

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

Con este _endpoint_ puedes cancelar un pago con QR en Argentina buscando la transacción por su `uid`. Esto evita que un cliente conserve la imagen del QR o código e intente realizar el pago posteriormente.

El _endpoint_ responde con una página HTML de ProntoPaga, donde se muestra el estado cancelado de la transacción.

Los pagos con estado final `SUCCESS` o `REJECTED` no pueden ser cancelados.