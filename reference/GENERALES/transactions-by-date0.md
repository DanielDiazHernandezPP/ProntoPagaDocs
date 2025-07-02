---
title: Consultar transacciones por fecha
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: transactions-by-date
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    ProntoPaga allows you to make requests of your transactions through this
    endpoint, in which you can select: Time period (start date and end date),
    Transaction type and Page number.
  keywords:
    - transactions by date
    - ' transactions'
    - ' time period'
    - ' transactions per period'
    - ' prontopaga'
    - ' api'
    - ' endpoint'
    - ' request'
  robots: index
next:
  description: ''
---
ProntoPaga te permite hacer consultas de tus transacciones a través de este endpoint, en el cual puedes seleccionar:

* Periodo de tiempo (fecha inicial y fecha final).
* Tipo de transacción.
* Número de página.
* Cantidad de registros por página.

> 📘 IVA y comisión
>
> Los pagos que tengan un estado diferente a `success` no traerán el detalle del IVA ni de las comisiones en la respuesta de este endpoint.