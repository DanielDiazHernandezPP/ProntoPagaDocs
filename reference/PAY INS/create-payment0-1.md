---
title: Crear un nuevo pago - Chile, Brasil, Ecuador y Perú
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: create-payment
deprecated: false
hidden: true
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
Endpoint para crear un nuevo pago en Chile, Brasil, Ecuador y Perú, con distintos métodos. La respuesta de ProntoPaga a la solicitud de pago es el UID de la transacción y la URL a la que debe redirigir al usuario.

> 📘 Datos del cliente
>
> Como recomendación, la información que se envía en los parámetros del body debería proceder del perfil del cliente.

### Métodos para tu comercio

Para conocer los métodos de pago asociados a tu comercio, primero deberás hacer una consulta en el endpoint de [Métodos de pago](https://docs.prontopaga.com/reference/payment-methods). Si deseas conocer todos los métodos de pago disponibles en ProntoPaga, consulta [este artículo](https://docs.prontopaga.com/docs/payment-methods-per-country).

### Solicitud a un banco específico (Direct Banks - Chile y Perú)

Para hacer una solicitud a un banco específico, sigue estos pasos:

1. Consulta el endpoint de [Lista de códigos bancarios](https://docs.prontopaga.com/reference/bank-codes)
2. Toma el valor del campo `code`
3. Colócalo en el parámetro `bankCode` de este endpoint.

### Logos de los métodos de pago

Antes de finalizar tu integración, recuerda agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu front-end. Puedes [descargarlos aquí.](https://drive.google.com/uc?export=download\&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr)