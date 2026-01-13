---
title: Conoce los estados de los PayOuts
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Conoce los estados de los payouts | ProntoPaga Docs
  description: >-
    The statuses of the payouts in Prontopaga are: “new” (request received),
    “process” (in process), “success” (approved), and “canceled” (rejected),
    with additional details on “process” and “canceled”.
  image: >-
    https://files.readme.io/639cc6e8b6ccd6cd509c97c8b2a35e9a7d3aa3b234fda90cc41398b537b2a0d0-Prontopaga_logotipo.png
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
Estos son los posibles estados que pueden tener los PayOuts.

| Estado     | Descripción                                                                                                                                                               |
| :--------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `new`      | Se ha recibido la solicitud                                                                                                                                               |
| `process`  | Solicitud en proceso                                                                                                                                                      |
| `success`  | Solicitud aprobada                                                                                                                                                        |
| `canceled` | Solicitud rechazada. Conoce los tipos de retiros rechazados <Anchor label="aquí" target="_blank" href="https://docs.prontopaga.com/docs/payouts-rejections">aquí</Anchor> |

> 📘 Estado process y canceled
>
> El estado `process` se notifica al momento de procesar el retiro en la entidad bancaria. Sin embargo, el estado `canceled` se puede notificar antes de `process` si se detecta algún dato erróneo o un problema en la entidad bancaria.
