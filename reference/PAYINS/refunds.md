---
title: Devolución de un pago
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: refunds
deprecated: false
hidden: false
metadata:
  title: Devolución de un pago | ProntoPaga Docs
  description: Endpoint to refund payments with ProntoPaga.
  image: >-
    https://files.readme.io/8ad86258e65f9cb3b9ff72521a49dab4c1babd0254a641d9151edfe49108e884-Prontopaga_logotipo.png
  keywords:
    - refund a payment prontopaga
    - refund payments endpoint
    - prontopaga api
    - request
    - body params Prontopaga
    - devolver un pago prontopaga
  robots: index
next:
  description: ''
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

> 🚧 Importante
>
> Solo los pagos con estado exitoso pueden ser reembolsados.

Endpoint para realizar la devolución de un pago. Actualmente, este servicio está operativo solamente para los siguientes métodos de pago:

* [Servicios de Yape On File: One Click Payments ](https://docs.prontopaga.com/update/docs/yape-on-file-ocp#/)
* [Servicios de Yape On File: Recurrencia](https://docs.prontopaga.com/update/docs/yape-on-file-recurrent#/)

> 📘 Tarjeta Perú
>
> Para casos de devolución con [Tarjeta en Perú](https://docs.prontopaga.com/update/docs/payins-peru-card#/) la solicitud se realiza desde el Portal de servicios.

> ❗️ Número de documento
>
> Para que la devolución sea exitosa, en el campo `clientDocument` debe enviarse el mismo número de documento que el cliente utilizó para realizar la afiliación.

***