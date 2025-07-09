---
title: Crear un nuevo retiro - Ecuador Payphone
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: payout-ecuador-payphone
deprecated: false
hidden: false
metadata:
  title: 'Create a new payout in Ecuador with Payphone '
  description: >-
    This endpoint is used to create a new payout in Ecuador throgout Payphone
    using the ProntoPaga API. This guide covers required parameters, the use of
    bank code, and webhook confirmation.
  image: >-
    https://files.readme.io/7763cb4f35f503a463dfcd76844a1835e8970997fcdbe6211ca99a2b2d4d2797-Prontopaga_logotipo.png
  keywords:
    - create payout API Ecuador
    - ProntoPaga payout Ecuador
    - ProntoPaga Ecuador withdrawal
    - bank transfer Ecuador
    - crear retiro ProntoPaga
    - endpoint retiro Ecuador
    - Payphone Ecuador
  robots: index
next:
  description: ''
---
Endpoint para crear una nuevo retiro. Para crear una nueva solicitud de retiro, la solicitud debe construirse con los siguientes parámetros.

> 📘 Webhook
>
> Una vez que el usuario haya completado el proceso de retiro, ProntoPaga devolverá los datos a la URL que hayas especificado en la `confirmationURL`.

## Estados del retiro en Payphone

| Estado   | Descripción                                                                                                         |
| :------- | :------------------------------------------------------------------------------------------------------------------ |
| Success  | Solicitud aprobada                                                                                                  |
| Canceled | Solicitud rechazada. Conoce los [tipos de retiros cancelados](https://docs.prontopaga.com/docs/payouts-rejections). |

> 📘 Estados
>
> Payphone solo utiliza el estado "success" y "canceled" ya que son pagos instantáneos.