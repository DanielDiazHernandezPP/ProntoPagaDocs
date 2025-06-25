---
title: Crear un nuevo pago - Chile, Brasil, Ecuador y Perú
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: create-payment
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    Endpoint to create a new payment with ProntoPaga in Brasil, Chile, Ecuador
    and Perú.
  keywords:
    - create a payment
    - ' create a new payment'
    - ' create a payin'
    - ' prontopaga'
    - ' request'
    - ' body params'
    - ' response'
    - ' examples'
  robots: index
next:
  description: ''
---
> 📘 Datos del cliente
>
> Como recomendación, la información que se envía en los parámetros del body debería proceder del perfil del cliente.

La respuesta de ProntoPaga a la solicitud de pago es el UID de la transacción y la URL a la que debe redirigir al usuario.

## Logos de los métodos de pago

Antes de finalizar tu integración, recuerda agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu front-end. Puedes [descargarlos aquí.](https://drive.google.com/uc?export=download\&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr)

## Métodos por país

### Brasil

<div class="table-five-columns">

| Solución                 | Método de pago | Marca |
| :----------------------- | :------------- | :---- |
| QR/Wallet                | pix\_payment   | Pix   |
| QR/Wallet (Open-Finance) | belvo\_payment | Pix+  |

### Chile

| Solución      | Método de pago         | Marca             |
| :------------ | :--------------------- | :---------------- |
| Tarjeta       | webpay\_payment        | Webpay            |
| Transferencia | PagaConTuBanco         | Paga con tu Banco |
| QR/Wallet     | mercadopagoqr\_payment | Mercado Pago      |
| QR/Wallet     | mach\_payment          | MACH              |

### Ecuador

| Solución      | Método de pago     | Marca                      |
| :------------ | :----------------- | :------------------------- |
| Transferencia | PagaConTuBanco     | Paga con tu Banco          |
| Wallet        | payphone\_payment  | Payphone                   |
| Efectivo      | broadnet\_payment  | Ponle más                  |
| Efectivo      | bemovil\_payment   | Bemovil                    |
| Efectivo      | redactiva\_payment | Red Activa / Western Union |

### Perú

| Solución      | Método de pago        | Marca             |
| :------------ | :-------------------- | :---------------- |
| Tarjetas      | pe\_card\_payment     | VISA y MasterCard |
| Transferencia | PagaConTuBanco        | Paga con tu banco |
| Wallet        | yape\_payment         | Botón Yape        |
| QR            | pe\_qr\_payment       | QR                |
| Efectivo      | pagoefectivo\_payment | PagoEfectivo      |

</div>

> 👍 Solicitud a un banco específico (Direct Banks - Chile y Perú)
>
> Para hacer una solicitud a un banco específico, primero debes consultar el endpoint de [Lista de códigos bancarios](https://docs.prontopaga.com/reference/bank-codes), tomar el valor del campo `code` y colocarlo en el parámetro `bankCode` de este endpoint. Puedes ver un ejemplo en nuestra sección de [Recipes](https://docs.prontopaga.com/recipes/crea-un-solicitud-de-pago-a-un-banco-espec%C3%ADfico-direct-banks).
