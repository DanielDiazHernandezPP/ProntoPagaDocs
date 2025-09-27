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

## Generales (todos los países) 🌎

A continuación se muestran varios posibles casos de rechazo, junto con su descripción.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Mensaje de rechazo</b></th>
      <th><b>Descripción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>The client is blocked</td><td>El cliente se bloquea en lista negra.</td></tr>
    <tr><td>Exceeds daily limit</td><td>	El cliente ha superado los límites establecidos para la transacción o comercio.</td></tr>
    <tr><td>High fraudulent score - DM</td><td>La transacción tiene un alto nivel de riesgo de fraude.</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

| Mensaje de rechazo         | Descripción                                                                     |
| :------------------------- | :------------------------------------------------------------------------------ |
| The client is blocked      | El cliente se bloquea en lista negra.                                           |
| Exceeds daily limit        | El cliente ha superado los límites establecidos para la transacción o comercio. |
| High fraudulent score - DM | La transacción tiene un alto nivel de riesgo de fraude.                         |

***

## Argentina 🇦🇷

### Tarjeta

A continuación se muestran varios posibles casos de rechazo, junto con su descripción.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Mensaje de rechazo</b></th>
      <th><b>Descripción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>INSUFFICIENT_FUNDS</td><td>Saldo insuficiente para realizar la transacción.</td></tr>
    <tr><td>RECHAZADO POR EL BANCO</td><td>Tu banco rechazó la transacción. Contáctate con ellos para más información.</td></tr>
    <tr><td>DO_NOT_HONOR</td><td>Tu banco rechazó la transacción. Intenta con otra tarjeta o contacta a tu banco.</td></tr>
<tr><td>INVALID_SECURITY_CODE</td><td>El código CVV ingresado no es correcto. Verifica e inténtalo nuevamente.</td></tr>
    <tr><td>INVALID_CARD_DATA</td><td>Los datos de la tarjeta ingresados son incorrectos. Revisa los datos e inténtalo de nuevo.</td></tr>
    <tr><td>REPORTED_STOLEN</td><td>No se puede realizar la transacciones. La tarjeta ha sido reportada como robada. Contacta a tu banco para más información.</td></tr>
    <tr><td>ERROR</td><td>Se ha producido un error en la transacción. Inténtalo nuevamente o usa otro método de pago.</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

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

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Mensaje de rechazo</b></th>
      <th><b>Descripción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Error while creating the payment in the Pix service. Please try again</td><td>Error al crear el pago en el servicio Pix.</td></tr>
    <tr><td>Error generating Pix QR Code</td><td>Error al generar el código QR Pix.</td></tr>
    <tr><td>Error generating Pix AccessToken</td><td>Error al generar el Token de Acceso Pix.</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

| Mensaje de rechazo                                                    | Descripción                                |
| :-------------------------------------------------------------------- | :----------------------------------------- |
| Error while creating the payment in the Pix service. Please try again | Error al crear el pago en el servicio Pix. |
| Error generating Pix QR Code                                          | Error al generar el código QR Pix.         |
| Error generating Pix AccessToken                                      | Error al generar el Token de Acceso Pix.   |

***

## Chile 🇨🇱

Estos son los tipos de pagos rechazados en Chile.

### Paga con Tu Banco

A continuación se muestran varios posibles casos de rechazo, junto con su descripción.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Mensaje de rechazo</b></th>
      <th><b>Descripción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Bank not recognized</td><td>Banco no reconocido en la metadata.</td></tr>
    <tr><td>No destination account for BancoEstado</td><td>BancoEstado sin cuenta configurada.</td></tr>
    <tr><td>Failed to assign destination account</td><td>Error al asignar cuenta destino.</td></tr>
    <tr><td>Unexpected internal error</td><td>Error inesperado.</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

| Mensaje de rechazo                     | Descripción                         |
| :------------------------------------- | :---------------------------------- |
| Bank not recognized                    | Banco no reconocido en la metadata. |
| No destination account for BancoEstado | BancoEstado sin cuenta configurada. |
| Failed to assign destination account   | Error al asignar cuenta destino.    |
| Unexpected internal error              | Error inesperado.                   |

### Tarjeta

