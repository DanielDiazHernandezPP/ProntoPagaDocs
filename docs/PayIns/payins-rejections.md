---
title: Tipos de rechazos (PayIns)
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Tipos de rechazos (PayIns) | ProntoPaga Docs
  description: >-
    The document describes common types of rejections for payments in Brazil,
    Chile, Ecuador and Peru, including customer blocking, transaction limits,
    and payment system-specific errors.
  image: >-
    https://files.readme.io/db77d5d688b748ca74e3599fde8da46f4e41ed804872c28d67fd75bf242b1f74-Prontopaga_logotipo.png
  keywords:
    - Prontopaga
    - payins rejections
    - types of rejections prontopaga
    - rechazos prontopaga
    - pago rechazado prontopaga
    - pago denegado
  robots: index
next:
  description: ''
---
Los tipos de rechazos posibles para PayIns varían dependiendo del país y del método de pago utilizado. A continuación, se describen los más comunes.

## Brasil 🇧🇷

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

***

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

***

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

***

## Perú

Estos son los tipos de pagos rechazados en Perú.

### Yape - Primarios

Estos son los posibles **motivos de rechazo primarios** para pagos con Yape.

> ❗️ Integración sin iFrame
>
> En el caso de integraciones de [Yape sin iFrame](https://docs.prontopaga.com/docs/payins-peru-wallet#crea-un-nuevo-pago-sin-iframe), los mensajes de rechazo de la tabla de abajo son los que el comercio deberá mostrar al cliente en el front-end. Este código y mensaje te será entregado en la respuesta, en el campo `errorMessage`.
>
> Además, hay 3 rechazos que son especialmente importantes para los pagos realizados con la integración de Yape vía API (sin iFrame). Estos son los rechazos en donde ya no es posible colocar otro OTP:
>
> * Límite diario excedido (> 500.00).
> * Cuenta bloqueada por OTP.
> * 3er intento de OTP incorrecto.

| Action_code | Mensaje del rechazo                                                           |
| :---------- | :---------------------------------------------------------------------------- |
| 101         | Tarjeta vencida                                                               |
| 116         | Fondos insuficientes                                                          |
| 118         | Tarjeta inválida                                                              |
| 129         | Tarjeta no operativa                                                          |
| 208         | Tarjeta perdida                                                               |
| 209         | Tarjeta robada                                                                |
| 666         | Problemas de comunicación                                                     |
| 413         | Excediste el límite diario de pagos con Yape                                  |
| 414         | Tu cuenta fue bloqueada. Vuelve a intentar en 24 horas                        |
| 418         | Ingresaste 3 códigos de aprobación incorrectos. Vuelve a intentar en 24 horas |

> 👍 Datos de prueba
>
> Puedes hacer pruebas de los escenarios de rechazo anteriores con los datos listados en [esta página](https://docs.prontopaga.com/docs/test-data-cards-peru#bot%C3%B3n-yape).

### Yape - Secundarios

A continuación se listan los posibles **rechazos secundarios** al realizar un pago con Yape (aparecerán en el formulario de pago):

> ❗️ errorMessage
>
> Tanto el action_code, como el Mensaje de rechazo te será entregado en la respuesta, en el campo `errorMessage`.

| Action_code | Mensaje del rechazo                                |
| :---------- | :------------------------------------------------- |
| 410         | Operacion denegada. OTP Incorrecto                 |
| 411         | Operacion denegada. Cuenta Inactiva                |
| 412         | Operacion Denegada. Cuenta no permitida            |
| 413         | Limite diario excedido                             |
| 414         | Operacion denegada. OTP Bloqueado                  |
| 415         | Operacion denegada. Cuenta no asociada al programa |
| 416         | Error codigo yape Incorrecto                       |
| 417         | Error codigo yape Incorrecto                       |
| 418         | Error codigo yape Incorrecto                       |
| 503         | Operacion denegada. Problemas de comunicacion      |
| 504         | Operacion denegada. Problemas de comunicacion      |
| 511         | Operacion denegada. Problemas de comunicacion      |
| 599         | Operacion denegada. Problemas de comunicacion      |

### Tarjeta - Autorizador

Códigos de acción en la respuesta del **autorizador** (al hacer pagos con tarjeta en Perú):

> ❗️ errorMessage
>
> Tanto el action_code, como el Mensaje de rechazo te será entregado en la respuesta, en el campo `errorMessage`.

| Action_code | Mensaje del rechazo                      |
| :---------- | :--------------------------------------- |
| 101         | Tarjeta vencida                          |
| 102         | Operación no permitida para esta tarjeta |
| 113         | Monto no permitido                       |
| 116         | Fondos insuficientes                     |
| 118         | Tarjeta inválida                         |
| 129         | Tarjeta no operativa                     |
| 180         | Tarjeta inválida                         |
| 208         | Tarjeta perdida                          |
| 209         | Tarjeta robada                           |
| 666         | Problemas de comunicación                |
| 670         | Transacción denegada por posible fraude  |
| 678         | Error en autenticación                   |
| 754         | Comercio no válido                       |
| 191         | Contactar emisor                         |
| 0           | Afiliación a REC no exitosa              |
| 190         | Contactar emisor                         |
