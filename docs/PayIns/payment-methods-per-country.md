---
title: Métodos de pago por país
excerpt: ''
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
En esta página están listados todos los métodos de pago por país, así como su nomenclatura dentro de ProntoPaga.

> 👍 Métodos en tu comercio
>
> Recuerda que para conocer los métodos asociados a tu comercio, primero deberás consulta el endpoint de [Métodos de pago](https://docs.prontopaga.com/reference/payment-methods). Solo podrás hacer pruebas con los métodos de pago asociados a tu comercio.

<br />

## Argentina

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
    <tr><td>Tarjeta</td><td>latam_chk_card_payment</td><td>Visa y Mastercard</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

| Solución | Método de pago         | Marca             |
| :------- | :--------------------- | :---------------- |
| Tarjeta  | latam_chk_card_payment | Visa y Mastercard |

<br />

## Brasil

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
    <tr><td>QR/Wallet</td><td>pix_payment</td><td>Pix</td></tr>
   	<tr><td>QR/Wallet (Open-Finance)</td><td>belvo_payment</td><td>Pix+</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

| Solución                 | Método de pago | Marca |
| :----------------------- | :------------- | :---- |
| QR/Wallet                | pix_payment    | Pix   |
| QR/Wallet (Open-Finance) | belvo_payment  | Pix+  |

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

| Solución      | Método de pago        | Marca             |
| :------------ | :-------------------- | :---------------- |
| Tarjeta       | webpay_payment        | Webpay            |
| Transferencia | PagaConTuBanco        | Paga con tu Banco |
| QR/Wallet     | mercadopagoqr_payment | Mercado Pago      |
| QR/Wallet     | mach_payment          | MACH              |

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
    <tr><td>Transferencia</td><td>PagaConTuBanco</td><td>Paga con tu Banco</td></tr>
    <tr><td>Wallet</td><td>payphone_payment</td><td>Payphone</td></tr>
    <tr><td>Efectivo</td><td>broadnet_payment</td><td>Ponle más</td></tr>
    <tr><td>Efectivo</td><td>bemovil_payment</td><td>Bemovil</td></tr>
   	<tr><td>Efectivo</td><td>redactiva_payment</td><td>Red Activa / Western Union</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

| Solución      | Método de pago    | Marca                      |
| :------------ | :---------------- | :------------------------- |
| Tarjeta       | ec_card_payment   | Payphone                   |
| Transferencia | PagaConTuBanco    | Paga con tu Banco          |
| Wallet        | payphone_payment  | Payphone                   |
| Efectivo      | broadnet_payment  | Ponle más                  |
| Efectivo      | bemovil_payment   | Bemovil                    |
| Efectivo      | redactiva_payment | Red Activa / Western Union |

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
    <tr><td>Wallet</td><td>yape_payment</td><td>Botón Yape</td></tr>
    <tr><td>Wallet</td><td>yape_oneshot_payment</td><td>Botón Yape: One Shot</td></tr>
    <tr><td>Wallet</td><td>yape_cof_payment</td><td>Yape On File</td></tr>
    <tr><td>QR</td><td>pe_qr_payment</td><td>QR</td></tr>
   	<tr><td>Efectivo</td><td>pagoefectivo_payment</td><td>PagoEfectivo</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

| Solución      | Método de pago       | Marca                |
| :------------ | :------------------- | :------------------- |
| Tarjeta       | pe_card_payment      | VISA y MasterCard    |
| Transferencia | PagaConTuBanco       | Paga con tu banco    |
| Wallet        | yape_payment         | Botón Yape           |
| Wallet        | yape_oneshot_payment | Botón Yape: One Shot |
| Wallet        | yape_cof_payment     | Yape On File         |
| QR            | pe_qr_payment        | QR                   |
| Efectivo      | pagoefectivo_payment | PagoEfectivo         |
