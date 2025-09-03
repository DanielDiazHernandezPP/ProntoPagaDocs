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

| Solución | Método de pago         | Marca   |
| :------- | :--------------------- | :------ |
| Tarjeta  | latam_chk_card_payment | Tarjeta |

<br />

## Brasil

| Solución                 | Método de pago | Marca |
| :----------------------- | :------------- | :---- |
| QR/Wallet                | pix_payment    | Pix   |
| QR/Wallet (Open-Finance) | belvo_payment  | Pix+  |

<br />

## Chile

| Solución      | Método de pago        | Marca             |
| :------------ | :-------------------- | :---------------- |
| Tarjeta       | webpay_payment        | Webpay            |
| Transferencia | PagaConTuBanco        | Paga con tu Banco |
| QR/Wallet     | mercadopagoqr_payment | Mercado Pago      |
| QR/Wallet     | mach_payment          | MACH              |

<br />

## Ecuador

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

| Solución      | Método de pago       | Marca                |
| :------------ | :------------------- | :------------------- |
| Tarjetas      | pe_card_payment      | VISA y MasterCard    |
| Transferencia | PagaConTuBanco       | Paga con tu banco    |
| Wallet        | yape_payment         | Botón Yape           |
| Wallet        | yape_oneshot_payment | Botón Yape: One Shot |
| Wallet        | yape_cof_payment     | Yape On File         |
| QR            | pe_qr_payment        | QR                   |
| Efectivo      | pagoefectivo_payment | PagoEfectivo         |
