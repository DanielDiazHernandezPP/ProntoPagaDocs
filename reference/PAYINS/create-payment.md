---
title: Crear un nuevo pago - Chile, Ecuador y Perú
api:
  file: prontopaga-api.json
  operationId: post_paymentnew
deprecated: false
hidden: false
metadata:
  title: >-
    Crear un nuevo pago - Chile, Brasil, Ecuador, Perú y Argentina | ProntoPaga
    Docs
  description: >-
    Endpoint to create a new payment with ProntoPaga in Brasil, Chile, Ecuador.
    Perú and Argentina.
  image: >-
    https://files.readme.io/093d7d2050099106203729c4236a6462fa57ae381bf81269d0d0da85dbe62117-Prontopaga_logotipo.png
  keywords:
    - create a payment
    - create a new payment
    - create a payin
    - prontopaga request
    - body params prontopaga
    - response
    - crear un nuevo pago Prontopaga
  robots: index
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

Endpoint para crear un nuevo pago en Chile, Ecuador y Perú, con distintos métodos. La respuesta de ProntoPaga a la solicitud de pago es el UID de la transacción y la URL a la que debe redirigir al usuario.

> 📘 Datos del cliente
>
> Como recomendación, la información que se envía en los parámetros del body debería proceder del perfil del cliente.

***

### Métodos para tu comercio

Para conocer los métodos de pago asociados a tu comercio, primero deberás hacer una consulta en el endpoint de [Métodos de pago](https://docs.prontopaga.com/reference/payment-methods). Si deseas conocer todos los métodos de pago disponibles en ProntoPaga, consulta [este artículo](https://docs.prontopaga.com/docs/payment-methods-per-country).

### Solicitud a un banco específico (Direct Banks - Chile y Perú)

Para hacer una solicitud a un banco específico, sigue estos pasos:

1. Consulta el endpoint de [Lista de códigos bancarios](https://docs.prontopaga.com/reference/bank-codes)
2. Toma el valor del campo `code`
3. Colócalo en el parámetro `bankCode` de este endpoint.

***

### Logos de los métodos de pago

Antes de finalizar tu integración, recuerda agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu front-end. Puedes [descargarlos aquí.](https://prontopagalatam-my.sharepoint.com/:f:/g/personal/tahbet_reategui_prontopaga_com/EtPhXrMz3TxAtA11de5jVZEB3yowkpS1i2v6lm_eMKkB7g?e=KXcZX5)

***

> 🚧 Número de caracteres
>
> Ten en cuenta que, al obtener una transacción exitosa, el campo `reference` puede contener hasta 20 caracteres.

***
