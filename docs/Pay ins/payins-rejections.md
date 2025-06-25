---
title: Tipos de rechazos
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    The document describes common types of rejections for payments in Brazil,
    Chile and Ecuador, including customer blocking, transaction limits, and
    payment system-specific errors.
  keywords:
    - rejections
    - ' payins'
    - ' types'
    - ' payment rejections'
    - ' prontopaga'
  robots: index
next:
  description: ''
---
Los tipos de rechazos posibles para pay ins varían dependiendo del país y del método de pago utilizado. A continuación, se describen los más comunes.

## Brasil

Estos son los tipos de pagos rechazados en Brasil.

### Opción 1 - Cliente bloqueado

El cliente se bloquea en lista negra.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "rejected",
    "message": "The client is blocked"
},
```

### Opción 2 - Limite de comercio

El cliente ha superado los límites establecidos para la transacción o comercio.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "rejected",
    "message": "Exceeds daily limit,
                5,000,000.00 BRL available for the day,
                10,000,000.00 BRL available for the week,
                30,000,000.00 BRL available for the month.
                Maximum deposit per transaction 6,000,000.00 BRL"
},
```

### Opción 3

Error al crear el pago en el servicio Pix.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "rejected",
    "message": "Error while creating the payment in the Pix service. Please try again"
},
```

### Opción 4

Error al generar el código QR Pix.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "rejected",
    "message": "Error generating Pix QR Code"
},
```

### Opción 5

Error al generar el Token de Acceso Pix.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "rejected",
    "message": "Error generating Pix AccessToken"
},
```

<br />

## Chile

Estos son los tipos de pagos rechazados en Chile.

### Opción 1 - Cliente Bloqueado

El cliente se bloquea en lista negra.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "rejected",
    "message": "The client is blocked"
},
```

### Opción 2 - Limite de comercio

El cliente ha superado los límites establecidos para la transacción o comercio.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "rejected",
    "message": "Exceeds daily limit,
                5,000,000.00 CLP available for the day,
                10,000,000.00 CLP available for the week,
                30,000,000.00 CLP available for the month.
                Maximum deposit per transaction 6,000,000.00 CLP"
},
```

<br />

## Ecuador

Estos son los tipos de pagos rechazados en Ecuador.

### Opción 1 - Cliente Bloqueado

El cliente se bloquea en lista negra.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "rejected",
    "message": "The client is blocked"
},
```

### Opción 2 - Limite de comercio

El cliente ha superado los límites establecidos para la transacción o comercio.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "rejected",
    "message": "Exceeds daily limit,
                5,000,000.00 CLP available for the day,
                10,000,000.00 CLP available for the week,
                30,000,000.00 CLP available for the month.
                Maximum deposit per transaction 6,000,000.00 CLP"
},
```

### Opción 3 - Pago pendiente

El cliente tiene una transacción de pago pendiente para ese mismo número de teléfono.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "rejected",
    "message": "There is already a pending payment for that phone number."
},
```

### Opción 4 - Pago fallido

El cliente tiene una transacción de pago pendiente.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "rejected",
    "message": "Failed payment: There is already a pending payment transaction."
},
```

<br />

## Perú

Estos son los tipos de pagos rechazados en Perú.

### Yape

A continuación se listan los posibles **rechazos secundarios** al realizar un pago con Yape (aparecerán en el formulario de pago):

| YAPE_ACTION_CODE | YAPE_ACTION_DESCRIPTION                            |
| :--------------- | :------------------------------------------------- |
| 410              | Operacion denegada. OTP Incorrecto                 |
| 411              | Operacion denegada. Cuenta Inactiva                |
| 412              | Operacion Denegada. Cuenta no permitida            |
| 413              | Limite diario excedido                             |
| 414              | Operacion denegada. OTP Bloqueado                  |
| 415              | Operacion denegada. Cuenta no asociada al programa |
| 416              | Error codigo yape Incorrecto                       |
| 417              | Error codigo yape Incorrecto                       |
| 418              | Error codigo yape Incorrecto                       |
| 503              | Operacion denegada. Problemas de comunicacion      |
| 504              | Operacion denegada. Problemas de comunicacion      |
| 511              | Operacion denegada. Problemas de comunicacion      |
| 599              | Operacion denegada. Problemas de comunicacion      |

### Yape y Tarjeta

Códigos de acción en la respuesta del **autorizador** (al hacer pagos con Yape o con tarjeta en Perú):

| Código de acción | Escenarios                               |
| :--------------- | :--------------------------------------- |
| 101              | Tarjeta vencida                          |
| 102              | Operación no permitida para esta tarjeta |
| 113              | Monto no permitido                       |
| 116              | Fondos insuficientes                     |
| 118              | Tarjeta inválida                         |
| 129              | Tarjeta no operativa                     |
| 180              | Tarjeta inválida                         |
| 208              | Tarjeta perdida                          |
| 209              | Tarjeta robada                           |
| 666              | Problemas de comunicación                |
| 670              | Transacción denegada por posible fraude  |
| 678              | Error en autenticación                   |
| 754              | Comercio no válido                       |
| 191              | Contactar emisor                         |
| 0                | Afiliación a REC no exitosa              |
| 190              | Contactar emisor                         |