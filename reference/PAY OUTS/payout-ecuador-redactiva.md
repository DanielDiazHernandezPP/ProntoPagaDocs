---
title: Crear un nuevo retiro - Ecuador Red Activa/Western Union
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: payout-ecuador-redactiva
deprecated: false
hidden: false
metadata:
  title: Create a new payout in Ecuador with Red Activa/Western Union
  description: >-
    This endpoint is used to create a new payout in Ecuador through Red
    Activa/Western Union using the ProntoPaga API. This guide covers required
    parameters, the use of bank code, and webhook confirmation.
  image: >-
    https://files.readme.io/c96314e80fc943d953ebf4adcf880cdb401a8445319d0f407187620f44eef195-Prontopaga_logotipo.png
  keywords:
    - create payout API Ecuador
    - ProntoPaga payout Ecuador
    - bank transfer Ecuador
    - crear retiro ProntoPaga
    - endpoint retiro Ecuador
    - Red Activa Ecuador integración
    - Western Union Ecuador Prontopaga
  robots: index
next:
  description: ''
---
Endpoint para crear una nuevo retiro. Para crear una nueva solicitud de retiro, la solicitud debe construirse con los siguientes parámetros.

> 📘 Webhook
>
> Una vez que el usuario haya completado el proceso de retiro, ProntoPaga devolverá los datos a la URL que hayas especificado en la `confirmationURL`.