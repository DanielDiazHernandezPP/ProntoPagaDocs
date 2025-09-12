---
title: 'Yape On File: One Click Payments'
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: 'Yape On File: One Click Payments | ProntoPaga Docs'
  description: >-
    Yape One Click Payments is a feature that allows users to make payments with
    a single tap after registering their details just once. You can easily add
    this feature to your business through the ProntoPaga API. 
  image: >-
    https://files.readme.io/650f2bd6a9aa7dcded6023e3e7a43d99ee109f556991bb114149d712551079fe-Prontopaga_logotipo.png
  keywords:
    - Yape One Click Payments
    - payment Peru
    - ProntoPaga API
    - integrate Yape
    - pay with Yape
    - One Click Payments integration Peru
    - Yape One Click Payments
    - wallet checkout Peru
    - pagar con Yape Perú
    - integrar Yape Perú
  robots: index
next:
  description: ''
---
Crear un pago con esta modalidad consiste en hacer una solicitud de afiliación a través de nuestra API. Esta solicitud podrá realizarse tanto para versión web, como para versión mobile. Una vez realizada con éxito, el cliente podrá realizar sus pagos posteriores con un solo clic, a través de su cuenta de Yape.

***

## ¿Cómo funciona?

Yape es una aplicación que permite realizar pagos y transferencias de dinero en Perú, utilizando solo el número de celular. Con Yape, los usuarios pueden hacer pagos en línea, recargar saldo en su cuenta o realizar compras en comercios afiliados. Para completar una transacción utilizando este método de pago, el cliente debe seleccionar la opción "Agrega Yape como método de pago", tener una cuenta creada y aprobar la afiliación desde su aplicación.

El proceso de pago con **Yape On File: One Click Payment** en Perú consta de las siguientes etapas:

<Image align="center" src="https://files.readme.io/9e669b7d42a453a5ecb3d022290857c591ebda3fb06a1d823421a87ede68fb27-oneClick-oneclick_1.jpg" />

1. **Selección de afiliación.** Durante el checkout, el cliente elige la opción de "Agrega Yape como método de pago". La siguiente parte del flujo varía según el dispositivo del cliente y si tu comercio tiene o no activado el servicio de validación de pago de terceros:

<Tabs>
  <Tab title="En web">
    1) **Si se tiene desactivado el servicio de validación pago de terceros:** Se le pide al cliente ingresar su número de celular y hacer clic en el botón de "Solicitar aprobación". Luego se le muestran en pantalla instrucciones para abrir su aplicación de Yape, ir a **Aprobar compras > Solicitudes por aprobar**, seleccionar la indicada y hacer clic en **Aprobar afiliación**.
    2) **Si se tiene activado el servicio de validación pago de terceros:** Se le pide al cliente confirmar su número de celular y hacer clic en el botón de "Solicitar aprobación". Si los datos no coinciden, se le muestra un mensaje de error. Si los datos coinciden, se le manda la solicitud directamente a su aplicación de Yape (por notificación y correo). El cliente ingresa, ve en pantalla las solicitudes por aprobar, selecciona la indicada y hace clic en **Confirmar afiliación**.
  </Tab>

  <Tab title="En mobile">
    1. **Si se tiene desactivado el servicio de validación pago de terceros:** El cliente debe hacer clic en el botón de "Solicitar aprobación". Luego se le muestran en pantalla instrucciones para abrir su aplicación de Yape, ir a **Aprobar compras > Solicitudes por aprobar**, seleccionar la indicada y hacer clic en **Aprobar afiliación**.
    2. **Si se tiene activado el servicio de validación pago de terceros:** Se le pide al cliente confirmar su número de celular y hacer clic en el botón de "Solicitar aprobación". Si los datos no coinciden, se le muestra un mensaje de error. Si los datos coinciden, el cliente debe hacer clic en el botón de "Abrir Yape" para ser redirigido a la aplicación. El cliente ingresa, ve en pantalla las solicitudes por aprobar, selecciona la indicada y hace clic en **Confirmar afiliación**. Para dispositivos móviles, se debe agregar un deeplink de Yape. Este deeplink redirecciona automáticamente al usuario a la sección de **Código de aprobación** de su aplicación de Yape. La URL del deeplink es: `https://www.yape.com.pe/app/checkout/approval_code`.
  </Tab>
