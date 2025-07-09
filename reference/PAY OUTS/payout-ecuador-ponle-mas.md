---
title: Crear un nuevo retiro - Ecuador Ponle más
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: payout-ecuador-ponle-mas
deprecated: false
hidden: false
metadata:
  title: Create a new payout in Ecuador with Ponle más
  description: >-
    This endpoint is used to create a new payout in Ecuador through Ponle más
    using the ProntoPaga API. This guide covers required parameters, the use of
    bank code, and webhook confirmation.
  image: >-
    https://files.readme.io/50d1ddb3ff59698104655999512ab620e7ff726f3d3ff8e75d8e0d665dcce82f-Prontopaga_logotipo.png
  keywords:
    - create payout API Ecuador
    - ProntoPaga payout Ecuador
    - bank transfer Ecuador
    - crear retiro ProntoPaga
    - endpoint retiro Ecuador
    - Ponle más Ecuador integración
  robots: index
next:
  description: ''
---
Endpoint para crear una nuevo retiro. Para crear una nueva solicitud de retiro, la solicitud debe construirse con los siguientes parámetros.

> 📘 Webhook
>
> Una vez que el usuario haya completado el proceso de retiro, ProntoPaga devolverá los datos a la URL que hayas especificado en la `confirmationURL`.