---
title: Crear un nuevo retiro - Ecuador Payphone
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: payout-ecuador-payphone
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
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