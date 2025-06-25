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

> 🚧 Respuesta exitosa incompleta
>
> En caso de que:
>
> * La fecha final sea anterior a la fecha inicial
> * El tipo de transacción no exista
> * La página no exista
> * Falte un campo obligatorio
>
> Es posible recibir una respuesta 200 OK, pero sin los datos solicitados.
