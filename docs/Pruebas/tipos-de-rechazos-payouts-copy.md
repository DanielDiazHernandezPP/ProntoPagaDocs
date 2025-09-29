---
title: Tipos de rechazos (PayOuts) (COPY)
deprecated: false
hidden: true
metadata:
  title: Tipos de rechazos (PayOuts) | ProntoPaga Docs
  description: >-
    The document describes common types of payout rejections in Brazil, Chile,
    Ecuador, and Peru, including customer blocks, transaction limits, and
    payment system-specific errors. 
  image: >-
    https://files.readme.io/1d8dd9ae76841fe399a75c800b1196bd9b0f17a4e83ebdd496b4d640d7f97c74-Prontopaga_logotipo.png
  keywords:
    - rejections Prontopaga
    - payouts rejections
    - types of rejections prontopaga
    - rechazos prontopaga
    - pago rechazado prontopaga
    - pago denegado
    - payout cancelled
    - rejected
  robots: index
---
A continuación se describen todos los posibles tipos de rechazos para PayOuts. El número corresponde al número que se devuelve en el campo `errorCode` del rechazo.

> 👍 Números de error
>
> Los tipos de rechazos están ordenados por país, y el número que se indica al inicio de cada error, es el que se recibe como `errorCode`. Para encontrar el error que buscas, puedes guiarte con la Tabla de Contenidos que aparece a la derecha del artículo.

***

<br />

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

<br />

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

<br />

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

<br />

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

<br />

### 21 - Moneda inválida

El código de moneda que se ha enviado no es correcto.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "Moneda ingresada es inválida",
    "errorCode": "21"
},
```

<br />

### 22 - Cuenta inválida

La cuenta no es válida. Posiblemente ha sido bloqueada o cerrada con anterioridad.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "Cuenta  invalida, bloqueada o cerrada",
    "errorCode": "22"
},
```

<br />

### 23 - Información inválida

La información enviada no pudo ser verificada, es inválida. O bien, hay campos esenciales que no se enviaron.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "La información suministrada es insuficiente o inválida",
    "errorCode": "23"
},
```

<br />

### 24 - Numero de cuenta inválido

Se realizó una validación y el número de cuenta ingresado para hacer el PayOut, no corresponde a los datos del usuario. Es un retiro a terceros, no válido.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "El número de cuenta del destinatario no corresponde a los datos del usuario ingresado",
    "errorCode": "24"
},
```

<br />

### 25 - ID inválido

El número de ID ingresado es inválido.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "ID inválido",
    "errorCode": "25"
},
```

***

<br />

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

<br />

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

<br />

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

<br />

### 8 - Banco en mantenimiento

El banco al que será enviado el PayOut se encuentra en pausa de actividades por mantenimiento.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "Banco de destino en mantención.",
    "errorCode": "8"
},
```

<br />

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

<br />

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

***

<br />

## Perú

### 11 - InstantPayouts no disponibles

El servicio de PayOuts instantáneos no está disponible por el momento, por lo que se debe intentar nuevamente.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "InstanPayouts no disponible, intente nuevamente.",
    "errorCode": "11"
},
```

<br />

### 12 - Banco no disponible (en InstantPayouts)

En una solicitud de PayOuts instantáneo, el banco de destino no está disponible.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "Banco de destino no disponible.",
    "errorCode": "12"
},
```

<br />

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

<br />

### 20 - Wallet no encontrada

El número de teléfono enviado no está asociado con la wallet que se seleccionó para hacer el PayOut.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "Wallet no encontrada para este número.",
    "errorCode": "20"
},
```

***

<br />

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

<br />

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

<br />

### 19 - CPF no coincide con los datos

El CPF enviado no coincide con los datos de la persona a quien se quiere enviar el PayOut. No es posible hacer PayOuts a terceros.

```json
{
    "uid": "01GMB3VVRB3QWYDKW6Z92W2T3B",
    "status": "canceled",
    "message": "Os saques não podem ser feitos com terceiros. O CPF não corresponde ao cadastrado.",
    "errorCode": "19"
},
```

***

<br />

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

<br />

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

<br />

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