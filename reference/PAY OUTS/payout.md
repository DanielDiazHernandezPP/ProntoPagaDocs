---
title: Crear un nuevo retiro - Chile, Ecuador y Perú
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: payout
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

## Tipos de cuentas por país

Estos son los posibles tipos de cuentas que se pueden enviar en el campo `accountType`.

### Chile

| Tipo de cuenta | Descripción |
| :------------- | :---------- |
| C              | Corriente   |
| S              | Savings     |
| V              | Demand      |

### Ecuador

| Tipo de cuenta | Descripción |
| :------------- | :---------- |
| AHO            | Ahorros     |
| CTE            | Corriente   |

### Perú

| Tipo de cuenta | Descripción |
| :------------- | :---------- |
| A              | Ahorros     |
| C              | Corriente   |

> 🚧 Código bancario
>
> En el parámetro `bankCode`debe enviarse el código del banco al cual se enviará el pay out. Conoce la **lista completa de códigos bancarios** en [este artículo](https://docs.prontopaga.com/docs/bank-codes-transfer).