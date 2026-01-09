---
title: Ver flujo final QR/Wallet- QR web
api:
  file: prontopaga-api.json
  operationId: get_paymentarqrcomplete{uid}
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  title: Ver flujo final de pago con QR/Wallet - Argentina | ProntoPaga Docs
  description: >-
    This endpoint allows you to view the final payment flow A for QR and wallet
    payments in Argentina. It redirects the user to a ProntoPaga-hosted HTML
    page that displays the current status of the transaction.
  image: >-
    https://files.readme.io/f4c43363d78eaad106bb6aaa084e14289de5102423a9f935532c7babce1bc35d-Prontopaga_logotipo.png
  keywords:
    - view a QR payment
    - Prontopaga argentina
    - qr
    - wallet
    - payment argentina
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

Este _endpoint_ se utiliza para visualizar el flujo final de **pago con QR en Argentina**. Redirige a la página HTML final de ProntoPaga. Busca el pago mediante su `uid` y no realiza validaciones adicionales ni modifica el estado de la transacción.

***