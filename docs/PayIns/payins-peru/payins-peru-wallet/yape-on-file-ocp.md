---
title: 'Yape On File: One Click Payments'
excerpt: Conoce el paso a paso de cómo crear un pago con Yape en Perú.
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

El proceso de pago con **Yape On File: One Click Payments** en Perú consta de las siguientes etapas:

<Image align="center" border={false} src="https://files.readme.io/9e669b7d42a453a5ecb3d022290857c591ebda3fb06a1d823421a87ede68fb27-oneClick-oneclick_1.jpg" />

1. **Selección de afiliación.** Durante el checkout, el cliente elige la opción de "Agrega Yape como método de pago". La siguiente parte del flujo varía según el dispositivo del cliente y si tu comercio tiene o no activado el servicio de validación de pago de terceros:

**🌐 En web:**

<Cards columns={2}>
  <Card title="Si se tiene desactivado el servicio de validación pago de terceros">
    Se le pide al cliente ingresar su número de celular para solicitar el pago. Luego, se le muestra en pantalla un instructivo para abrir su aplicación y aprobar el pago en la sección de **Aprobar compras**.
  </Card>

  <Card title="Si se tiene activado el servicio de validación pago de terceros">
    Se le pide al cliente confirmar su número de celular y documento de identidad. Si los datos (número de celular y documento de identidad) no coinciden, se muestra un mensaje de error. Si los datos coinciden, la solicitud se envía directamente a su aplicación de Yape, donde el cliente podrá visualizar en pantalla las solicitudes pendientes, seleccionar la correspondiente y hacer clic en **Confirmar**.

    En el caso del proceso de afiliación, Yape envía un correo electrónico únicamente cuando esta ha sido exitosa, y, en caso de una desafiliación, el cliente recibe una notificación push en su app.
  </Card>
</Cards>

**📱En mobile:**

<Cards columns={2}>
  <Card title="Si se tiene desactivado el servicio de validación pago de terceros">
    El cliente debe hacer clic en el botón **Solicitar aprobación**. Luego, será redirigido a la aplicación de Yape mediante un deeplink dinámico generado a demanda, el cual estará activo por 15 minutos.

    Después de ingresar su clave de acceso, aparecerá un modal en la pantalla, donde podrá aprobar la afiliación directamente.
  </Card>

  <Card title="Si se tiene activado el servicio de validación pago de terceros">
    Se le pide al cliente confirmar su número de celular y su documento de identidad, y luego hacer clic en el botón **Solicitar aprobación**. Si alguno de estos datos (número de celular y documento de identidad) no coincide, se muestra un mensaje de error. Si los datos coinciden, el cliente debe hacer clic en el botón **Abrir Yape** para ser redirigido a la aplicación. El cliente ingresa, visualiza en pantalla las solicitudes por aprobar, selecciona la indicada y hace clic en **Confirmar afiliación**.

    Se utiliza un deeplink genérico, el cual redirige automáticamente al usuario a una sección específica dentro de la app de Yape.

    La URL del deeplink genérico es:
    `https://www.yape.com.pe/app/checkout/approval_code`.
  </Card>
</Cards>

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

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Motivo</b></th>
      <th><b>Mensaje</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>El número de celular y el documento de identidad no están asociados.</td><td><code>The user's phone number and identity document do not match</code></td></tr>
    <tr><td>El usuario no tiene una cuenta de Yape activa.</td><td><code>The user does not have an active Yape account</code></td></tr>
    <tr><td>El tipo de documento de identidad proporcionado del servicio de validación es distinto al enviado por el comercio.</td><td><code>The Document Type provided by the validation service does not match the one sent by the Merchant</code></td></tr>
    <tr><td>El servicio de validación no está respondiendo correctamente.</td><td><code>The validation service is currently unavailable. Please try again, and if the error persists, contact your KAM</code></td></tr>
  </tbody>
