---
title: Datos de prueba Chile
excerpt: ''
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

| Tipo de tarjeta     | Detalle                                                      | Resultado                                                                          |
| :------------------ | :----------------------------------------------------------- | :--------------------------------------------------------------------------------- |
| VISA (crédito)      | 4051 8856 0044 6623 **CVV** 123 Cualquier fecha de caducidad | Genera transacciones aprobadas.                                                    |
| AMEX                | 3700 0000 0002 032 **CVV** 1234 Cualquier fecha de caducidad | Genera transacciones aprobadas.                                                    |
| MasterCard          | 5186 0595 5959 0568 **CVV** 123 Cualquier fecha de caducidad | Genera transacciones rechazadas.                                                   |
| Red compra (débito) | 4051 8842 3993 7763                                          | Genera transacciones aprobadas (para operaciones que permiten débito Red compra).  |
| Red compra          | 4511 3466 6003 7060                                          | Genera transacciones aprobadas (para operaciones que permiten débito Red compra).  |
| Red compra          | 5186 0085 4123 3829                                          | Genera transacciones rechazadas (para operaciones que permiten débito Red compra). |
| Prepago VISA        | 4051 8860 0005 6590 **CVV** 123 msg_testCard4                | Genera transacciones aprobadas.                                                    |
| Prepago MasterCard  | 5186 1741 1062 9480 **CVV** 123 Cualquier fecha de caducidad | Genera transacciones rechazadas.                                                   |

Además, puedes usar los siguientes datos para tus pruebas con Webpay:

<br />

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

| RUT / RUT Usuario | Clave / Clave de transferencia |
| :---------------- | :----------------------------- |
| 11.111.111-1      | 123                            |

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
    
  </tbody>
</table>
`}</HTMLBlock>

| Banco           | RUT        | Clave   | Cuenta     | Coordenadas | Verificación                |
| :-------------- | :--------- | :------ | :--------- | :---------- | :-------------------------- |
| Banco Estado    | 11111111-1 | 1234    | Primera    | NA          | Método: bepass. Clave: 1234 |
| Banco Santander | 415792638  | jonsnow | Cualquiera | 00 00 00    | NA                          |
| Banco de Test   | 11111111-1 | 111111  | Primera    | 11 11 11    | 11 11 11                    |
