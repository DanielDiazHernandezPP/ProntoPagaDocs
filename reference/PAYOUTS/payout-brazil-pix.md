---
title: Crear un nuevo retiro - Brasil PIX
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: payout-brazil-pix
deprecated: false
hidden: false
metadata:
  title: Crear un nuevo retiro - Brasil PIX | ProntoPaga Docs
  description: >-
    This endpoint is used to create a new payout using the ProntoPaga API. This
    guide covers required parameters, the use of bank code, and webhook
    confirmation.
  image: >-
    https://files.readme.io/f51cda7b4cef2b27a541983c989c232b6ac1f6c9a55a3e1c726dc0a04428d481-Prontopaga_logotipo.png
  keywords:
    - create payout API Brazil
    - ProntoPaga payout Brazil
    - ProntoPaga Brazil withdrawal
    - bank transfer Brazil
    - crear retiro ProntoPaga
    - endpoint retiro Brasil Pix
    - Pix Brasil
  robots: index
next:
  description: ''
---
Prueba este endpoint directamente en Postman haciendo clic en el siguiente botón:

<HTMLBlock>{`
<!DOCTYPE html>
<html>
<body>

<p><a href="https://www.postman.com/prontopaga-api/workspace/prontopaga-docs/request/34607190-0d6476c8-9ce4-4eb0-93ff-38b609e8e8a8?action=share&source=copy-link&creator=45976681" target="_blank">
  <img src="https://run.pstmn.io/button.svg" alt="Run in Postman" style="width: 160px;">
</a></p>

</body>
</html>
`}</HTMLBlock>

***

Endpoint para crear una nuevo retiro. Para crear una nueva solicitud de retiro, la solicitud debe construirse con los siguientes parámetros.

> 📘 Webhook
>
> Una vez que el usuario haya completado el proceso de retiro, ProntoPaga devolverá los datos a la URL que hayas especificado en la `confirmationURL`.

***

## Tipos de cuentas

Estos son los posibles tipos de cuentas que se pueden enviar en el campo `accountType`.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Tipo de cuenta</b></th>
      <th><b>Descripción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>1</td><td>Corrente</td></tr>
    <tr><td>2</td><td>Salario</td></tr>
    <tr><td>3</td><td>Poupança</td></tr>
    <tr><td>4</td><td>Transacional</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

***

<NmeroDeCaracteres />

***
