---
title: Datos de prueba Chile
excerpt: Conoce los datos de prueba disponibles para Chile
deprecated: false
hidden: false
metadata:
  title: Datos de prueba Chile | ProntoPaga Docs
  description: >-
    This document provides a list of test cards for the Webpay service in Chile,
    indicating the card type, details and whether transactions are approved or
    declined.
  keywords:
    - webpay card numbers
    - Prontopaga chile
    - datos de prueba Chile
    - tarjetas de prueba Chile
    - data test Chile
    - pagos de prueba
    - test credit cards Chile
    - simulate payments Chile
  robots: index
next:
  description: ''
---
> 🚧 Webhook de la transacción
>
> El webhook de la transacción se enviará automáticamente en el ambiente _Sandbox_ únicamente si se utilizan los datos de prueba especificados en nuestra documentación. Para los demás métodos de pago, será necesario contactar con el soporte técnico por correo electrónico, proporcionando el **uid** y la **referencia** de la transacción, para que podamos cambiar el estado a `success` y, de este modo, se reciba el webhook correspondiente.

***

<br />

## Tarjetas

Tarjetas para realizar pagos en modo prueba con el servicio de Webpay en Chile.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Tipo de tarjeta</b></th>
      <th><b>Detalles</b></th>
      <th><b>Resultado</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>VISA (crédito)</td><td>4051 8856 0044 6623 / <b>CVV</b> 123 / Cualquier fecha de caducidad</td><td>Genera transacciones aprobadas.</td></tr>
    <tr><td>AMEX</td><td>3700 0000 0002 032 / <b>CVV</b> 1234 / Cualquier fecha de caducidad</td><td>Genera transacciones aprobadas.</td></tr>
    <tr><td>MasterCard</td><td>5186 0595 5959 0568 / <b>CVV</b> 123 / Cualquier fecha de caducidad</td><td>Genera transacciones rechazadas.</td></tr>
    <tr><td>Red compra (débito)</td><td>4051 8842 3993 7763</td><td>Genera transacciones aprobadas (para operaciones que permiten débito Red compra).</td></tr>
    <tr><td>Red compra</td><td>4511 3466 6003 7060</td><td>Genera transacciones aprobadas (para operaciones que permiten débito Red compra).</td></tr>
		<tr><td>Red compra</td><td>5186 0085 4123 3829</td><td>Genera transacciones rechazadas (para operaciones que permiten débito Red compra).</td></tr></tr>
    <tr><td>Prepago VISA</td><td>4051 8860 0005 6590 / <b>CVV</b> 123 / msg_testCard4</td><td>Genera transacciones aprobadas.</td></tr>
    <tr><td>Prepago MasterCard</td><td>5186 1741 1062 9480 / <b>CVV</b> 123 / Cualquier fecha de caducidad</td><td>Genera transacciones rechazadas.</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

Además, puedes usar los siguientes datos para tus pruebas con Webpay:

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>RUT / RUT Usuario</b></th>
      <th><b>Clave / Clave de transferencia</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>11.111.111-1</td><td>123</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

<br />

## Paga con tu banco

Datos para pruebas en el servicio Paga con tu banco de Chile.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Banco</b></th>
      <th><b>RUT</b></th>
      <th><b>Clave</b></th>
      <th><b>Cuenta</b></th>
      <th><b>Coordenadas</b></th>
      <th><b>Verificación</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Banco Estado</td><td>11111111-1</td><td>1234</td><td>Primera</td><td>NA</td><td>Método: bepass. <br>Clave: 1234</td></tr>
    <tr><td>Banco Santander</td><td>415792638</td><td>jonsnow</td><td>Cualquiera</td><td>00 00 00</td><td>NA</td></tr>
		<tr><td>Banco de Test</td><td>11111111-1</td><td>111111</td><td>Primera</td><td>11 11 11</td><td>11 11 11</td></tr>
  </tbody>
</table>
`}</HTMLBlock>