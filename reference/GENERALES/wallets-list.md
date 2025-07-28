---
title: Lista de wallets - Perú
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: wallets-list
deprecated: false
hidden: false
metadata:
  title: List of wallets Peru
  description: >-
    Endpoint to obtain the available wallets. You can get the total list or the
    wallets associated to a certain phone number.
  image: >-
    https://files.readme.io/030e02b11cd0298def34d356b4191da63aa7cb1ff9379e8a8e0faf156783f5a7-Prontopaga_logotipo.png
  keywords:
    - wallets list Prontopaga
    - peru wallets
    - available wallets
    - wallets per phone number
    - prontopaga api
    - endpoint
    - lista de wallets perú
  robots: index
next:
  description: ''
---
Endpoint para obtener las wallets disponibles. Prueba este endpoint directamente en Postman haciendo clic en el siguiente botón:

<HTMLBlock>{`
<!DOCTYPE html>
<html>
<body>

<p><a href="https://www.postman.com/prontopaga-api/workspace/prontopaga-docs/request/34607190-ca2980b2-0aaf-40a2-bae3-6a38ae6dad5c?action=share&source=copy-link&creator=45976681" target="_blank">
  <img src="https://run.pstmn.io/button.svg" alt="Run in Postman" style="width: 160px;">
</a></p>

</body>
</html>
`}</HTMLBlock>

***

> 🚧 Número telefónico
>
> El envío del `{teléfono}` en la URL es opcional. Si se manda, recibirás como respuesta las wallets asociadas a ese número telefónico. Si no se manda, recibirás una lista de todas las wallets disponibles.

<br />

***