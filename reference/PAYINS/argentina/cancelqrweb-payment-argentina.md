---
title: Cancelar un pago con QR/Wallet- QR web
api:
  file: prontopaga-api.json
  operationId: get_new-endpoint-cancelQR
hidden: false
metadata:
  title: Cancelar un pago con QR - Argentina | ProntoPaga Docs
  description: Endpoint to cancel a payment QR web with ProntoPaga in Argentina.
  image: >-
    https://files.readme.io/9c387287ec24692f6f0ccd9e3798b812d371f2e13798e9275e26cbd465b5b63e-Captura_de_pantalla_2025-09-08_a_las_4.24.49_p._m..png
  keywords:
    - endpoint Prontopaga
    - cancel a QR
    - cancel a payment
    - qr argentina prontopaga
    - api prontopaga
    - cancelar un pago con QR Argentina
---
Prueba este _endpoint_ en la colección de Postman de ProntoPaga haciendo clic en el siguiente botón

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

Con este _endpoint_ puedes cancelar un pago con **QR web en Argentina** buscando la transacción por su `uid`. Esto evita que un cliente conserve la imagen del QR e intente realizar el pago posteriormente.

El _endpoint_ responde con una página HTML de ProntoPaga, donde se muestra el estado cancelado de la transacción.

<Callout icon="❗️" theme="error">
  **Ten en cuenta que**

  Los pagos con estado final `SUCCESS` o `REJECTED` no pueden ser cancelados.
</Callout>

<br />