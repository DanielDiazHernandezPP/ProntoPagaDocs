---
title: Crear un nuevo retiro a wallet - Perú
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: instant-payout-peru-wallet
deprecated: false
hidden: false
metadata:
  title: Crear un nuevo retiro a wallet - Perú | ProntoPaga Docs
  description: >-
    Use this endpoint to make an instant payout from your business to a wallet
    in Peru. This guide explains the required parameters, how to use the
    bankCode, and how to confirm transactions through webhooks.
  image: >-
    https://files.readme.io/5ea4fd45a9e5560657cd9c0ece637024d525806f30b3f98e408a52063678c20a-Prontopaga_logotipo.png
  keywords:
    - Peru wallet payout
    - ProntoPaga payout Peru
    - send money to wallet Peru
    - instant withdrawal Peru
    - payout API ProntoPaga
    - crear un retiro a wallet
    - wallet transfer Peru
    - transferir a billetera Perú
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