</table>
`}</HTMLBlock>

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

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Código</b></th>
			<th><b>Motivo</b></th>
      <th><b>Mensaje</b></th>
    </tr>
  </thead>
  <tbody>    
    <tr><td><code>YPSBS998</code></td><td>Error por incumplimiento de contrato</td><td><ul><li><b>Ocurrió un inconveniente.</b> Estamos poniendo manos a la obra. Por favor, vuelve a intentarlo en unos minutos.</li></ul></td></tr>
		<tr><td><code>YPSBS003</code></td><td>Error por cuenta yapera no existe o inactiva</td><td><ul><li><b>Ocurrió un inconveniente.</b> Comunícate con Yape por WhatsApp al 939 339 299 para brindarte más información.</li></ul></td></tr>
    <tr><tr><td><code>YPSBS004</code></td><td>Error por tipo de cuenta yapera no soportada</td><td><ul><li><b>Tu tipo de cuenta Yape no está habilitada para esta funcionalidad.</b> Conoce tu tipo de cuenta ingresando al menú de Yape, opción Mi perfil.</li></ul></td></tr>
    <tr><tr><td><code>YPSBS005</code></td><td>Error por cuenta yapera en blacklist</td><td><ul><li><b>Por seguridad, tu cuenta Yape fue bloqueada.</b> Comunícate con Yape por Whatsapp al 939 339 299 para brindarte más información.</li></ul></td></tr>
    <tr><tr><td><code>YPSBS006</code></td><td>Error por cuenta yapera bloqueada para el canal e-commerce</td><td><ul><li><b>Tu cuenta Yape está bloqueada temporalmente.</b> Por seguridad, tu cuenta de Yape fue bloqueada solo para compras por internet. Vuelve a intentar en 24 horas.</li></ul></td></tr>  
    <tr><td><code>YPSBS014</code></td><td>Error por suscripción confirmada no existente</td><td><ul><li><b>Ocurrió un inconveniente.</b> Estamos poniendo manos a la obra. Por favor, vuelve a intentarlo en unos minutos.</li></ul></td></tr>  
 		<tr><td><code>YPSBS015</code></td><td>Error por no coincidencia del código de comercio de la suscripción</td><td><ul><li><b>Ocurrió un inconveniente.</b> Estamos poniendo manos a la obra. Por favor, vuelve a intentarlo en unos minutos.</li></ul></td></tr>    
    <tr><td><code>YPSBS016</code></td><td>Error por límite diario excedido</td><td><ul><li><b>Esta operación excede tu monto límite diario para compras por internet.</b> Vuelve a intentarlo el día de mañana.</li></ul></td></tr>
    <tr><td><code>YPTRX001</code></td><td>Error por autorización detectada como fraude</td><td><ul><li><b>Detectamos una actividad sospechosa.</b> Comunícate con Yape por WhatsApp al 939 339 299 para validar y brindarte una solución.</li></ul></td></tr>
    <tr><td><code>YPTRX002</code></td><td>Error por fondos insuficientes</td><td><ul><li><b>Necesitas más saldo para este pago.</b> No cuentas con saldo suficiente para realizar este pago.</li></ul></td></tr>
   <tr><td><code>YPTRX003</code></td><td>Error por cuenta bancaria bloqueada</td><td><ul><li><b>Tu cuenta asociada a Yape está bloqueada.</b> No se pudo realizar el pago. Comunícate con Yape por WhatsApp al 939 339 299 para brindarte una solución.</li></ul></td></tr> 
    <tr><td><code>YPTRX004</code></td><td>Error por timeout en el proceso de transferencia</td><td><ul><li><b>Ocurrió un inconveniente.</b> Estamos poniendo manos a la obra. Por favor, vuelve a intentarlo en unos minutos.</li></ul></td></tr>
		    <tr><td><code>YPTRX005</code></td><td>Error por cuenta yapera no encontrada</td><td><ul><li><b>Ocurrió un inconveniente.</b> Comunícate con Yape por WhatsApp al 939 339 299 para validar y brindarte una solución.</li></ul></td></tr>
    <tr><td><code>YPTRX006</code></td><td>Error por tarjeta BCP desactualizada</td><td><ul><li><b>Necesitas asociar tu nueva tarjeta BCP a Yape.</b> Ingresa al Centro de Ayuda de <a href=" www.yape.com.pe">www.yape.com.pe</a> y conoce los pasos para asociar tu nueva tarjeta y renovar tu cuenta.</li></ul></td></tr>
    <tr><td><code>YPTRX007</code></td><td>Error por tarjeta BCP bloqueada</td><td><ul><li><b>Tu tarjeta asociada a Yape está bloqueada, necesitas una nueva.</b> Si ya tienes tu nueva tarjeta, ingresa al Centro de Ayuda de Yape <a href=" www.yape.com.pe">www.yape.com.pe</a> y conoce los pasos para renovar tu cuenta con tus mismos datos.</li></ul></td></tr>
    <tr><td><code>YPTRX008</code></td><td>Error por tarjeta digital inválida</td><td><ul><li><b>Tu cuenta está bloqueada.</b> Si ya tienes tu nueva tarjeta, ingresa al Centro de Ayuda de Yape <a href=" www.yape.com.pe">www.yape.com.pe</a> y conoce los pasos para renovar tu cuenta con tus mismos datos.</li></ul></td></tr>
    <tr><td><code>YPTRX009</code></td><td>Error por tarjeta BCP vencida</td><td><ul><li><b>Tu cuenta está vencida.</b> Si ya tienes tu nueva tarjeta, ingresa al Centro de Ayuda de Yape <a href=" www.yape.com.pe">www.yape.com.pe</a> y conoce los pasos para renovar tu cuenta. De no tenerla, acude a una agencia BCP y solicita una nueva para renovar tu cuenta.</li></ul></td></tr>
    <tr><td><code>YPTRX013</code></td><td>Error por cuenta bancaria cerrada</td><td><ul><li><b>Tu cuenta asociada a Yape está cerrada.</b> No se pudo realizar el pago. Comunícate con Yape por Whatsapp al 939 339 299 para brindarte una solución.</li></ul></td></tr>
    <tr><td><code>YPSBS999</code></td><td>Error inesperado ocurrido en el servidor</td><td><ul><li><b>Ocurrió un inconveniente. </b> Estamos poniendo manos a la obra. Por favor, vuelve a intentarlo en unos minutos</li></ul></td></tr>
  </tbody>
</table>
`}</HTMLBlock>

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

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Motivo</b></th>
      <th><b>Mensaje</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Error por cuenta yapera no existe o inactiva</td><td><ul><li><b>Ocurrió un inconveniente.</b> Comunícate con Yape por WhatsApp al 939 339 299 para brindarte más información.</li></ul></td></tr>
    <tr><td>Error por tipo de cuenta yapera no soportada</td><td><ul><li><b>Tu tipo de cuenta Yape no está habilitada para esta funcionalidad.</b> Conoce tu tipo de cuenta ingresando al menú de Yape, opción Mi perfil.</li></ul></td></tr>
    <tr><td>Error por cuenta yapera en blacklist</td><td><ul><li><b>Por seguridad, tu cuenta Yape fue bloqueada.</b> Comunícate con Yape por Whatsapp al 939 339 299 para brindarte más información.</li></ul></td></tr>
    <tr><td>Error por cuenta yapera bloqueada para el canal e-commerce</td><td><ul><li><b>Tu cuenta Yape está bloqueada temporalmente.</b> Por seguridad, tu cuenta de Yape fue bloqueada solo para compras por internet. Vuelve a intentar en 24 horas.</li></ul></td></tr>  
		<tr><td>Error por suscripción confirmada no existente</td><td><ul><li><b>Ocurrió un inconveniente.</b> Estamos poniendo manos a la obra. Por favor, vuelve a intentarlo en unos minutos.</li></ul></td></tr>  
 		<tr><td>Error por no coincidencia del código de comercio de la suscripción</td><td><ul><li><b>Ocurrió un inconveniente.</b> Estamos poniendo manos a la obra. Por favor, vuelve a intentarlo en unos minutos.</li></ul></td></tr>    
    <tr><td>Error por límite diario excedido</td><td><ul><li><b>Esta operación excede tu monto límite diario para compras por internet.</b> Vuelve a intentarlo el día de mañana.</li></ul></td></tr>
    <tr><td>Error por autorización detectada como fraude</td><td><ul><li><b>Detectamos una actividad sospechosa.</b> Comunícate con Yape por WhatsApp al 939 339 299 para validar y brindarte una solución.</li></ul></td></tr>
    <tr><td>Error por fondos insuficientes</td><td><ul><li><b>Necesitas más saldo para este pago.</b> No cuentas con saldo suficiente para realizar este pago.</li></ul></td></tr>
   <tr><td>Error por cuenta bancaria bloqueada</td><td><ul><li><b>Tu cuenta asociada a Yape está bloqueada.</b> No se pudo realizar el pago. Comunícate con Yape por WhatsApp al 939 339 299 para brindarte una solución.</li></ul></td></tr> 
    <tr><td>Error por timeout en el proceso de transferencia</td><td><ul><li><b>Ocurrió un inconveniente.</b> Estamos poniendo manos a la obra. Por favor, vuelve a intentarlo en unos minutos.</li></ul></td></tr>
    <tr><td>Error por cuenta yapera no encontrada</td><td><ul><li><b>Ocurrió un inconveniente.</b> Comunícate con Yape por WhatsApp al 939 339 299 para brindarte más información.</li></ul></td></tr>
    <tr><td>Error por tarjeta BCP desactualizada</td><td><ul><li><b>Necesitas asociar tu nueva tarjeta BCP a Yape.</b> Ingresa al Centro de Ayuda de <a href=" www.yape.com.pe">www.yape.com.pe</a> y conoce los pasos para asociar tu nueva tarjeta y renovar tu cuenta.</li></ul></td></tr>
    <tr><td>Error por tarjeta BCP bloqueada</td><td><ul><li><b>Tu tarjeta asociada a Yape está bloqueada, necesitas una nueva.</b> Si ya tienes tu nueva tarjeta, ingresa al Centro de Ayuda de Yape <a href=" www.yape.com.pe">www.yape.com.pe</a> y conoce los pasos para renovar tu cuenta con tus mismos datos.</li></ul></td></tr>
    <tr><td>Error por tarjeta digital inválida</td><td><ul><li><b>Tu cuenta está bloqueada.</b> Si ya tienes tu nueva tarjeta, ingresa al Centro de Ayuda de Yape <a href=" www.yape.com.pe">www.yape.com.pe</a> y conoce los pasos para renovar tu cuenta con tus mismos datos.</li></ul></td></tr>
    <tr><td>Error por tarjeta BCP vencida</td><td><ul><li><b>Tu cuenta está vencida.</b> Si ya tienes tu nueva tarjeta, ingresa al Centro de Ayuda de Yape <a href=" www.yape.com.pe">www.yape.com.pe</a> y conoce los pasos para renovar tu cuenta. De no tenerla, acude a una agencia BCP y solicita una nueva para renovar tu cuenta.</li></ul></td></tr>
    <tr><td>Error por cuenta bancaria cerrada</td><td><ul><li><b>Tu cuenta asociada a Yape está cerrada.</b> No se pudo realizar el pago. Comunícate con Yape por Whatsapp al 939 339 299 para brindarte una solución.</li></ul></td></tr>
    <tr><td>Error inesperado ocurrido en el servidor</td><td><ul><li><b>Ocurrió un inconveniente. </b> Estamos poniendo manos a la obra. Por favor, vuelve a intentarlo en unos minutos</li></ul></td></tr>
  </tbody>
</table>
`}</HTMLBlock>

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

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Motivo</b></th>
      <th><b>Acción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Error por cuenta yapera no encontrada</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
    <tr><td>Error por operación de cargo no encontrado</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
    <tr><td>Error por plazo vencido para solicitar una devolución</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
    <tr><td>Error en monto de devolución</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
    <tr><td>Error por cuenta bancaria cerrada</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
		<tr><td>Error inesperado ocurrido en el servidor</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

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
    * 📥 Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu *front-end*. Puedes [descargarlos aquí](https://prontopagalatam-my.sharepoint.com/:u:/g/personal/tahbet_reategui_prontopaga_com/EWC1ijJHq5JKnjpIH9qH0ncB42rHOzcbXWdiOlyQQHciCA?e=3taLCb\&download=1).
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