</Tabs>

2. **Confirmación de la afiliación.** Se hace la afiliación, la pantalla de tu comercio se actualiza y se muestra el resultado de la transacción. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.
3. **One Click Payment.** Ahora el cliente puede ver en el checkout la sección de "Métodos de pago guardados", con su cuenta Yape. Al elegirla, comienza el proceso de pago, y el dinero se mueve desde la wallet del cliente hacia la cuenta de tu comercio.
4. **Confirmación del One Click Payment.** La pantalla de tu comercio se actualiza y se muestra el resultado de la transacción. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

***

<br />

## Versiones

Es posible integrar el servicio **Yape On File: One Click Payment** de dos maneras:

* **Versión web.**
* **Versión mobile.**

Más abajo, verás las instrucciones para la versión web. Después, dentro de esta misma página, verás los pasos para la versión mobile. Para una navegación más rápida, te sugerimos usar el índice de la derecha.

***

<br />

## Validación pago terceros

ProntoPaga cuenta con un servicio de validación de pago de terceros, el cual confirma que el número de teléfono celular ingresado coincida con los datos de la cuenta del cliente, evitando que se realicen pagos de terceros, y maximizando la seguridad de tus transacciones.

Esta validación se asigna de forma automática a ciertos comercios integrados con nosotros. Si deseas activarla o desactivarla, comunícate con nuestro equipo de integración. Toma en cuenta las diferencias que existen en la experiencia del cliente para cada caso. Esas diferencias están descritas en la sección de **¿Cómo funciona?** de este artículo, en la parte superior.

<br />

### Motivos de rechazo de validación pago terceros

A continuación, se listan los posibles motivos de validación pago terceros, así como los mensajes que se mostrarán.

| Motivo                                                                                                             | Mensaje                                                                                                          |
| :----------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------- |
| El número de celular y el documento de identidad no están asociados.                                               | `The user's phone number and identity document do not match`                                                     |
| El usuario no tiene una cuenta de Yape activa.                                                                     | `The user does not have an active Yape account`                                                                  |
| El tipo de documento de identidad proporcionado del servicio de validación es distinto al enviado por el comercio. | `The Document Type provided by the validation service does not match the one sent by the Merchant`               |
| El servicio de validación no está respondiendo correctamente.                                                      | `The validation service is currently unavailable. Please try again, and if the error persists, contact your KAM` |

***

<br />

## Integra la versión web

El front-end será el encargado de recopilar los datos necesarios de tu cliente para comenzar el proceso de afiliación, mientras que tu back-end estará integrado con nuestra API, procesando la afiliación y el pago.

<br />

### Crea una afiliación

