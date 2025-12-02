---
title: Devolver un pago - QR - Argentina
api:
  file: prontopaga-api.json
  operationId: get_transactionrefund
deprecated: false
hidden: true
metadata:
  robots: index
---
Prueba este endpoint directamente en Postman haciendo clic en el siguiente botón:

<HTMLBlock>{`
<!DOCTYPE html>
<html>
<body>

<p><a href="https://www.postman.com/prontopaga-api/workspace/prontopaga-docs/request/34607190-924fdaa9-39de-4540-81ee-0a9bd841c496?action=share&source=copy-link&creator=45976681" target="_blank">
  <img src="https://run.pstmn.io/button.svg" alt="Run in Postman" style="width: 160px;">
</a></p>

</body>
</html>
`}</HTMLBlock>

***

Este endpoint permite hacer la devolución de un pago con QR en Argentina. 

> ❗️ Monto de la devolución
>
> Debes especificar el monto a reembolsar (min: 0.01, max: 99999999999.99), si no se especifica, se reembolsará el monto total disponible.

<br />
