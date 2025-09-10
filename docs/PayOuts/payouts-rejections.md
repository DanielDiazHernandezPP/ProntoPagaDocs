---
title: Tipos de rechazos (PayOuts)
excerpt: ''
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

<br />

## Generales (todos los países)

A continuación se muestran varios posibles casos de rechazo, junto con su descripción.

| Código de error | Mensaje de rechazo                                                                                                                  | Descripción                                                                                                                                                 |
| :-------------- | :---------------------------------------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1               | El cliente se encuentra bloqueado                                                                                                   | El cliente se bloquea en la lista negra.                                                                                                                    |
| 2               | Excede límite %s, quedan disponibles %s para el día, %s para la semana, %s para el mes. Retiro máximo por transacción %s            | El cliente ha superado los límites configurados para el comercio, detallándose las cifras en el mensaje.                                                    |
| 3               | El saldo a retirar excede el balance disponible en esta moneda                                                                      | No hay balance disponible para la moneda seleccionada.                                                                                                      |
| 4               | Cuenta ingresada no existe                                                                                                          | La cuenta bancaria ingresada no existe.                                                                                                                     |
| 21              | Moneda ingresada es inválida                                                                                                        | El código de moneda que se ha enviado no es correcto.                                                                                                       |
| 22              | Cuenta invalida, bloqueada o cerrada                                                                                                | La cuenta no es válida. Posiblemente ha sido bloqueada o cerrada con anterioridad.                                                                          |
| 23              | La información suministrada es insuficiente o inválida                                                                              | La información enviada no pudo ser verificada, es inválida. O bien, hay campos esenciales que no se enviaron.                                               |
| 34              | El número de cuenta del destinatario no corresponde a los datos del usuario ingresado                                               | Se realizó una validación y el número de cuenta ingresado para hacer el PayOut, no corresponde a los datos del usuario. Es un retiro a terceros, no válido. |
| 25              | ID inválido                                                                                                                         | El número de ID ingresado es inválido.                                                                                                                      |
| 26              | Transaction amount limit exceeds                                                                                                    | La cantidad total de la transacción excede los límites permitidos.                                                                                          |
| 27              | No se aceptan documentos de identidad correspondientes a empresas. Por favor, ingresa uno válido de persona natural para continuar. | El documento de identidad ingresado está asociado a una empresa, y los Payouts solo pueden realizarse a personas naturales.                                 |

***

<br />

## Brasil 🇧🇷

Estos son los tipos de retiros rechazados en Brasil.

| Código de error | Mensaje de rechazo                                                                | Descripción                                                                                                                        |
| :-------------- | :-------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------- |
| 14              | Validation error. Please check the Chave PIX and try again                        | Ocurrió un error de validación. Por favor verifique la llave PIX e intente nuevamente.                                             |
| 15              | Request declined by the server                                                    | La solicitud fue declinada por el servidor.                                                                                        |
| 19              | Os saques não podem ser feitos com terceiros. O CPF não corresponde ao cadastrado | El CPF enviado no coincide con los datos de la persona a quien se quiere enviar el PayOut. No es posible hacer PayOuts a terceros. |

***

<br />

## Chile 🇨🇱

Estos son los tipos de retiros rechazados en Chile.

| Código de error | Mensaje de rechazo                                                   | Descripción                                                                                              |
| :-------------- | :------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------- |
| 5               | El número de cuenta del destinatario no corresponde al Rut ingresado | El número de cuenta no coincide con el RUT ingresado (normalmente sucede con pagos hechos por terceros). |
| 6               | Banco seleccionado no corresponde                                    | El banco que se seleccionó no corresponde con los datos enviados.                                        |
| 7               | Cuenta con restricción de abono                                      | La cuenta tiene una restricción de abono (crédito).                                                      |
| 8               | Banco de destino en mantención                                       | El banco al que será enviado el PayOut se encuentra en pausa de actividades por mantenimiento.           |
| 9               | Rut Incorrecto                                                       | El RUT enviado es incorrecto.                                                                            |
| 10              | Cuenta Rut Con Dígito Verificador                                    | La cuenta de RUT tiene dígito verificador.                                                               |

