---
title: Devolución de un pago - QR - Argentina
api:
  file: prontopaga-api.json
  operationId: get_transactionrefund
deprecated: false
hidden: true
metadata:
  robots: index
---
<br />

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

> 🚧 Importante
>
> Solo los pagos con estado exitoso pueden ser reembolsados.

Endpoint para realizar la devolución de un pago. Actualmente, este servicio está operativo solamente para los siguientes métodos de pago:

* [Tarjeta Perú](https://docs.prontopaga.com/update/docs/payins-peru-card#/)
* [QR (PE)](https://docs.prontopaga.com/docs/payins-peru-qr#/)
* [Servicios de Yape On File: One Click Payments ](https://docs.prontopaga.com/update/docs/yape-on-file-ocp#/)
* [Servicios de Yape On File: Recurrencia](https://docs.prontopaga.com/update/docs/yape-on-file-recurrent#/)
* [Payphone Wallet](https://docs.prontopaga.com/update/docs/payins-ecuador-wallet#/)
* [Payphone Tarjeta](https://docs.prontopaga.com/update/docs/payins-ecuador-card#/)

> ❗️ Número de documento
>
> Para que la devolución sea exitosa, en el campo `clientDocument` debe enviarse el mismo número de documento que el cliente utilizó para realizar la afiliación.
