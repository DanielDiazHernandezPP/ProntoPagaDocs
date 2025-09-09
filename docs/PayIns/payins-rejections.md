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

## General (todos los países)

A continuación se muestran varios posibles casos de rechazo, junto con su descripción.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Mensaje de rechazo
      </th>

      <th>
        Descripción
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        The client is blocked
      </td>

      <td>
        El cliente se bloquea en lista negra.
      </td>
    </tr>

    <tr>
      <td>
        Exceeds daily limit,
        5,000,000.00 BRL available for the day,
        10,000,000.00 BRL available for the week,
        30,000,000.00 BRL available for the month.

        Maximum deposit per transaction 6,000,000.00 BRL
      </td>

      <td>
        El cliente ha superado los límites establecidos para la transacción o comercio.
      </td>
    </tr>

    <tr>
      <td>
        High fraudulent score - DM
      </td>

      <td>
        La transacción tiene un alto nivel de riesgo de fraude.
      </td>
    </tr>
  </tbody>
</Table>

***

## Argentina 🇦🇷

### Tarjeta

A continuación se muestran varios posibles casos de rechazo, junto con su descripción.

| Mensaje de rechazo     | Descripción                                                                                                                |
| :--------------------- | :------------------------------------------------------------------------------------------------------------------------- |
| INSUFFICIENT_FUNDS     | Saldo insuficiente para realizar la transacción.                                                                           |
| RECHAZADO POR EL BANCO | Tu banco rechazó la transacción. Contáctate con ellos para más información.                                                |
| DO_NOT_HONOR           | Tu banco rechazó la transacción. Intenta con otra tarjeta o contacta a tu banco.                                           |
| INVALID_SECURITY_CODE  | El código CVV ingresado no es correcto. Verifica e inténtalo nuevamente.                                                   |
| INVALID_CARD_DATA      | Los datos de la tarjeta ingresados son incorrectos. Revisa los datos e inténtalo de nuevo.                                 |
| REPORTED_STOLEN        | No se puede realizar la transacciones. La tarjeta ha sido reportada como robada. Contacta a tu banco para más información. |
| ERROR                  | Se ha producido un error en la transacción. Inténtalo nuevamente o usa otro método de pago.                                |

***

## Brasil 🇧🇷

Estos son los tipos de pagos rechazados en Brasil, junto con su descripción.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Mensaje de rechazo
      </th>

      <th>
        Descripción
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Exceeds daily limit,

        5,000,000.00 BRL available for the day,
        10,000,000.00 BRL available for the week,
        30,000,000.00 BRL available for the month.
        Maximum deposit per transaction 6,000,000.00 BRL
      </td>

      <td>
        El cliente ha superado los límites establecidos para la transacción o comercio.
      </td>
    </tr>

    <tr>
      <td>
        Error while creating the payment in the Pix service. Please try again
      </td>

      <td>
        Error al crear el pago en el servicio Pix.
      </td>
    </tr>

    <tr>
      <td>
        Error generating Pix QR Code
      </td>

      <td>
        Error al generar el código QR Pix.
      </td>
    </tr>

    <tr>
      <td>
        Error generating Pix AccessToken
      </td>

      <td>
        Error al generar el Token de Acceso Pix.
      </td>
    </tr>
  </tbody>
</Table>

***

## Chile 🇨🇱

Estos son los tipos de pagos rechazados en Chile.

### Paga Con Tu Banco

A continuación se muestran varios posibles casos de rechazo, junto con su descripción.

| Mensaje de rechazo                     | Descripción                         |
| :------------------------------------- | :---------------------------------- |
| Bank not recognized                    | Banco no reconocido en la metadata. |
| No destination account for BancoEstado | BancoEstado sin cuenta configurada. |
| Failed to assign destination account   | Error al asignar cuenta destino.    |
| Unexpected internal error              | Error inesperado.                   |

### Tarjeta

A continuación se muestran varios posibles casos de rechazo, junto con su descripción.

| Mensaje de rechazo                                                                                                                                        | Descripción                                                                                            |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------- |
| Excede monto máximo                                                                                                                                       | La transacción excede el monto máximo establecido.                                                     |
| Problema en la transacción                                                                                                                                | Se ha producido un error en la transacción. Inténtalo nuevamente o usa otro método de pago.            |
| Rechazo general                                                                                                                                           | Se ha producido un rechazo general de la transacción. Inténtalo nuevamente o usa otro método de pago.  |
| Rechazo - Posible error en el ingreso de datos de la transacción                                                                                          | Se ha producido un error en el ingresos de los datos. Inténtalo nuevamente o usa otro método de pago.  |
| Rechazo - Se produjo fallo al procesar la transacción, este mensaje de rechazo se encuentra relacionado a parámetros de la tarjeta y/o su cuenta asociada | Se ha producido un fallo al procesar la transacción. Inténtalo nuevamente o usa otro método de pago.   |
| Rechazo - Error en Transacción                                                                                                                            | Se ha producido un error en la transacción. Inténtalo nuevamente o usa otro método de pago.            |
| Rechazo - Rechazada por parte del emisor                                                                                                                  | La transacción ha sido rechazada por parte del emisor. Inténtalo nuevamente o usa otro método de pago. |
| Rechazo - Transacción con riesgo de posible fraude                                                                                                        | La transacción tiene un alto nivel de riesgo de fraude.                                                |

***

## Ecuador 🇪🇨

Estos son los tipos de pagos rechazados en Ecuador.

### Efectivo

A continuación se muestran varios posibles casos de rechazo, junto con su descripción.

| Mensaje de rechazo                            | Descripción                                                  |
| :-------------------------------------------- | :----------------------------------------------------------- |
| Excede límite Depósito Máximo por Transacción | Se ha excedido el límite de depósito máximo por transacción. |

### Tarjeta / Wallet

A continuación se muestran varios posibles casos de rechazo, junto con su descripción.

| Mensaje de rechazo                                                                                  | Descripción                                                                                                                        |
| :-------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------- |
| There is already a pending payment for that phone number.                                           | El cliente tiene una transacción de pago pendiente para ese mismo número de teléfono.                                              |
| Failed payment: There is already a pending payment transaction.                                     | El cliente tiene una transacción de pago pendiente.                                                                                |
| The identity document does not match the one registered in PayPhone.                                | El documento ingresado no coincide con el documento registrado en Payphone.                                                        |
| La aplicación no existe, verifique que el token enviado sea el entregado para su aplicación.        | El token enviado no es el correcto. Verifica que el token enviado sea el correcto. Inténtalo nuevamente o usa otro método de pago. |
| La aplicación no tiene relación con la compañía especificada.                                       | Revisa la relación entre tu app y la compañía configurada. Inténtalo nuevamente o usa otro método de pago.                         |
| Su dominio no está autorizado por la aplicación. Ingrese a la consola de developer para configurar. | Ingresa a la consola de developer y añade tu dominio.                                                                              |
| La transacción no existe, verifique que el identificador enviado sea correcto.                      | Verifica que el identificador enviado sea correcto. Inténtalo nuevamente o usa otro método de pago.                                |
| La transacción no pudo ser creada, por favor inténtelo de nuevo.                                    | Intenta nuevamente más tarde; si persiste, contacta al soporte.                                                                    |

***

## Perú 🇵🇪

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
