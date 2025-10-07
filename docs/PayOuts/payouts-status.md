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

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Estado</b></th>
      <th><b>Descripción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>new</td><td>Se ha recibido la solicitud</td></tr>
    <tr><td>process</td><td>Solicitud en proceso</td></tr>
    <tr><td>success</td><td>Solicitud aprobada</td></tr>
    <tr><td>canceled</td><td>Solicitud rechazada. Conoce los tipos de retiros rechazados <a href="https://docs.prontopaga.com/docs/payouts-rejections">aquí</a></td></tr>
  </tbody>
</table>
`}</HTMLBlock>

> 📘 Estado process y canceled
>
> El estado `process` se notifica al momento de procesar el retiro en la entidad bancaria. Sin embargo, el estado `canceled` se puede notificar antes de `process` si se detecta algún dato erróneo o un problema en la entidad bancaria.
