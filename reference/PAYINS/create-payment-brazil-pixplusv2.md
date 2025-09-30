---
title: Crear un nuevo pago - Brasil Pix+ v2
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: create-payment-brazil-pixplusv2
deprecated: false
hidden: false
metadata:
  title: Crear un nuevo pago - Brasil Pix+ v2 | ProntoPaga Docs
  description: >-
    Endpoint to create a new payment in Brazil PIX + (Open Finance) with
    ProntoPaga.
  image: >-
    https://files.readme.io/0d8f5a459c9030a38a655f837fb3e141a96cffc2a52af7875510336d744393f0-Prontopaga_logotipo.png
  keywords:
    - create a payment
    - brazil
    - brazil pix
    - brazil pix plus
    - open finance
    - api
    - endpoint
    - body params
    - request
    - examples
    - crear un nuevo pago Prontopaga Brasil
  robots: index
next:
  description: 'Siguiente paso:'
  pages:
    - type: endpoint
      slug: institution-brazil-pixplus-v2
      title: Selección de institución de pago Brasil Pix+ v2
---
Prueba este endpoint directamente en Postman haciendo clic en el siguiente botón:

<HTMLBlock>{`
<!DOCTYPE html>
<html>
<body>

<p><a href="https://www.postman.com/prontopaga-api/workspace/prontopaga-docs/request/34607190-f38af423-8277-4234-a3ad-5f5ed69b252d?action=share&source=copy-link&creator=45976681" target="_blank">
  <img src="https://run.pstmn.io/button.svg" alt="Run in Postman" style="width: 160px;">
</a></p>

</body>
</html>
`}</HTMLBlock>

***

> 📘 Datos del cliente
>
> Como recomendación, la información que se envía en los parámetros del body debería proceder del perfil del cliente.

La respuesta de ProntoPaga a la solicitud de pago es el UID de la transacción y un array con las instituciones para mostrar al cliente, de manera que puedan elegir cómo pagar.

> ❗️ Seleccionar institución
>
> Una vez que el cliente selecciona el banco, deben enviar el id de la institución y el uid del pago en el endpoint de [Selección de institución de pago Brasil Pix+ v2](https://docs.prontopaga.com/reference/institution-brazil-pixplus-v2).

***

## Logos de los métodos de pago

Antes de finalizar tu integración, recuerda agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu front-end. Puedes [descargarlos aquí.](https://prontopagalatam-my.sharepoint.com/:u:/g/personal/tahbet_reategui_prontopaga_com/EWC1ijJHq5JKnjpIH9qH0ncB42rHOzcbXWdiOlyQQHciCA?e=3taLCb\&download=1)

***
