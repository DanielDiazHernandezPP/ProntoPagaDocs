---
title: Tipos de rechazos (PayOuts)
excerpt: Explora los distintos tipos de rechazos para los PayOuts, divididos por país.
deprecated: false
hidden: false
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
next:
  description: ''
---
A continuación se describen todos los posibles tipos de rechazos para PayOuts. El número corresponde al número que se devuelve en el campo `errorCode` del rechazo.

***

## Generales (todos los países) 🌎

A continuación se muestran varios posibles casos de rechazo, junto con su descripción.

| Código de error | Mensaje de rechazo                                                                                                                 |
| :-------------- | :--------------------------------------------------------------------------------------------------------------------------------- |
| 1               | El cliente se encuentra bloqueado                                                                                                  |
| 2               | Excede límite %s, quedan disponibles %s para el día, %s para la semana, %s para el mes. Retiro máximo por transacción %s           |
| 3               | El saldo a retirar excede el balance disponible en esta moneda                                                                     |
| 4               | Cuenta ingresada no existe                                                                                                         |
| 21              | Moneda ingresada es inválida                                                                                                       |
| 22              | Cuenta invalida, bloqueada o cerrada                                                                                               |
| 23              | La información suministrada es insuficiente o inválida                                                                             |
| 24              | El número de cuenta del destinatario no corresponde a los datos del usuario ingresado                                              |
| 25              | ID inválido                                                                                                                        |
| 26              | Transaction amount limit exceeds                                                                                                   |
| 27              | No se aceptan documentos de identidad correspondientes a empresas. Por favor, ingresa uno válido de persona natural para continuar |

***

## Chile 🇨🇱

Estos son los tipos de retiros rechazados en Chile.

| Código de error | Mensaje de rechazo                                                   |
| :-------------- | :------------------------------------------------------------------- |
| 5               | El número de cuenta del destinatario no corresponde al Rut ingresado |
| 6               | Banco seleccionado no corresponde                                    |
| 7               | Cuenta con restricción de abono                                      |
| 8               | Banco de destino en mantención                                       |
| 9               | Rut Incorrecto                                                       |
| 10              | Cuenta Rut Con Dígito Verificador                                    |

***

## Ecuador 🇪🇨

Estos son los tipos de retiros rechazados en Ecuador.

| Código de error    | Mensaje de rechazo                                                                                                                                                                                 | Descripción                                                                                                 |
| :----------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------------------- |
| Limite de comercio | Exceeds daily limit, 5,000,000.00 CLP available for the day, 10,000,000.00 CLP available for the week, 30,000,000.00 CLP available for the month. Maximum deposit per transaction 6,000,000.00 CLP | La cantidad límite del comercio, ya sea por día, semana o mes, fue excedida.                                |
| Pago pendiente     | There is already a pending payment for that phone number                                                                                                                                           | El número de teléfono ya cuenta con un pago pendiente.                                                      |
| Pago fallido       | Failed payment: There is already a pending payment transaction                                                                                                                                     | El pago falló y se generó una transacción pendiente.                                                        |
| 16                 | El número de teléfono no es válido en la cabina telefónica                                                                                                                                         | El número telefónico enviado no es válido para el servicio de Payphone (no está registrado en el servicio). |
| 17                 | Error interno, validaciones fallidas                                                                                                                                                               | Ocurrió un error interno debido a una falla durante el proceso de validación.                               |
| 18                 | Problem with bank account details, please try again                                                                                                                                                | Ocurrió un problema con algunos detalles de la cuenta bancaria. Por favor, intente nuevamente.              |
| 100                | Error de autenticación                                                                                                                                                                             | Hay un error de autenticación. Por favor, intente nuevamente.                                               |
| 101                | Error de autenticación                                                                                                                                                                             | Hay un error de autenticación. Por favor, intente nuevamente.                                               |
| 104                | Error de autenticación                                                                                                                                                                             | Hay un error de autenticación. Por favor, intente nuevamente.                                               |
| 110                | Datos incompletos                                                                                                                                                                                  | Los datos ingresados no están completos. Por favor, ingréselos e intente nuevamente.                        |
| 120                | Referencia no encontrada                                                                                                                                                                           | La referencia solicitada no fue encontrada.                                                                 |
| 121                | Referencia no asociada a esta pasarela                                                                                                                                                             | La referencia solicitada no está asociada a esta pasarela de retiros.                                       |
| 122                | Pago expirado                                                                                                                                                                                      | El pago ha caducado.                                                                                        |
| 123                | Pago pendiente                                                                                                                                                                                     | El pago se encuentra en estado pendiente.                                                                   |
| 200                | Pago Completado                                                                                                                                                                                    | El pago fue completado exitosamente.                                                                        |
| 300                | No se puede resolver                                                                                                                                                                               | Ocurrió un error inesperado. Por favor, intente nuevamente                                                  |

***

## Perú 🇵🇪

Estos son los tipos de retiros rechazados en Perú.

| Código de error | Mensaje de rechazo                                                 | Descripción                                                                                                    |
| :-------------- | :----------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------- |
| 7               | Internal error, failed validations                                 | Ocurrió un error interno y las validaciones fallaron. Por favor, reintente nuevamente.                         |
| 11              | InstanPayouts not available, please try again                      | El servicio de PayOuts instantáneos no está disponible por el momento, por lo que se debe intentar nuevamente. |
| 12              | Destination bank not available                                     | En una solicitud de PayOuts instantáneo, el banco de destino no está disponible.                               |
| 13              | Internal error, please try again                                   | Ocurrió un error interno inesperado. Por favor reintente nuevamente.                                           |
| 20              | Wallet not found for this phone number                             | El número de teléfono enviado no está asociado con la wallet que se seleccionó para hacer el PayOut.           |
| 26              | Withdrawal amount exceeds limits, please retry with a valid amount | Monto de retiro excede los limites, por favor reintentar con un monto valido.                                  |
| 26              | Exceeds the maximum transaction amount per month                   | Monto de retiro excede los limites, por favor reintentar con un monto valido.                                  |

<br />
