---
title: Crear un nuevo retiro por transferencia bancaria - Chile, Ecuador y Perú
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: bank-transfer-payout
deprecated: false
hidden: true
metadata:
  title: ''
  description: >-
    Endpoint to create a new bank transfer payout with ProntoPaga. To create a
    new payout, the request must be constructed with the following parameters.
  keywords:
    - bank transfer payout
    - ' transfer payout'
    - ' payout'
    - ' wire transfer payout'
    - ' prontopaga'
    - ' api'
    - ' edpoint'
    - ' body params'
    - ' request'
    - ' response'
    - ' examples'
  robots: index
next:
  description: ''
---
Endpoint para crear una nueva solicitud de retiro por transferencia bancaria. 

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

<br />

> 🚧 Código bancario
> 
> En el parámetro `bankCode`debe enviarse el código del banco al cual se enviará el pay out. Conoce la **lista completa de códigos bancarios** en [este artículo](https://docs.prontopaga.com/docs/bank-codes-transfer).