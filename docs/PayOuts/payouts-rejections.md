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

> 👍 Números de error
>
> Los tipos de rechazos están ordenados por país, y el número que se indica al inicio de cada error, es el que se recibe como `errorCode`. Para encontrar el error que buscas, puedes guiarte con la Tabla de Contenidos que aparece a la derecha del artículo.

***

<br />

## Generales (todos los países)

A continuación se muestran varios posibles casos de rechazo, junto con su descripción.

| Mensaje de rechazo                                                                                                       | Descripción                                                                                                                                                 |
| :----------------------------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| El cliente se encuentra bloqueado                                                                                        | El cliente se bloquea en la lista negra.                                                                                                                    |
| Excede límite %s, quedan disponibles %s para el día, %s para la semana, %s para el mes. Retiro máximo por transacción %s | El cliente ha superado los límites configurados para el comercio, detallándose las cifras en el mensaje.                                                    |
| El saldo a retirar excede el balance disponible en esta moneda                                                           | No hay balance disponible para la moneda seleccionada.                                                                                                      |
| Cuenta ingresada no existe                                                                                               | La cuenta bancaria ingresada no existe.                                                                                                                     |
| Moneda ingresada es inválida                                                                                             | El código de moneda que se ha enviado no es correcto.                                                                                                       |
| Cuenta invalida, bloqueada o cerrada                                                                                     | La cuenta no es válida. Posiblemente ha sido bloqueada o cerrada con anterioridad.                                                                          |
| La información suministrada es insuficiente o inválida                                                                   | La información enviada no pudo ser verificada, es inválida. O bien, hay campos esenciales que no se enviaron.                                               |
| El número de cuenta del destinatario no corresponde a los datos del usuario ingresado                                    | Se realizó una validación y el número de cuenta ingresado para hacer el PayOut, no corresponde a los datos del usuario. Es un retiro a terceros, no válido. |
| ID inválido                                                                                                              | El número de ID ingresado es inválido.                                                                                                                      |

***

<br />

## Brasil 🇧🇷

Estos son los tipos de retiros rechazados en Brasil.

| Mensaje de rechazo                                                                | Descripción                                                                                                                        |
| :-------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------- |
| Validation error. Please check the Chave PIX and try again                        | Ocurrió un error de validación. Por favor verifique la llave PIX e intente nuevamente.                                             |
| Request declined by the server                                                    | La solicitud fue declinada por el servidor.                                                                                        |
| Os saques não podem ser feitos com terceiros. O CPF não corresponde ao cadastrado | El CPF enviado no coincide con los datos de la persona a quien se quiere enviar el PayOut. No es posible hacer PayOuts a terceros. |

***

<br />

## Chile 🇨🇱

Estos son los tipos de retiros rechazados en Chile.

| Mensaje de rechazo                                                   | Descripción                                                                                              |
| :------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------- |
| El número de cuenta del destinatario no corresponde al Rut ingresado | El número de cuenta no coincide con el RUT ingresado (normalmente sucede con pagos hechos por terceros). |
| Banco seleccionado no corresponde                                    | El banco que se seleccionó no corresponde con los datos enviados.                                        |
| Cuenta con restricción de abono                                      | La cuenta tiene una restricción de abono (crédito).                                                      |
| Banco de destino en mantención                                       | El banco al que será enviado el PayOut se encuentra en pausa de actividades por mantenimiento.           |
| Rut Incorrecto                                                       | El RUT enviado es incorrecto.                                                                            |
| Cuenta Rut Con Dígito Verificador                                    | La cuenta de RUT tiene dígito verificador.                                                               |

***

<br />

## Ecuador 🇪🇨

Estos son los tipos de retiros rechazados en Ecuador.

| Mensaje de rechazo                                          | Descripción                                                                                                 |
| :---------------------------------------------------------- | :---------------------------------------------------------------------------------------------------------- |
| El número de teléfono no es válido en la cabina telefónica. | El número telefónico enviado no es válido para el servicio de Payphone (no está registrado en el servicio). |
| Error interno, validaciones fallidas                        | Ocurrió un error interno debido a una falla durante el proceso de validación.                               |
| Problem with bank account details, please try again         | Ocurrió un problema con algunos detalles de la cuenta bancaria. Por favor, intente nuevamente.              |

***

<br />

## Perú 🇵🇪

Estos son los tipos de retiros rechazados en Perú.

| Mensaje de rechazo                              | Descripción                                                                                                    |
| :---------------------------------------------- | :------------------------------------------------------------------------------------------------------------- |
| InstanPayouts no disponible, intente nuevamente | El servicio de PayOuts instantáneos no está disponible por el momento, por lo que se debe intentar nuevamente. |
| Banco de destino no disponible                  | En una solicitud de PayOuts instantáneo, el banco de destino no está disponible.                               |
| Error interno, favor reintentar                 | Ocurrió un error interno inesperado. Por favor reintente nuevamente.                                           |
| Wallet no encontrada para este número           | El número de teléfono enviado no está asociado con la wallet que se seleccionó para hacer el PayOut.           |
