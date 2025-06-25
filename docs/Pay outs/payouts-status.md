---
title: Estados de los pay outs
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    The status of the pay outs are: “new” (request received), “process” (in
    process), “success” (approved) and “canceled” (rejected), with additional
    details on “process” and “canceled”.
  keywords:
    - payouts
    - ' payout statuses'
    - ' statuses'
    - ' prontopaga'
    - ' success'
    - ' canceled'
  robots: index
next:
  description: ''
---
Estos son los posibles estados que pueden tener los pay outs.

| Estado   | Descripción                                                                                                              |
| :------- | :----------------------------------------------------------------------------------------------------------------------- |
| new      | Se ha recibido la solicitud                                                                                              |
| process  | Solicitud en proceso                                                                                                     |
| success  | Solicitud aprobada                                                                                                       |
| canceled | Solicitud rechazada. Conoce los tipos de retiros rechazados [aquí.](https://docs.prontopaga.com/docs/payouts-rejections) |

> 📘 Estado process y canceled
>
> El estado **process** se notifica al momento de procesar el retiro en la entidad bancaria. Sin embargo, el estado **canceled** se puede notificar antes de **process** si se detecta algún dato erróneo o un problema en la entidad bancaria.
