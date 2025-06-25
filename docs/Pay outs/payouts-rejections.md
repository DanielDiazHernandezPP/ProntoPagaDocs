---
title: Tipos de rechazos
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    The document describes the types of rejections possible for payouts in
    Brazil, Chile and Ecuador, including reasons such as blocked customer, trade
    limits, insufficient balance and various specific banking errors.
  keywords:
    - payouts
    - ' payout rejections'
    - ' rejections'
    - ' cancelled'
    - ' rejected'
    - ' prontopaga'
  robots: index
next:
  description: ''
---
A continuación se describen todos los posibles tipos de rechazos para pay outs. El número corresponde al número que se devuelve en el campo `errorCode` del rechazo.

## Generales (todos los países)

### 1 - Cliente bloqueado

El cliente está bloqueado en lista negra.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "El cliente se encuentra bloqueado",
    "errorCode": "1"
},
```

### 2 - Límite excedido

El cliente ha superado los límites configurados para el comercio (se detallan las cifras en el mensaje).

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "Excede límite %s, quedan disponibles %s para el dia, %s para la semana, %s para el mes. Retiro máximo por transacción %s",
    "errorCode": "2"
},
```

### 3 - Balance excedido para cierta moneda

No hay balance disponible para la moneda seleccionada.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "El saldo a retirar excede el balance disponible en esta moneda",
    "errorCode": "3"
},
```

### 4 - La cuenta no existe

La cuenta bancaria ingresada no existe. 

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "Cuenta ingresada no existe",
    "errorCode": "4"
},
```

## Chile

### 5 - La cuenta no coincide con el RUT

El número de cuenta no coincide con el RUT ingresado (normalmente sucede con pagos hechos por terceros).

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "El número de cuenta del destinatario no corresponde al Rut ingresado.",
    "errorCode": "5"
},
```

#### 5\_1 - La cuenta corriente no coincide con el RUT

El número de **cuenta corriente** no coincide con el RUT ingresado (normalmente sucede con pagos hechos por terceros).

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "El número de cuenta corriente del destinatario no corresponde al rut ingresado.",
    "errorCode": "5_1"
},
```

#### 5\_2 - La cuenta corriente no coincide con el RUT

El número de **cuenta corriente** no coincide con el RUT ingresado (normalmente sucede con pagos hechos por terceros).

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "El número de cuenta corriente del destinatario no corresponde al rut ingresado",
    "errorCode": "5_2"
},
```

#### 5\_3 - Cuenta corriente incorrecta

El número de cuenta corriente del destinatario es incorrecto.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "El número de cuenta corriente de destinatario es incorrecto. Por favor valide la información del beneficiario.",
    "errorCode": "5_3"
},
```

### 6 - Banco no corresponde

El banco que se seleccionó no corresponde con los datos enviados.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "Banco seleccionado no corresponde.",
    "errorCode": "6"
},
```

### 7 - Restricción de abono

La cuenta tiene una restricción de abono (crédito).

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "Cuenta con restricción de abono.",
    "errorCode": "7"
},
```

### 8 - Banco en mantenimiento

El banco al que será enviado el pay out se encuentra en pausa de actividades por mantenimiento.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "Banco de destino en mantención.",
    "errorCode": "8"
},
```

### 9 - RUT incorrecto

El RUT enviado es incorrecto.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "Rut Incorrecto.",
    "errorCode": "9"
},
```

### 10 - RUT con dígito verificador

La cuenta de RUT tiene dígito verificador.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "Cuenta Rut Con Dígito Verificador.",
    "errorCode": "10"
},
```

## Perú

### 11 - InstantPayouts no disponibles

El servicio de pay outs instantáneos no está disponible por el momento, por lo que se debe intentar nuevamente.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "InstanPayouts no disponible, intente nuevamente.",
    "errorCode": "11"
},
```

### 12 - Banco no disponible (en InstantPayouts)

En una solicitud de pay outs instantáneo, el banco de destino no está disponible.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "Banco de destino no disponible.",
    "errorCode": "12"
},
```

### 13 - Error interno (en InstantPayouts)

Ocurrió un error interno inesperado. Por favor reintente nuevamente.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "Error interno, favor reintentar.",
    "errorCode": "13"
},
```

### 20 - Wallet no encontrada

El número de teléfono enviado no está asociado con la wallet que se seleccionó para hacer el pay out. 

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "Wallet no encontrada para este número.",
    "errorCode": "20"
},
```

## Brasil

### 14 - Error de llave PIX

Ocurrió un error de validación. Por favor verifique la llave PIX e intente nuevamente.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "Validation error. Please check the Chave PIX and try again.",
    "errorCode": "14"
},
```

### 15 - Declinación del servidor

La solicitud fue declinada por el servidor.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "Request declined by the server.",
    "errorCode": "15"
},
```

### 19 - CPF no coincide con los datos

El CPF enviado no coincide con los datos de la persona a quien se quiere enviar el pay out. No es posible hacer pay outs a terceros. 

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "Os saques não podem ser feitos com terceiros. O CPF não corresponde ao cadastrado.",
    "errorCode": "19"
},
```

## Ecuador

### 16 - Número telefónico inválido (Payphone)

El número telefónico enviado no es válido para el servicio de Payphone (no está registrado en el servicio).

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "El número de teléfono no es válido en la cabina telefónica.",
    "errorCode": "16"
},
```

### 17 - Error interno por validaciones

Ocurrió un error interno debido a una falla durante el proceso de validación.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "Error interno, validaciones fallidas.",
    "errorCode": "17"
},
```

### 18 - Problema con detalles de la cuenta bancaria

Ocurrió un problema con algunos detalles de la cuenta bancaria. Por favor, intente nuevamente. 

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "Problem with bank account details, please try again.",
    "errorCode": "18"
},
```
