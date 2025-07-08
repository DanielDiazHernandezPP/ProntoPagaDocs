---
title: Consultar transacciones por fecha
api:
  file: prontopaga-api.json
  operationId: post_transactionscustom-date2
deprecated: false
hidden: false
link:
  new_tab: false
metadata:
  title: 'Check transaction by date '
  description: >-
    ProntoPaga allows you to make requests of your transactions through this
    endpoint, in which you can select: Time period (start date and end date),
    Transaction type and Page number.
  image: >-
    https://files.readme.io/edfa9a193f1380979280da9a707edf72d383fcb32471da78e2b5022759d4fdb4-Prontopaga_logotipo.png
  keywords:
    - transactions by date
    - transactions
    - time period
    - transactions per period
    - prontopaga api
    - endpoint
    - request
    - ver transacciones por fecha Prontopaga
  robots: index
---
ProntoPaga te permite hacer consultas de tus transacciones a través de este endpoint, en el cual puedes seleccionar:

* Periodo de tiempo (fecha inicial y fecha final).
* Tipo de transacción.
* Número de página.
* Cantidad de registros por página.

> 📘 IVA y comisión
>
> Los pagos que tengan un estado diferente a `success` no traerán el detalle del IVA ni de las comisiones en la respuesta de este endpoint.