Para crear una solicitud de afiliación de tipo One Click Payment, deberás usar [este endpoint](https://docs.prontopaga.com/reference/affiliations) y enviar un body request con los datos necesarios. A continuación, puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "origin": "WEB",
  "document": "12345678",
  "phoneNumber": "999999999",
  "webhookUrl": "https://www.webhook.com",
  "type": "ON_DEMAND",
  "clientName": "John Doe",
  "clientDocumentType": "PP"
}
```

Si la afiliación se realizó con éxito, se mostrará el resultado de la transacción en pantalla. A su vez, tu comercio recibirá la confirmación a través de los webhooks que hayas configurado.

> 🚧 Tiempo de expiración
>
> El cliente debe aprobar la afiliación en menos de 15 minutos. En caso de no hacerse, la afiliación expirará a los 15 minutos.

<br />

<br />

### Crea un One Click Payment

Una vez que tu cliente esté afiliado correctamente, podrá realizar One Click Payments en tu comercio. Para solicitar un pago, deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `yape_cof_payment` como método de pago en el body de la solicitud, así como agregar el identificador único (UID) de la afiliación de la wallet del cliente en el parámetro `wallet_uid`.

La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, monto, entre otros.

<NotaFirma />

#### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la [solicitud de un One Click Payment](https://docs.prontopaga.com/reference/create-payment):

```json
{
  "currency": "PEN",
  "country": "PE",
  "amount": "100.90",
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "12345678912",
  "paymentMethod": "yape_cof_payment",
  "urlConfirmation": "https://www.webhook.com",
  "order": "XYZ789",
  "wallet_uid": "01JXNCAK8TX6PNBBN7ZNBSAEJH",
  "sign": "Signature of the parameters"
}
```

> 🚧 Límite transaccional
>
> Recuerda que el límite máximo por transacción y por día es de 2000 soles. Esto significa que, si un cliente realiza hoy una compra por ese monto, no podrá hacer otra transacción hasta mañana.

#### Confirmación de un pago

Una vez que se haya completado el pago, ProntoPaga le mostrará al cliente una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

> 📘 Notificación del estado de la transacción
>
> Para configurar el webhook que irá en el campo `urlConfirmation` y recibir notificaciones con el estado de tu transacción, revisa [este artículo](https://docs.prontopaga.com/docs/webhooks).

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los PayIns](https://docs.prontopaga.com/docs/payins-status).

### Motivos de rechazo de un pago

A continuación, se listan los posibles motivos de rechazo para un pago de tipo One Click Payment, así como los mensajes que se muestran en pantalla a tu cliente.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Motivo
      </th>

      <th>
        Mensaje
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Error por cuenta yapera no existe o inactiva
      </td>

      <td>
        * **Ocurrió un inconveniente.** Comunícate con Yape por WhatsApp al 939 339 299 para brindarte más información.
      </td>
    </tr>

    <tr>
      <td>
        Error por tipo de cuenta yapera no soportada
      </td>

      <td>
        * **Tu tipo de cuenta Yape no está habilitada para esta funcionalidad.** Conoce tu tipo de cuenta ingresando al menú de Yape, opción Mi perfil.
      </td>
    </tr>

    <tr>
      <td>
        Error por cuenta yapera en blacklist
      </td>

      <td>
        * **Por seguridad, tu cuenta Yape fue bloqueada.** Comunícate con Yape por Whatsapp al 939 339 299 para brindarte más información.
      </td>
    </tr>

    <tr>
      <td>
        Error por cuenta yapera bloqueada para el canal e-commerce
      </td>

      <td>
        * **Tu cuenta Yape está bloqueada temporalmente.** Por seguridad, tu cuenta de Yape fue bloqueada solo para compras por internet. Vuelve a intentar en 24 horas.
      </td>
    </tr>

    <tr>
      <td>
        Error por suscripción confirmada no existente
      </td>

      <td>
        * **Ocurrió un inconveniente.** Estamos poniendo manos a la obra. Por favor, vuelve a intentarlo en unos minutos.
      </td>
    </tr>

    <tr>
      <td>
        Error por no coincidencia del código de comercio de la suscripción
      </td>

      <td>
        * **Ocurrió un inconveniente.** Estamos poniendo manos a la obra. Por favor, vuelve a intentarlo en unos minutos.
      </td>
    </tr>

    <tr>
      <td>
        Error por límite diario excedido
      </td>

      <td>
        * **Esta operación excede tu monto límite diario para compras por internet.** Vuelve a intentarlo el día de mañana.
      </td>
    </tr>

    <tr>
      <td>
        Error por autorización detectada como fraude
      </td>

      <td>
        * **Detectamos una actividad sospechosa.** Comunícate con Yape por WhatsApp al 939 339 299 para validar y brindarte una solución.
      </td>
    </tr>

    <tr>
      <td>
        Error por fondos insuficientes
      </td>

      <td>
        * **Necesitas más saldo para este pago.** No cuentas con saldo suficiente para realizar este pago.
      </td>
    </tr>

    <tr>
      <td>
        Error por cuenta bancaria bloqueada
      </td>

      <td>
        * **Tu cuenta asociada a Yape está bloqueada.** No se pudo realizar el pago. Comunícate con Yape por WhatsApp al 939 339 299 para brindarte una solución.
      </td>
    </tr>

    <tr>
      <td>
        Error por timeout en el proceso de transferencia
      </td>

      <td>
        * **Ocurrió un inconveniente.** Estamos poniendo manos a la obra. Por favor, vuelve a intentarlo en unos minutos.
      </td>
    </tr>

    <tr>
      <td>
        Error por cuenta yapera no encontrada
      </td>

      <td>
        * **Ocurrió un inconveniente.** Comunícate con Yape por WhatsApp al 939 339 299 para brindarte más información.
      </td>
    </tr>

    <tr>
      <td>
        Error por tarjeta BCP desactualizada
      </td>

      <td>
        * **Necesitas asociar tu nueva tarjeta BCP a Yape.** Ingresa al Centro de Ayuda de [www.yape.com.pe](http://www.yape.com.pe) y conoce los pasos para asociar tu nueva tarjeta y renovar tu cuenta.
      </td>
    </tr>

    <tr>
      <td>
        Error por tarjeta BCP bloqueada
      </td>

      <td>
        * **Tu tarjeta asociada a Yape está bloqueada, necesitas una nueva.** Si ya tienes tu nueva tarjeta, ingresa al Centro de Ayuda de Yape [www.yape.com.pe](http://www.yape.com.pe) y conoce los pasos para renovar tu cuenta con tus mismos datos.
      </td>
    </tr>

    <tr>
      <td>
        Error por tarjeta digital inválida
      </td>

      <td>
        * **Tu cuenta está bloqueada.** Ingresa al Centro de Ayuda de [www.yape.com.pe](http://www.yape.com.pe) y conoce los pasos para eliminar tu Yape y crear una nueva cuenta. Si tienes saldo, acude a una agencia BCP con tu DNI para retirarlo.
      </td>
    </tr>

    <tr>
      <td>
        Error por tarjeta BCP vencida
      </td>

      <td>
        * **Tu cuenta está vencida.** Si ya tienes tu nueva tarjeta, ingresa al Centro de Ayuda de Yape [www.yape.com.pe](http://www.yape.com.pe) y conoce los pasos para renovar tu cuenta. De no tenerla, acude a una agencia BCP y solicita una nueva para renovar tu cuenta.
      </td>
    </tr>

    <tr>
      <td>
        Error por cuenta bancaria
        cerrada
      </td>

      <td>
        * **Tu cuenta asociada a Yape está cerrada.** No se pudo realizar el pago. Comunícate con Yape por Whatsapp al 939 339 299 para brindarte una solución.
      </td>
    </tr>

    <tr>
      <td>
        Error inesperado ocurrido en el servidor
      </td>

      <td>
        * **Ocurrió un inconveniente.** Estamos poniendo manos a la obra. Por favor, vuelve a intentarlo en unos minutos.
      </td>
    </tr>
  </tbody>
</Table>

<br />

### Devolución de un One Click Payment

Para solicitar la devolución de un pago exitoso realizado con este método, usa [este endpoint](https://docs.prontopaga.com/reference/refunds). A continuación, se muestra un ejemplo del body request que debe llevar:

```json
{
  "reference": "1111111111",
  "clientDocument": "12345678912",
  "amount": "100.90",
  "urlCallbackRefund": "https://www.webhook.com",
  "sign": "Signature of the parameters"
}
```

<br />

### Motivos de rechazo de una devolución

A continuación, se listan los posibles motivos de rechazo para una devolución de un pago realizado con este método, así como las acciones de Yape al respecto.

| Motivo                                                | Acción                                                |
| :---------------------------------------------------- | :---------------------------------------------------- |
| Error por cuenta yapera no encontrada                 | Yape notifica sobre la transacción denegada por email |
| Error por operación de cargo no encontrado            | Yape notifica sobre la transacción denegada por email |
| Error por plazo vencido para solicitar una devolución | Yape notifica sobre la transacción denegada por email |
| Error en monto de devolución                          | Yape notifica sobre la transacción denegada por email |
| Error por cuenta bancaria cerrada                     | Yape notifica sobre la transacción denegada por email |
| Error inesperado ocurrido en el servidor              | Yape notifica sobre la transacción denegada por email |

<br />

### Lista de afiliaciones

Puedes obtener una lista con las afiliaciones activas de cierto cliente, haciendo una consulta con su número de documento. Utiliza [este endpoint](https://docs.prontopaga.com/reference/affiliations-list) para ello.

<br />

### Detalle de una afiliación

Consulta el detalle del estado de una afiliación, usando el identificador único (UID) de la afiliación de la wallet del cliente. Utiliza [este endpoint](https://docs.prontopaga.com/reference/affiliation-details) para conocer el detalle.

<br />

### Cancelar una afiliación

Para cancelar la afiliación de un cliente, y que éste ya no vea asociada su wallet a tu comercio, ni pueda realizar One Click Payments, haz una solicitud a [este endpoint](https://docs.prontopaga.com/reference/affiliation-cancel).

Para ello, deberás enviar el identificador único (UID) de la afiliación de la wallet del cliente en el path. Una vez finalizado el proceso de cancelación de forma exitosa, el cliente recibirá una notificación push de Yape, confirmando el proceso.

***

<br />

## Integra la versión mobile

El front-end será el encargado de recopilar los datos necesarios de tu cliente para comenzar el proceso de afiliación, mientras que tu back-end estará integrado con nuestra API, procesando la afiliación y el pago.

<br />

### Crea una afiliación

Para crear una solicitud de afiliación de tipo One Click Payment, deberás usar [este endpoint](https://docs.prontopaga.com/reference/affiliations) y enviar un body request con los datos necesarios. A continuación, puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "origin": "MOBILE",
  "document": "12345678",
  "webhookUrl": "https://www.webhook.com",
  "type": "ON_DEMAND",
  "clientName": "John Doe",
  "clientDocumentType": "PP"
}
```

