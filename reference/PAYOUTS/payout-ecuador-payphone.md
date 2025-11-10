---
title: Crear un nuevo retiro - Ecuador Payphone
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: payout-ecuador-payphone
deprecated: false
hidden: false
metadata:
  title: Crear un nuevo retiro - Ecuador Payphone | ProntoPaga Docs
  description: >-
    This endpoint is used to create a new payout in Ecuador through Payphone
    using the ProntoPaga API. This guide covers required parameters, the use of
    bank code, and webhook confirmation.   
  image: >-
    https://files.readme.io/7763cb4f35f503a463dfcd76844a1835e8970997fcdbe6211ca99a2b2d4d2797-Prontopaga_logotipo.png
  keywords:
    - create payout API Ecuador
    - ProntoPaga payout Ecuador
    - ProntoPaga Ecuador withdrawal
    - bank transfer Ecuador
    - crear retiro ProntoPaga
    - endpoint retiro Ecuador
    - Payphone Ecuador
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

### Logos de los métodos de retiro

Antes de finalizar tu integración, recuerda agregar los logotipos de los diferentes métodos de ProntoPaga a tu front-end. Puedes [descargarlos aquí.](https://drive.google.com/uc?export=download\&id=1MmsVaugP7ztzRXA_dK9wNrwKJOfHSL59)

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