A continuación se muestran varios posibles casos de rechazo, junto con su descripción.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Mensaje de rechazo</b></th>
      <th><b>Descripción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Excede monto máximo</td><td>La transacción excede el monto máximo establecido.</td></tr>
    <tr><td>Problema en la transacción</td><td>Se ha producido un error en la transacción. Inténtalo nuevamente o usa otro método de pago.</td></tr>
    <tr><td>Rechazo general</td><td>Se ha producido un rechazo general de la transacción. Inténtalo nuevamente o usa otro método de pago.</td></tr>
    <tr><td>Rechazo - Posible error en el ingreso de datos de la transacción</td><td>Se ha producido un error en el ingresos de los datos. Inténtalo nuevamente o usa otro método de pago.</td></tr>
    <tr><td>Rechazo - Se produjo fallo al procesar la transacción, este mensaje de rechazo se encuentra relacionado a parámetros de la tarjeta y/o su cuenta asociada</td><td>Se ha producido un fallo al procesar la transacción. Inténtalo nuevamente o usa otro método de pago.</td></tr>
    <tr><td>Rechazo - Error en Transacción</td><td>Se ha producido un error en la transacción. Inténtalo nuevamente o usa otro método de pago.</td></tr>
    <tr><td>Rechazo - Rechazada por parte del emisor</td><td>La transacción ha sido rechazada por parte del emisor. Inténtalo nuevamente o usa otro método de pago.</td></tr>
    <tr><td>Rechazo - Transacción con riesgo de posible fraude</td><td>La transacción tiene un alto nivel de riesgo de fraude.</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

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

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Mensaje de rechazo</b></th>
      <th><b>Descripción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Excede límite Depósito Máximo por Transacción</td><td>BSe ha excedido el límite de depósito máximo por transacción.</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

| Mensaje de rechazo                            | Descripción                                                  |
| :-------------------------------------------- | :----------------------------------------------------------- |
| Excede límite Depósito Máximo por Transacción | Se ha excedido el límite de depósito máximo por transacción. |

### Tarjeta / Wallet

A continuación se muestran varios posibles casos de rechazo, junto con su descripción.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Mensaje de rechazo</b></th>
      <th><b>Descripción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>There is already a pending payment for that phone number.</td><td>El cliente tiene una transacción de pago pendiente para ese mismo número de teléfono.</td></tr>
    <tr><td>Failed payment: There is already a pending payment transaction.</td><td>El cliente tiene una transacción de pago pendiente.</td></tr>
    <tr><td>The identity document does not match the one registered in PayPhone.</td><td>El documento ingresado no coincide con el documento registrado en Payphone.</td></tr>
    <tr><td>La aplicación no existe, verifique que el token enviado sea el entregado para su aplicación.</td><td>El token enviado no es el correcto. Verifica que el token enviado sea el correcto. Inténtalo nuevamente o usa otro método de pago.</td></tr>
    <tr><td>La aplicación no tiene relación con la compañía especificada.</td><td>Revisa la relación entre tu app y la compañía configurada. Inténtalo nuevamente o usa otro método de pago.</td></tr>
    <tr><td>Su dominio no está autorizado por la aplicación. Ingrese a la consola de developer para configurar.</td><td>Ingresa a la consola de developer y añade tu dominio.</td></tr>
    <tr><td>La transacción no existe, verifique que el identificador enviado sea correcto.</td><td>Verifica que el identificador enviado sea correcto. Inténtalo nuevamente o usa otro método de pago.</td></tr>
    <tr><td>La transacción no pudo ser creada, por favor inténtelo de nuevo.</td><td>Intenta nuevamente más tarde; si persiste, contacta al soporte.</td></tr>
    <tr><td>Ya existe una transacción con el <code>ClientTransactionId</code> especificado.</td><td>Cambia el identificador; cada transacción debe tener un ID único.</td></tr>
    <tr><td>La transacción ya se encuentra cancelada.</td><td>Verifica el estado de la transacción antes de intentar cancelarla.</td></tr>
    <tr><td>La transacción no se pudo cancelar. Puede que ya se encuentre aprobada o cancelada.</td><td>Asegúrate de que no esté ya aprobada o cancelada.</td></tr>
    <tr><td>Solo se permiten 0 transacciones por día para la misma tarjeta. Por favor póngase en contacto con la persona encargada de la tienda.</td><td>Contacta al administrador de la tienda para revisar restricciones.</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