Si la afiliación se realizó con éxito, se mostrará el resultado de la transacción en pantalla. A su vez, tu comercio recibirá la confirmación a través de los webhooks que hayas configurado.

> 🚧 Tiempo de expiración
>
> El cliente debe aprobar la afiliación en menos de 15 minutos. En caso de no hacerse, la afiliación expirará a los 15 minutos.

<br />

### Crea un One Click Payment

Una vez que tu cliente esté afiliado correctamente, podrá realizar pagos One Click en tu comercio. Para solicitar un pago, deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `yape_cof_payment` como método de pago en el body de la solicitud, así como agregar el identificador único (UID) de la afiliación de la wallet del cliente en el parámetro `wallet_uid`.

La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, monto, entre otros.

<NotaFirma />

#### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la [solicitud de un One Click Payment](https://docs.prontopaga.com/reference/create-payment):

```json
{
  "currency": "PEN",
  "country": "PE",
  "amount": "100.90",
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "12345678912",
  "paymentMethod": "yape_cof_payment",
  "urlConfirmation": "https://www.webhook.com",
  "order": "XYZ789",
  "wallet_uid": "01JXNCAK8TX6PNBBN7ZNBSAEJH",
  "sign": "Signature of the parameters"
}
```

> 🚧 Límite transaccional
>
> Recuerda que el límite máximo por transacción y por día es de 2000 soles. Esto significa que, si un cliente realiza hoy una compra por ese monto, no podrá hacer otra transacción hasta mañana.