***

<br />

## Ecuador 🇪🇨

Estos son los tipos de retiros rechazados en Ecuador.

| Código de error    | Mensaje de rechazo                                                                                                                                                                                                                                 | Descripción                                                                                                 |
| :----------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------------------- |
| Cliente Bloqueado  | The client is blocked                                                                                                                                                                                                                              | El cliente está bloqueado en la lista negra.                                                                |
| Limite de comercio | Exceeds daily limit, 5,000,000.00 CLP available for the day,                 10,000,000.00 CLP available for the week,                 30,000,000.00 CLP available for the month.                 Maximum deposit per transaction 6,000,000.00 CLP | La cantidad límite del comercio, ya sea por día, semana o mes, fue excedida.                                |
| Pago pendiente     | There is already a pending payment for that phone number.                                                                                                                                                                                          | El número de teléfono ya cuenta con un pago pendiente.                                                      |
| Pago fallido       | Failed payment: There is already a pending payment transaction.                                                                                                                                                                                    | El pago falló y se generó una transacción pendiente.                                                        |
| 16                 | El número de teléfono no es válido en la cabina telefónica.                                                                                                                                                                                        | El número telefónico enviado no es válido para el servicio de Payphone (no está registrado en el servicio). |
| 17                 | Error interno, validaciones fallidas                                                                                                                                                                                                               | Ocurrió un error interno debido a una falla durante el proceso de validación.                               |
| 18                 | Problem with bank account details, please try again                                                                                                                                                                                                | Ocurrió un problema con algunos detalles de la cuenta bancaria. Por favor, intente nuevamente.              |
| 100                | Error de autenticación                                                                                                                                                                                                                             | Hay un error de autenticación. Por favor, intente nuevamente.                                               |
| 101                | Error de autenticación                                                                                                                                                                                                                             | Hay un error de autenticación. Por favor, intente nuevamente.                                               |
| 104                | Error de autenticación                                                                                                                                                                                                                             | Hay un error de autenticación. Por favor, intente nuevamente.                                               |
| 110                | Datos incompletos                                                                                                                                                                                                                                  | Los datos ingresados no están completos. Por favor, ingréselos e intente nuevamente.                        |
| 120                | Referencia no encontrada                                                                                                                                                                                                                           | La referencia solicitada no fue encontrada.                                                                 |
| 121                | Referencia no asociada a esta pasarela                                                                                                                                                                                                             | La referencia solicitada no está asociada a esta pasarela de retiros.                                       |
| 122                | Pago expirado                                                                                                                                                                                                                                      | El pago ha caducado.                                                                                        |
| 123                | Pago pendiente                                                                                                                                                                                                                                     | El pago se encuentra en estado pendiente.                                                                   |
| 200                | Pago Completado                                                                                                                                                                                                                                    | El pago fue completado exitosamente.                                                                        |
| 300                | No se puede resolver                                                                                                                                                                                                                               | Ocurrió un error inesperado. Por favor, intente nuevamente.                                                 |

***

<br />

## Perú 🇵🇪

Estos son los tipos de retiros rechazados en Perú.

| Código de error | Mensaje de rechazo                            | Descripción                                                                                                    |
| :-------------- | :-------------------------------------------- | :------------------------------------------------------------------------------------------------------------- |
| 7               | Internal error, failed validations            | Ocurrió un error interno y las validaciones fallaron. Por favor, reintente nuevamente.                         |
| 11              | InstanPayouts not available, please try again | El servicio de PayOuts instantáneos no está disponible por el momento, por lo que se debe intentar nuevamente. |
| 12              | Destination bank not available                | En una solicitud de PayOuts instantáneo, el banco de destino no está disponible.                               |
| 13              | Internal error, please try again              | Ocurrió un error interno inesperado. Por favor reintente nuevamente.                                           |
| 20              | Wallet not found for this phone number        | El número de teléfono enviado no está asociado con la wallet que se seleccionó para hacer el PayOut.           |

<br />
