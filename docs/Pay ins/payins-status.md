---
title: Estados de los pay ins
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    The document describes the possible statuses of pay ins in ProntoPaga, which
    include: new, created, successful, cancelled, rejected, pending and expired.
  keywords:
    - pay ins
    - ' statuses'
    - ' payment status'
    - ' status'
    - ' successful'
    - ' rejected'
    - ' prontopaga'
  robots: index
next:
  description: ''
---
Estos son los posibles estados que pueden tener los pay ins.

| Estado   | Descripción                                                                                                                                                     |
| :------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| new      | Estado inicial de la aplicación.                                                                                                                                |
| created  | Estado correspondiente a cuando el usuario selecciona el método de pago.                                                                                        |
| success  | Indica que la transacción fue exitosa.                                                                                                                          |
| canceled | El usuario ha cancelado la transacción.                                                                                                                         |
| rejected | Solicitud rechazada por el método de pago. Conoce los tipos de pagos rechazados [aquí](https://docs.prontopaga.com/docs/payins-rejections).                     |
| pending  | Solicitud pendiente de aprobación por el método de pago. Normalmente sucede cuando falta algo para completar la transacción (comúnmente en pagos con efectivo). |
| expired  | El sistema expira automáticamente las solicitudes pendientes después de cierta cantidad de tiempo.                                                              |