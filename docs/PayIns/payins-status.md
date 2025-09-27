---
title: Conoce los estados de los PayIns
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Conoce los estados de los pay ins | ProntoPaga Docs
  description: >-
    The document describes the possible statuses of pay ins in ProntoPaga, which
    include: new, created, successful, cancelled, rejected, pending and expired.
  image: >-
    https://files.readme.io/3e9d6f50f24cb1db0c6f36214510f01fa0329163510eec6957056185bf5e8b2a-Prontopaga_logotipo.png
  keywords:
    - pay ins statuses
    - payment status
    - status
    - successful
    - rejected
    - estados de pay ins
    - estados Prontopaga
  robots: index
next:
  description: ''
---
Estos son los posibles estados que pueden tener los PayIns.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Estado</b></th>
      <th><b>Descripción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>new</td><td>Estado inicial de la aplicación</td></tr>
    <tr><td>created</td><td>Estado correspondiente a cuando el usuario selecciona el método de pago</td></tr>
    <tr><td>success</td><td>Indica que la transacción fue exitosa</td></tr>
    <tr><td>canceled</td><td>El usuario ha cancelado la transacción</td></tr>
    <tr><td>rejected</td><td>Solicitud rechazada por el método de pago. Conoce los tipos de pagos rechazados <a href="https://docs.prontopaga.com/docs/payins-rejections">aquí</a></td></tr>
    <tr><td>pending</td><td>Solicitud pendiente de aprobación por el método de pago. Normalmente sucede cuando falta algo para completar la transacción (comúnmente en pagos con efectivo)</td></tr>
    <tr><td>expired</td><td>El sistema expira automáticamente las solicitudes pendientes después de cierta cantidad de tiempo</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

| Estado   | Descripción                                                                                                                                                     |
| :------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| new      | Estado inicial de la aplicación.                                                                                                                                |
| created  | Estado correspondiente a cuando el usuario selecciona el método de pago.                                                                                        |
| success  | Indica que la transacción fue exitosa.                                                                                                                          |
| canceled | El usuario ha cancelado la transacción.                                                                                                                         |
| rejected | Solicitud rechazada por el método de pago. Conoce los tipos de pagos rechazados [aquí](https://docs.prontopaga.com/docs/payins-rejections).                     |
| pending  | Solicitud pendiente de aprobación por el método de pago. Normalmente sucede cuando falta algo para completar la transacción (comúnmente en pagos con efectivo). |
| expired  | El sistema expira automáticamente las solicitudes pendientes después de cierta cantidad de tiempo.                                                              |
