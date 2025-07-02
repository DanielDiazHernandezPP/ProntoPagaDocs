---
title: Consultar transacciones por fecha
api:
  file: prontopaga-api.json
  operationId: post_transactionscustom-date2
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
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