---
title: Crear un nuevo retiro - Ecuador Bemovil
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: payout-ecuador-bemovil
deprecated: false
hidden: false
metadata:
  title: Create a new payout in Ecuador with Bemovil
  description: >-
    This endpoint is used to create a new payout in Ecuador through Payphone
    using the ProntoPaga API. This guide covers required parameters, the use of
    bank code, and webhook confirmation.    
  image: >-
    https://files.readme.io/edb211052843808b0f51395a675a8f8542047687bac1131515f0ffa1f279e9e0-Prontopaga_logotipo.png
  keywords:
    - create payout API Ecuador
    - ProntoPaga payout Ecuador
    - bank transfer Ecuador
    - crear retiro ProntoPaga
    - endpoint retiro Ecuador
    - Bemovil Ecuador integración
  robots: index
next:
  description: ''
---
Endpoint para crear una nuevo retiro. Para crear una nueva solicitud de retiro, la solicitud debe construirse con los siguientes parámetros.

> 📘 Webhook
>
> Una vez que el usuario haya completado el proceso de retiro, ProntoPaga devolverá los datos a la URL que hayas especificado en la `confirmationURL`.