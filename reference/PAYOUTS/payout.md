---
title: Crear un nuevo retiro - Chile, Ecuador y Perú
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: payout
deprecated: false
hidden: false
metadata:
  title: Crear un nuevo retiro - Chile, Ecuador y Perú | ProntoPaga Docs
  description: >-
    This endpoint is used to create a new payout using the ProntoPaga API. This
    guide covers required parameters, supported account types by country, the
    use of bank codes, and webhook confirmation. Includes links to bank code
    lists for Chile, Ecuador, and Peru. 
  image: >-
    https://files.readme.io/04065208016c1b5950bf489fcd3cc5abd5bba0b1a28d02a0ae0ea3423ebb959c-Prontopaga_logotipo.png
  keywords:
    - create payout API
    - ProntoPaga payout Chile
    - ProntoPaga Ecuador withdrawal
    - bank transfer Peru
    - crear retiro ProntoPaga
    - endpoint retiro Chile Ecuador Perú
  robots: index
next:
  description: ''
---
Prueba este endpoint en la colección de ProntoPaga de Postman haciendo clic en el siguiente botón:

<HTMLBlock>{`
<!DOCTYPE html>
<html>
<body>

<p><a href="https://www.postman.com/prontopaga-api/prontopaga-docs/collection/24iz2pb/prontopaga-api?action=share&source=copy-link&creator=45976681" target="_blank">
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

## Tipos de cuentas por país

Estos son los posibles tipos de cuentas que se pueden enviar en el campo `accountType`.

### Chile

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Tipo de cuenta</b></th>
      <th><b>Descripción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>C</td><td>Corriente</td></tr>
    <tr><td>S</td><td>Savings</td></tr>
    <tr><td>V</td><td>Demand</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

***

### Ecuador

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Tipo de cuenta</b></th>
      <th><b>Descripción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>AHO</td><td>Ahorros</td></tr>
    <tr><td>CTE</td><td>Corriente</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

***

### Perú

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Tipo de cuenta</b></th>
      <th><b>Descripción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>A</td><td>Ahorros</td></tr>
    <tr><td>C</td><td>Corriente</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

***

## Código bancario

En el parámetro `bankCode` debe enviarse el código del banco al cual se enviará el PayOut. Conoce la **lista completa de códigos bancarios** en <Anchor label="este artículo" target="_blank" href="https://docs.prontopaga.com/docs/bank-codes-transfer#/">este artículo</Anchor>.

***

<NmeroDeCaracteres />

***