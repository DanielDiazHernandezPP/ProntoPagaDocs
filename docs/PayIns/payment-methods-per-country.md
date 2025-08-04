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

## Brasil

| Solución                 | Método de pago | Marca |
| :----------------------- | :------------- | :---- |
| QR/Wallet                | pix\_payment   | Pix   |
| QR/Wallet (Open-Finance) | belvo\_payment | Pix+  |

<br />

## Chile

| Solución      | Método de pago         | Marca             |
| :------------ | :--------------------- | :---------------- |
| Tarjeta       | webpay\_payment        | Webpay            |
| Transferencia | PagaConTuBanco         | Paga con tu Banco |
| QR/Wallet     | mercadopagoqr\_payment | Mercado Pago      |
| QR/Wallet     | mach\_payment          | MACH              |

<br />

## Ecuador

| Solución      | Método de pago     | Marca                      |
| :------------ | :----------------- | :------------------------- |
| Tarjeta       | ec\_card\_payment  | Payphone                   |
| Transferencia | PagaConTuBanco     | Paga con tu Banco          |
| Wallet        | payphone\_payment  | Payphone                   |
| Efectivo      | broadnet\_payment  | Ponle más                  |
| Efectivo      | bemovil\_payment   | Bemovil                    |
| Efectivo      | redactiva\_payment | Red Activa / Western Union |

<br />

## Perú

| Solución      | Método de pago         | Marca                |
| :------------ | :--------------------- | :------------------- |
| Tarjetas      | pe\_card\_payment      | VISA y MasterCard    |
| Transferencia | PagaConTuBanco         | Paga con tu banco    |
| Wallet        | yape\_payment          | Botón Yape           |
| Wallet        | yape\_oneshot\_payment | Botón Yape: One Shot |
| Wallet        | yape\_cof\_payment     | Yape On File         |
| QR            | pe\_qr\_payment        | QR                   |
| Efectivo      | pagoefectivo\_payment  | PagoEfectivo         |