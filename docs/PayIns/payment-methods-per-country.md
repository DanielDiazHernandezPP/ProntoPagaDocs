---
title: Métodos de pago por país
excerpt: Descubre los diferentes métodos de pago por país, marca y nomenclatura
deprecated: false
hidden: false
metadata:
  title: Métodos de pago por país | ProntoPaga Docs
  description: >-
    Check the available payment methods by country using Prontopaga's API. See
    which options are active in Peru, Brazil, Chile and Ecuador.
  image: >-
    https://files.readme.io/d37e0b58dec644e240350156bf87913fb809021ee3f4b234511cad96dad65233-Prontopaga_logotipo.png
  keywords:
    - payment methods
    - Prontopaga
    - Peru
    - Brazil
    - Chile
    - Ecuador
    - regional payment options
    - fintech
    - métodos de pago
    - endpoints
  robots: index
next:
  description: ''
---
> 👍 Métodos en tu comercio
>
> Recuerda que para conocer los métodos asociados a tu comercio, primero deberás consulta el endpoint de [Métodos de pago](https://docs.prontopaga.com/reference/payment-methods). Solo podrás hacer pruebas con los métodos de pago asociados a tu comercio.

***

<br />

## Chile

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Solución</b></th>
      <th><b>Método de pago</b></th>
      <th><b>Marca</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Tarjeta</td><td>webpay_payment</td><td>Webpay</td></tr>
    <tr><td>Transferencia</td><td>PagaConTuBanco</td><td>Paga con tu Banco</td></tr>
    <tr><td>QR/Wallet</td><td>mercadopagoqr_payment</td><td>Mercado Pago</td></tr>
   	<tr><td>QR/Wallet</td><td>mach_payment</td><td>MACH</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

***

<br />

## Ecuador

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Solución</b></th>
      <th><b>Método de pago</b></th>
      <th><b>Marca</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Tarjeta</td><td>ec_card_payment</td><td>Payphone</td></tr>
    <tr><td>Wallet</td><td>payphone_payment</td><td>Payphone</td></tr>
    <tr><td>Efectivo</td><td>broadnet_payment</td><td>Ponle más</td></tr>
    <tr><td>Efectivo</td><td>bemovil_payment</td><td>Bemovil</td></tr>
   	<tr><td>Efectivo</td><td>redactiva_payment</td><td>Red Activa / Western Union</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

***

<br />

## Perú

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Solución</b></th>
      <th><b>Método de pago</b></th>
      <th><b>Marca</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Tarjeta</td><td>pe_card_payment</td><td>VISA y MasterCard</td></tr>
    <tr><td>Transferencia</td><td>PagaConTuBanco</td><td>Paga con tu Banco</td></tr>
    <tr><td>Wallet</td><td>yape_cof_payment</td><td>Yape On File</td></tr>
    <tr><td>QR</td><td>pe_qr_3_payment</td><td>QR</td></tr>
   	<tr><td>Efectivo</td><td>pagoefectivo_payment</td><td>PagoEfectivo</td></tr>
  </tbody>
</table>
`}</HTMLBlock>