#### Confirmación de un pago

Una vez que se haya completado el pago, ProntoPaga le mostrará al cliente una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

> 📘 Notificación del estado de la transacción
>
> Para configurar el webhook que irá en el campo `urlConfirmation` y recibir notificaciones con el estado de tu transacción, revisa [este artículo](https://docs.prontopaga.com/docs/webhooks).

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los PayIns](https://docs.prontopaga.com/docs/payins-status).

<br />

### Motivos de rechazo de un pago

A continuación, se listan los posibles motivos de rechazo para un pago de tipo One Click Payment, así como los mensajes que se muestran en pantalla a tu cliente.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Motivo
      </th>

      <th>
        Mensaje
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Error por cuenta yapera no existe o inactiva
      </td>

      <td>
        * **Ocurrió un inconveniente.** Comunícate con Yape por WhatsApp al 939 339 299 para brindarte más información.
      </td>
    </tr>

    <tr>
      <td>
        Error por tipo de cuenta yapera no soportada
      </td>

      <td>
        * **Tu tipo de cuenta Yape no está habilitada para esta funcionalidad.** Conoce tu tipo de cuenta ingresando al menú de Yape, opción Mi perfil.
      </td>
    </tr>

    <tr>
      <td>
        Error por cuenta yapera en blacklist
      </td>

      <td>
        * **Por seguridad, tu cuenta Yape fue bloqueada.** Comunícate con Yape por Whatsapp al 939 339 299 para brindarte más información.
      </td>
    </tr>

    <tr>
      <td>
        Error por cuenta yapera bloqueada para el canal e-commerce
      </td>

      <td>
        * **Tu cuenta Yape está bloqueada temporalmente.** Por seguridad, tu cuenta de Yape fue bloqueada solo para compras por internet. Vuelve a intentar en 24 horas.
      </td>
    </tr>

    <tr>
      <td>
        Error por suscripción confirmada no existente
      </td>

      <td>
        * **Ocurrió un inconveniente.** Estamos poniendo manos a la obra. Por favor, vuelve a intentarlo en unos minutos.
      </td>
    </tr>

    <tr>
      <td>
        Error por no coincidencia del código de comercio de la suscripción
      </td>

      <td>
        * **Ocurrió un inconveniente.** Estamos poniendo manos a la obra. Por favor, vuelve a intentarlo en unos minutos.
      </td>
    </tr>

    <tr>
      <td>
        Error por límite diario excedido
      </td>

      <td>
        * **Esta operación excede tu monto límite diario para compras por internet.** Vuelve a intentarlo el día de mañana.
      </td>
    </tr>

    <tr>
      <td>
        Error por autorización detectada como fraude
      </td>

      <td>
        * **Detectamos una actividad sospechosa.** Comunícate con Yape por WhatsApp al 939 339 299 para validar y brindarte una solución.
      </td>
    </tr>

    <tr>
      <td>
        Error por fondos insuficientes
      </td>

      <td>
        * **Necesitas más saldo para este pago.** No cuentas con saldo suficiente para realizar este pago.
      </td>
    </tr>

    <tr>
      <td>
        Error por cuenta bancaria bloqueada
      </td>

      <td>
        * **Tu cuenta asociada a Yape está bloqueada.** No se pudo realizar el pago. Comunícate con Yape por WhatsApp al 939 339 299 para brindarte una solución.
      </td>
    </tr>

    <tr>
      <td>
        Error por timeout en el proceso de transferencia
      </td>

      <td>
        * **Ocurrió un inconveniente.** Estamos poniendo manos a la obra. Por favor, vuelve a intentarlo en unos minutos.
      </td>
    </tr>

    <tr>
      <td>
        Error por cuenta yapera no encontrada
      </td>

      <td>
        * **Ocurrió un inconveniente.** Comunícate con Yape por WhatsApp al 939 339 299 para brindarte más información.
      </td>
    </tr>

    <tr>
      <td>
        Error por tarjeta BCP desactualizada
      </td>

      <td>
        * **Necesitas asociar tu nueva tarjeta BCP a Yape.** Ingresa al Centro de Ayuda de [www.yape.com.pe](http://www.yape.com.pe) y conoce los pasos para asociar tu nueva tarjeta y renovar tu cuenta.
      </td>
    </tr>

    <tr>
      <td>
        Error por tarjeta BCP bloqueada
      </td>

      <td>
        * **Tu tarjeta asociada a Yape está bloqueada, necesitas una nueva.** Si ya tienes tu nueva tarjeta, ingresa al Centro de Ayuda de Yape [www.yape.com.pe](http://www.yape.com.pe) y conoce los pasos para renovar tu cuenta con tus mismos datos.
      </td>
    </tr>

    <tr>
      <td>
        Error por tarjeta digital inválida
      </td>

      <td>
        * **Tu cuenta está bloqueada.** Ingresa al Centro de Ayuda de [www.yape.com.pe](http://www.yape.com.pe) y conoce los pasos para eliminar tu Yape y crear una nueva cuenta. Si tienes saldo, acude a una agencia BCP con tu DNI para retirarlo.
      </td>
    </tr>

    <tr>
      <td>
        Error por tarjeta BCP vencida
      </td>

      <td>
        * **Tu cuenta está vencida.** Si ya tienes tu nueva tarjeta, ingresa al Centro de Ayuda de Yape [www.yape.com.pe](http://www.yape.com.pe) y conoce los pasos para renovar tu cuenta. De no tenerla, acude a una agencia BCP y solicita una nueva para renovar tu cuenta.
      </td>
    </tr>

    <tr>
      <td>
        Error por cuenta bancaria
        cerrada
      </td>

      <td>
        * **Tu cuenta asociada a Yape está cerrada.** No se pudo realizar el pago. Comunícate con Yape por Whatsapp al 939 339 299 para brindarte una solución.
      </td>
    </tr>

    <tr>
      <td>
        Error inesperado ocurrido en el servidor
      </td>

      <td>
        * **Ocurrió un inconveniente.** Estamos poniendo manos a la obra. Por favor, vuelve a intentarlo en unos minutos.
      </td>
    </tr>
  </tbody>
</Table>

<br />

### Devolución de un One Click Payment

Para solicitar la devolución de un pago exitoso realizado con este método, usa [este endpoint](https://docs.prontopaga.com/reference/refunds). A continuación, se muestra un ejemplo del body request que debe llevar:

```json
{
  "reference": "1111111111",
  "clientDocument": "12345678912",
  "amount": "100.90",
  "urlCallbackRefund": "https://www.webhook.com",
  "sign": "Signature of the parameters"
}
```

<br />

### Motivos de rechazo de una devolución

A continuación, se listan los posibles motivos de rechazo para una devolución de un pago realizado con este método, así como las acciones de Yape al respecto.

| Motivo                                                | Acción                                                |
| :---------------------------------------------------- | :---------------------------------------------------- |
| Error por cuenta yapera no encontrada                 | Yape notifica sobre la transacción denegada por email |
| Error por operación de cargo no encontrado            | Yape notifica sobre la transacción denegada por email |
| Error por plazo vencido para solicitar una devolución | Yape notifica sobre la transacción denegada por email |
| Error en monto de devolución                          | Yape notifica sobre la transacción denegada por email |
| Error por cuenta bancaria cerrada                     | Yape notifica sobre la transacción denegada por email |
| Error inesperado ocurrido en el servidor              | Yape notifica sobre la transacción denegada por email |

<br />

### Lista de afiliaciones

Puedes obtener una lista con las afiliaciones activas de cierto cliente, haciendo una consulta con su número de documento. Utiliza [este endpoint](https://docs.prontopaga.com/reference/affiliations-list) para ello.

<br />

### Detalle de una afiliación

Consulta el detalle del estado de una afiliación, usando el identificador único (UID) de la afiliación de la wallet del cliente. Utiliza [este endpoint](https://docs.prontopaga.com/reference/affiliation-details) para conocer el detalle.

<br />

### Cancelar una afiliación

Para cancelar la afiliación de un cliente, y que éste ya no vea asociada su wallet a tu comercio, ni pueda realizar One Click Payments, haz una solicitud a [este endpoint](https://docs.prontopaga.com/reference/affiliation-cancel).

Para ello, deberás enviar el identificador único (UID) de la afiliación de la wallet del cliente en el path. Una vez finalizado el proceso de cancelación de forma exitosa, el cliente recibirá una notificación push de Yape, confirmando el proceso.

***

<br />

## Prueba tu integración

Contamos con demos que simulan la experiencia de pago del cliente, en donde podrás hacer pruebas. Conócelos aquí:

<Embed url="https://experience.prontopaga.com/" href="https://experience.prontopaga.com/" typeOfEmbed="iframe" height="1000px" width="100%" iframe="true" html="false" />

***

<br />

## Certifica tu integración

La certificación de la integración en _sandbox_ es un paso obligatorio que todos los comercios deben realizar antes de recibir sus credenciales de producción. Su propósito es asegurar que la integración cumpla con los estándares técnicos, funcionales y de seguridad requeridos por ProntoPaga. Dentro de esta sección, se establecen los requisitos que deben cumplirse sin excepción para que la certificación sea aprobada.

<br />

### Requisitos de certificación

A continuación, encontrarás los distintos requisitos necesarios para completar tu certificación:

<Tabs>
  <Tab title="ID del cliente">
    * ❌ El documento de identidad del cliente no debe ser modificable en ningún punto de la transacción.
    * ✅ Es recomendable que este dato no se muestre en el *checkout*. Solo puede estar disponible en la sección de perfil del usuario autenticado.
    * ⚠️ Esta medida tiene como objetivo prevenir fraudes y evitar que se realicen transacciones en nombre de terceros o menores de edad.
  </Tab>

  <Tab title="Logotipos">
    * 📥 Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu *front-end*. Puedes [descargarlos aquí](https://drive.google.com/uc?export=download\&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr).
    * 🔎 Todos los nombres y logos de los métodos de pago habilitados deben mostrarse de forma clara, sin modificaciones visuales o estilísticas que puedan generar confusión o inducir a errores.
    * ✅ Se recomienda ordenarlos según su popularidad o frecuencia de uso, para mejorar la experiencia del usuario y optimizar la conversión.
  </Tab>

  <Tab title="Mensajes al usuario">
    * ✅ El *checkout* debe incluir mensajes claros y visibles que orienten al usuario durante todo el proceso.

    ❗ Es obligatorio mostrar:

    * ℹ️ Montos mínimos y máximos permitidos para cada método de pago.
    * ℹ️ Estados transaccionales con claridad: por ejemplo, **Transacción aprobada** o **Transacción rechazada**, junto con una sugerencia de los pasos a seguir en caso de que corresponda.
  </Tab>

  <Tab title="Consideraciones importantes">
    * ❌ No almacenar datos sensibles del cliente en tu base de datos.
    * ✅ La certificación se otorga únicamente si estos requisitos se cumplen en su totalidad en el entorno de *sandbox*.
    * 💻 Una vez validada la integración, se habilitarán las credenciales para el entorno productivo.
    * ⚠️ El incumplimiento de estos requisitos podrá resultar en la denegación de la certificación.
  </Tab>
</Tabs>