| Mensaje de rechazo                                                                                                                     | Descripción                                                                                                                        |
| :------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------- |
| There is already a pending payment for that phone number.                                                                              | El cliente tiene una transacción de pago pendiente para ese mismo número de teléfono.                                              |
| Failed payment: There is already a pending payment transaction.                                                                        | El cliente tiene una transacción de pago pendiente.                                                                                |
| The identity document does not match the one registered in PayPhone.                                                                   | El documento ingresado no coincide con el documento registrado en Payphone.                                                        |
| La aplicación no existe, verifique que el token enviado sea el entregado para su aplicación.                                           | El token enviado no es el correcto. Verifica que el token enviado sea el correcto. Inténtalo nuevamente o usa otro método de pago. |
| La aplicación no tiene relación con la compañía especificada.                                                                          | Revisa la relación entre tu app y la compañía configurada. Inténtalo nuevamente o usa otro método de pago.                         |
| Su dominio no está autorizado por la aplicación. Ingrese a la consola de developer para configurar.                                    | Ingresa a la consola de developer y añade tu dominio.                                                                              |
| La transacción no existe, verifique que el identificador enviado sea correcto.                                                         | Verifica que el identificador enviado sea correcto. Inténtalo nuevamente o usa otro método de pago.                                |
| La transacción no pudo ser creada, por favor inténtelo de nuevo.                                                                       | Intenta nuevamente más tarde; si persiste, contacta al soporte.                                                                    |
| Ya existe una transacción con el `ClientTransactionId` especificado.                                                                   | Cambia el identificador; cada transacción debe tener un ID único.                                                                  |
| La transacción ya se encuentra cancelada.                                                                                              | Verifica el estado de la transacción antes de intentar cancelarla.                                                                 |
| La transacción no se pudo cancelar. Puede que ya se encuentre aprobada o cancelada.                                                    | Asegúrate de que no esté ya aprobada o cancelada.                                                                                  |
| Solo se permiten {0} transacciones por día para la misma tarjeta. Por favor póngase en contacto con la persona encargada de la tienda. | Contacta al administrador de la tienda para revisar restricciones.                                                                 |

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

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Action_code</b></th>
      <th><b>Mensaje del rechazo</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>101</td><td>Tarjeta vencida</td></tr>
    <tr><td>116</td><td>Fondos insuficientes</td></tr>
    <tr><td>118</td><td>Tarjeta inválida</td></tr>
    <tr><td>129</td><td>Tarjeta no operativa</td></tr>
    <tr><td>208</td><td>Tarjeta perdida</td></tr>
    <tr><td>209</td><td>Tarjeta robada</td></tr>
    <tr><td>413</td><td>Excediste el límite diario de pagos con Yape</td></tr>
    <tr><td>414</td><td>Tu cuenta fue bloqueada. Vuelve a intentar en 24 horas</td></tr>
    <tr><td>418</td><td>Ingresaste 3 códigos de aprobación incorrectos. Vuelve a intentar en 24 horas</td></tr>
    <tr><td>666</td><td>Problemas de comunicación</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

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

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Action_code</b></th>
      <th><b>Mensaje del rechazo</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>410</td><td>Operacion denegada. OTP Incorrecto</td></tr>
    <tr><td>411</td><td>Operacion denegada. Cuenta Inactiva</td></tr>
    <tr><td>412</td><td>Operacion Denegada. Cuenta no permitida</td></tr>
    <tr><td>413</td><td>Limite diario excedido</td></tr>
    <tr><td>414</td><td>Operacion denegada. OTP Bloqueado</td></tr>
    <tr><td>415</td><td>Operacion denegada. Cuenta no asociada al programa</td></tr>
    <tr><td>416</td><td>Error codigo yape Incorrecto</td></tr>
    <tr><td>417</td><td>Error codigo yape Incorrecto</td></tr>
    <tr><td>418</td><td>Error codigo yape Incorrecto</td></tr>
    <tr><td>503</td><td>Operacion denegada. Problemas de comunicacion</td></tr>
    <tr><td>504</td><td>Operacion denegada. Problemas de comunicacion</td></tr>
    <tr><td>511</td><td>Operacion denegada. Problemas de comunicacion</td></tr>
    <tr><td>599</td><td>Operacion denegada. Problemas de comunicacion</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

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

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Action_code</b></th>
      <th><b>Mensaje del rechazo</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>0</td><td>Afiliación a REC no exitosa</td></tr>
    <tr><td>101</td><td>Tarjeta vencida</td></tr>
    <tr><td>102</td><td>Operación no permitida para esta tarjeta</td></tr>
    <tr><td>113</td><td>Monto no permitido</td></tr>
    <tr><td>116</td><td>Fondos insuficientes</td></tr>
    <tr><td>118</td><td>Tarjeta inválida</td></tr>
    <tr><td>180</td><td>Tarjeta inválida</td></tr>
    <tr><td>190</td><td>Contactar emisor</td></tr>
    <tr><td>191</td><td>Contactar emisor</td></tr>
    <tr><td>208</td><td>Tarjeta perdida</td></tr>
    <tr><td>209</td><td>Tarjeta robada</td></tr>
    <tr><td>666</td><td>Problemas de comunicacion</td></tr>
    <tr><td>670</td><td>Transacción denegada por posible fraude</td></tr>
    <tr><td>754</td><td>Comercio no válido</td></tr>
    <tr><td>599</td><td>Operacion denegada. Problemas de comunicacion</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

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
