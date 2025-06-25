---
title: Crear un nuevo pago - Brasil Pix+ v2
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: create-payment-brazil-pixplusv2
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    Endpoint to create a new payment in Brazil PIX + (Open Finance) with
    ProntoPaga.
  keywords:
    - create a payment
    - ' brazil'
    - ' brazil pix'
    - ' brazil pix plus'
    - ' open finance'
    - ' api'
    - ' endpoint'
    - ' body params'
    - ' request'
    - ' examples'
    - ' response'
  robots: index
next:
  description: 'Siguiente paso:'
  pages:
    - type: endpoint
      slug: institution-brazil-pixplus-v2
      title: Selección de institución de pago Brasil Pix+ v2
---
> 📘 Datos del cliente
> 
> Como recomendación, la información que se envía en los parámetros del body debería proceder del perfil del cliente.

La respuesta de ProntoPaga a la solicitud de pago es el UID de la transacción y un array con las instituciones para mostrar al cliente, de manera que puedan elegir cómo pagar.

> ❗️ Seleccionar institución
> 
> Una vez que el cliente selecciona el banco, deben enviar el id de la institución y el uid del pago en el endpoint de [Selección de institución de pago Brasil Pix+ v2](https://docs.prontopaga.com/reference/institution-brazil-pixplus-v2).

## Logos de los métodos de pago

Antes de finalizar tu integración, recuerda agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu front-end. Puedes [descargarlos aquí.](https://drive.google.com/uc?export=download&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr)