---
title: Lista de códigos bancarios
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: bank-codes
deprecated: false
hidden: false
metadata:
  title: Lista de códigos bancarios | ProntoPaga Docs
  description: To see a list of available banks by country, request this endpoint.
  image: >-
    https://files.readme.io/9edb9f042ac1b31726d25ed524206b73f8fb508a4ac9c7d75f9e8c21e61f9254-Prontopaga_logotipo.png
  keywords:
    - bank codes
    - available banks
    - banks by country
    - prontopaga api
    - endpoint
    - request
    - body params Prontopaga
    - lista de códigos bancarios prontopaga
  robots: index
next:
  description: ''
---
Para ver una lista de los bancos disponibles por país, haz una solicitud a este endpoint o da clic en el siguiente botón:

<HTMLBlock>{`
<!DOCTYPE html>
<html>
<body>

<p><a href="https://www.postman.com/prontopaga-api/workspace/prontopaga-docs/request/34607190-7773944d-8c4a-434f-95d8-ee582f401e96?action=share&source=copy-link&creator=45976681" target="_blank">
  <img src="https://run.pstmn.io/button.svg" alt="Run in Postman" style="width: 160px;">
</a></p>

</body>
</html>
`}</HTMLBlock>

***

## Países

Se debe enviar en la URL el código de país en formato ISO 3166-1 alpha-2.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>País</b></th>
      <th><b>Código</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>chile</td><td>CL</td></tr>
    <tr><td>Ecuador</td><td>EC</td></tr>
		<tr><td>Perú</td><td>PE</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

***