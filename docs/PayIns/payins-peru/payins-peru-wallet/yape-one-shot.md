---
title: 'Botón Yape: One Shot'
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: 'Botón Yape: One Shot | ProntoPaga Docs'
  description: >-
    Yape One Shot is a new Yape feature that enables fast, one-time payments
    without the need to enter banking details, making online purchases
    easier—especially on high volume platforms. You can easily add this feature
    to your business through the Prontopaga API.
  image: >-
    https://files.readme.io/6cf8fa82009efa654a9fafab2e0bafd7aec2c4d9997dea115205a5863f577f30-Prontopaga_logotipo.png
  keywords:
    - Yape One Shot payment Peru
    - ProntoPaga API
    - integrate Yape
    - pay with Yape
    - One Shot integration Peru
    - Yape One Shot
    - wallet checkout Peru
    - pagar con Yape Perú
    - integrar Yape One Shot Perú
  robots: index
next:
  description: ''
---
Crear un pago con **Botón Yape: One Shot** en Perú consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un Bearer Token y una secretKey. Esta solicitud podrá realizarse tanto para versión web, como para versión mobile. Además, el flujo de pago del cliente también varía ligeramente, dependiendo del dispositivo que esté usando.

***

## ¿Cómo funciona?

Yape es una aplicación que permite realizar pagos y transferencias de dinero en Perú, utilizando solo el número de celular. Con Yape, los usuarios pueden hacer pagos en línea, recargar saldo en su cuenta o realizar compras en comercios afiliados. Para completar una transacción utilizando este método de pago, el cliente debe seleccionar la opción "Paga con Yape", tener una cuenta creada y aprobar la compra desde su aplicación.

El proceso de pago con wallet en Perú consta de las siguientes etapas:

<Image align="center" border={false} src="https://files.readme.io/efce1e62affd017683ff5f4c5d7d37aeaa0ac61be005cfb70327fc48a99f1f7d-oneShot.jpg" />

1. **Selección de método.** Durante el checkout, el cliente elige pagar con Yape en tu sitio web o aplicación.
2. **Solicitud.** ProntoPaga se comunica con la wallet y genera la solicitud de pago.
3. **Aprobación.** El flujo de aprobación del pago varía según el dispositivo del cliente y si tu comercio tiene o no activado el servicio de validación de pago de terceros:

**🌐 En web:**

<Cards columns={2}>
  <Card title="Si se tiene desactivado el servicio de validación pago de terceros">
    Se le pide al cliente ingresar su número de celular para solicitar el pago. Luego se le muestra en pantalla un instructivo para abrir su aplicación y aprobar el pago en la sección de **Aprobar compras**.
  </Card>

  <Card title="Si se tiene activado el servicio de validación pago de terceros">
    Se le pide al cliente confirmar su número de celular para solicitar el pago. Si los datos no coinciden, se le muestra un mensaje de error. Si los datos coinciden, se le manda la solicitud directamente a su aplicación de Yape (por notificación y correo). El cliente ingresa, ve en pantalla las solicitudes por aprobar, selecciona la indicada y hace clic en **Confirmar**.
  </Card>
</Cards>

**📱En mobile:**

<Cards columns={2}>
  <Card title="Si se tiene desactivado el servicio de validación pago de terceros">
    Se le pide al cliente ingresar su número de celular para solicitar el pago. Luego se le muestra en pantalla un instructivo para abrir su aplicación y aprobar el pago en la sección de **Aprobar compras**.
  </Card>

  <Card title="Si se tiene activado el servicio de validación pago de terceros">
    Se le pide al cliente confirmar su número de celular para solicitar el pago. Si los datos no coinciden, se le muestra un mensaje de error. Si los datos coinciden, se le manda la solicitud directamente a su aplicación de Yape (por notificación y correo). El cliente ingresa, ve en pantalla las solicitudes por aprobar, selecciona la indicada y hace clic en **Confirmar**.
  </Card>
</Cards>

4. **Validación.** Se valida que la información sea correcta, se hace el pago y el dinero se mueve desde la wallet del cliente hacia la cuenta de tu comercio.
5. **Confirmación.** Se le informa el resultado de la transacción al cliente. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

***

<br />

## Versiones

Es posible integrar el servicio **Botón Yape: One Shot** de dos maneras:

* **Versión web.**
* **Versión mobile.**

A continuación, verás las instrucciones para la versión web. Más abajo, dentro de esta misma página, verás los pasos para la versión mobile. Para una navegación más rápida, te sugerimos usar el índice de la derecha.

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

El front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

<br />

### Crea un nuevo pago

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `yape_oneshot_payment` como método de pago en el body de la solicitud. Además, deberás especificar en el parámetro `origin` que se trata de un pago de tipo `web`.

La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, monto, entre otros.

<NotaFirma />

<br />

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la [solicitud de pago](https://docs.prontopaga.com/reference/create-payment).

```json
{
  "currency": "PEN",
  "country": "PE",
  "amount": "100.90",
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "12345678912",
  "paymentMethod": "yape_oneshot_payment",
  "urlConfirmation": "https://www.webhook.com",
  "urlFinal": "https://www.webhook.com",
  "urlRejected": "https://www.webhook.com",
  "order": "XYZ789",
  "origin": "web",
  "sign": "Signature of the parameters"
}
```

> 🚧 Límite transaccional
>
> Recuerda que el límite máximo por transacción y por día es de 2000 soles. Esto significa que, si un cliente realiza hoy una compra por ese monto, no podrá hacer otra transacción hasta mañana.

<br />

### Confirmación de un pago

Una vez que el usuario haya completado el pago, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

> 📘 Notificación del estado de la transacción
>
> Para configurar el webhook que irá en el campo `urlConfirmation` y recibir notificaciones con el estado de tu transacción, revisa [este artículo](https://docs.prontopaga.com/docs/webhooks).

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los PayIns](https://docs.prontopaga.com/docs/payins-status).

### Motivos de rechazo de un pago

A continuación, se listan los posibles motivos de rechazo para un pago de tipo One Shot, así como los mensajes que se muestran en pantalla a tu cliente.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Código</b></th>
      <th><b>Descripción</b></th>
			<th><b>Mensaje mostrado en el app Yape</b></th>
    </tr>
  </thead>
  <tbody>    
		<tr><td><code>YPTRX000</code></td><td>Confirmación de transacción exitosa</td><td><b>Yape notifica transacción exitosa por push y email</b></td></tr>
    <tr><td><code>YPCOCE0001</code></td><td>Consentimiento expirado o no encontrado</td><<td><b>La solicitud ha expirado. </b>Regresa al comercio y vuelve a solicitar la aprobación de yapeo.</td></tr>
    <tr><td><code>YPCOCE0002</code></td><td>Consentimiento en estado inválido</td><td><b>La solicitud ha expirado. </b>Regresa al comercio y vuelve a solicitar la aprobación de yapeo.</td></tr>
    <tr><td><code>YPCOCE0003</code></td><td>Error por tipo de cuenta no soportada</td><td><b>Tu tipo de cuenta Yape no está habilitada para esta funcionalidad.</b> Conoce tu tipo de cuenta ingresando al menú de Yape, opción Mi perfil</td></tr>
    <tr><td><code>YPCOCE0004</code></td><td>Error por cuenta yapera en blacklist</td><td><b>Por seguridad, tu cuenta fue bloqueada.</b> Comunícate con nosotros por WhatsApp para brindate más información.</td></tr>
    <tr><td><code>YPCOCE0005</code></td><td>Error por tarjeta BCP desactualizada</td><td><b>Necesitas asociar tu nueva tarjeta BCP a Yape.</b> Presiona "Ir a renovar cuenta" y sigue los pasos, colocando tus mismos datos.</td></tr>
    <tr><td><code>YPCOCE0006</code></td><td>Error por tarjeta BCP bloqueada</td><td><b>Tu tarjeta está bloqueada, necesitas una nueva.</b> Si ya tienes tu tarjeta, presionar en "<b>Ir a renovar cuenta</b>" e ingresa tus mismos datos. De no tenerla, acude a una agencia BCP y solicita una nueva tarjeta para renovar tu cuenta.</td></tr>
    <tr><td><code>YPCOCE0007</code></td><td>Error por tarjeta BCP vencida</td><td><b>Tu tarjeta está vencida, necesitas una nueva.</b> Si ya tienes tu tarjeta, presionar en "<b>Ir a renovar cuenta</b>" e ingresa tus mismos datos. De no tenerla, acude a una agencia BCP y solicita una nueva tarjeta para renovar tu cuenta.</td></tr>
    <tr><td><code>YPCOCE0008</code></td><td>Error por tarjeta digital bloqueada</td><td><b>Tu cuenta está bloquedada.</b> Es necesario eliminar tu Yape y crear una cuenta nueva. Si tienes saldo, acude a una agencia BCP con tu DNI para retirarlo.</td></tr>
<tr><td><code>YPCOCE0009</code></td><td>Error por tarjeta digital vencida</td><td><b>Tu cuenta está bloquedada.</b> Es necesario eliminar tu Yape y crear una cuenta nueva. Si tienes saldo, acude a una agencia BCP con tu DNI para retirarlo.</td></tr>
    <tr><td><code>YPCOCE0010</code></td><td>Error por límite de compras excedido</td><td><b>No se pudo realizar tu compra por internet con Yape.</b> Inténtalo nuevamente.</td><td><b>Esta operación excede tu monto límite diario para compras por internet.</b> Superaste el límite diario de S/2000. Vuelve a intentarlo el día de mañana.</td></tr>
    <tr><td><code>YPCOCE0021</code></td><td>Bloqueo de 24 horas por OTP incorrecto (tercer intento)</td><td><b>No se pudo realizar tu compra por internet con Yape.</b> Inténtalo nuevamente.</td><td><b>Usaste todos tus intentos.</b> Por tu seguridad, no podrás hacer compras por internet con Yape durante 24 horas. Las demás funciones siguen disponibles.</td></tr>
    <tr><td><code>YPTRX001</code></td><td>Error por autorización detectada como fraude</td><td><b>Encontramos restricciones para completar tu yapeo.</b> Por favor, comunícate con el BCP al (01) 311 9898 anexo *911 para brindarte una solución.</td><td>N/A</td></tr>
    <tr><td><code>YPTRX002</code></td><td>Error por fondos insuficientes</td><td><b>Necesitas más saldo para esta compra</b></td><td>N/A</td></tr>
    <tr><td><code>YPTRX003</code></td><td>Error por cuenta bancaria bloqueada</td><td><b>Tu cuenta asociada a Yape está bloqueada.</b> No se pudo realizar el pago. Comunícate con Yape por WhatsApp al 939 339 299 para brindarte una solución.</td><td>N/A</td></tr>
    <tr><td><code>YPTRX004</code></td><td>Error por timeout en el proceso de transferencia</td><td><b>No se pudo realizar tu compra por internet con Yape.</b> Inténtalo nuevamente.</td><td>N/A</td></tr>
    <tr><td><code>YPTRX013</code></td><td>Error por cuenta bancaria cerrada</td><td><b>Tu cuenta asociada a Yape está cerrada.</b> No se pudo realizar el pago. Comunícate con Yape por WhatsApp al 939 339 299 para brindarte una solución.</td><td>N/A</td></tr>
    <tr><td><code>YPTRX999</code></td><td>Error inesperado ocurrido en el servidor</td><td><b>No se pudo realizar tu compra por internet con Yape.</b> Inténtalo nuevamente.</td><td>N/A</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

<br />

### Devolución de un pago

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

### Motivos de rechazo de una devolución de pago

A continuación, se listan los posibles motivos de rechazo para una devolución de pago de tipo One Shot, así como los mensajes que se muestran en pantalla a tu cliente.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Código</b></th>
      <th><b>Descripción</b></th>
      <th><b>Mensaje para mosrtar recomendado</b></th>
			<th><b>Mensaje mostrado en el app Yape</b></th>
    </tr>
  </thead>
  <tbody>    
		<tr><td><code>YPTRX000</code></td><td>Confirmación de transacción exitosa</td><td><b>Mostrar pantalla de win state.</b></td><td><b>Yape notifica transacción exitosa por push y email</b></td></tr>
    <tr><td><code>YPCOCE0001</code></td><td>Consentimiento expirado o no encontrado</td><td><b>No se pudo realizar tu compra por internet con Yape.</b> Inténtalo nuevamente.</td><td><b>La solicitud ha expirado. </b>Regresa al comercio y vuelve a solicitar la aprobación de yapeo.</td></tr>
    <tr><td><code>YPCOCE0002</code></td><td>Consentimiento en estado inválido</td><td><b>No se pudo realizar tu compra por internet con Yape.</b> Inténtalo nuevamente.</td><td><b>La solicitud ha expirado. </b>Regresa al comercio y vuelve a solicitar la aprobación de yapeo.</td></tr>
    <tr><td><code>YPCOCE0003</code></td><td>Error por tipo de cuenta no soportada</td><td><b>No se pudo realizar tu compra por internet con Yape.</b> Inténtalo nuevamente.</td><td><b>Tu tipo de cuenta Yape no está habilitada para esta funcionalidad.</b> Conoce tu tipo de cuenta ingresando al menú de Yape, opción Mi perfil</td></tr>
    <tr><td><code>YPCOCE0004</code></td><td>Error por cuenta yapera en blacklist</td><td><b>No se pudo realizar tu compra por internet con Yape.</b> Inténtalo nuevamente.</td><td><b>Por seguridad, tu cuenta fue bloqueada.</b> Comunícate con nosotros por WhatsApp para brindate más información.</td></tr>
    <tr><td><code>YPCOCE0005</code></td><td>Error por tarjeta BCP desactualizada</td><td><b>No se pudo realizar tu compra por internet con Yape.</b> Inténtalo nuevamente.</td><td><b>Necesitas asociar tu nueva tarjeta BCP a Yape.</b> Presiona "Ir a renovar cuenta" y sigue los pasos, colocando tus mismos datos.</td></tr>
    <tr><td><code>YPCOCE0006</code></td><td>Error por tarjeta BCP bloqueada</td><td><b>No se pudo realizar tu compra por internet con Yape.</b> Inténtalo nuevamente.</td><td><b>Tu tarjeta está bloqueada, necesitas una nueva.</b> Si ya tienes tu tarjeta, presionar en "<b>Ir a renovar cuenta</b>" e ingresa tus mismos datos. De no tenerla, acude a una agencia BCP y solicita una nueva tarjeta para renovar tu cuenta.</td></tr>
    <tr><td><code>YPCOCE0007</code></td><td>Error por tarjeta BCP vencida</td><td><b>No se pudo realizar tu compra por internet con Yape.</b> Inténtalo nuevamente.</td><td><b>Tu tarjeta está vencida, necesitas una nueva.</b> Si ya tienes tu tarjeta, presionar en "<b>Ir a renovar cuenta</b>" e ingresa tus mismos datos. De no tenerla, acude a una agencia BCP y solicita una nueva tarjeta para renovar tu cuenta.</td></tr>
    <tr><td><code>YPCOCE0008</code></td><td>Error por tarjeta digital bloqueada</td><td><b>No se pudo realizar tu compra por internet con Yape.</b> Inténtalo nuevamente.</td><td><b>Tu cuenta está bloquedada.</b> Es necesario eliminar tu Yape y crear una cuenta nueva. Si tienes saldo, acude a una agencia BCP con tu DNI para retirarlo.</td></tr>
    <tr><td><code>YPCOCE0009</code></td><td>Error por tarjeta digital vencida</td><td><b>No se pudo realizar tu compra por internet con Yape.</b> Inténtalo nuevamente.</td><td><b>Tu cuenta está bloquedada.</b> Es necesario eliminar tu Yape y crear una cuenta nueva. Si tienes saldo, acude a una agencia BCP con tu DNI para retirarlo.</td></tr>
    <tr><td><code>YPCOCE0010</code></td><td>Error por límite de compras excedido</td><td><b>No se pudo realizar tu compra por internet con Yape.</b> Inténtalo nuevamente.</td><td><b>Esta operación excede tu monto límite diario para compras por internet.</b> Superaste el límite diario de S/2000. Vuelve a intentarlo el día de mañana.</td></tr>
    <tr><td><code>YPCOCE0021</code></td><td>Bloqueo de 24 horas por OTP incorrecto (tercer intento)</td><td><b>No se pudo realizar tu compra por internet con Yape.</b> Inténtalo nuevamente.</td><td><b>Usaste todos tus intentos.</b> Por tu seguridad, no podrás hacer compras por internet con Yape durante 24 horas. Las demás funciones siguen disponibles.</td></tr>
    <tr><td><code>YPTRX001</code></td><td>Error por autorización detectada como fraude</td><td><b>Encontramos restricciones para completar tu yapeo.</b> Por favor, comunícate con el BCP al (01) 311 9898 anexo *911 para brindarte una solución.</td><td>N/A</td></tr>
    <tr><td><code>YPTRX002</code></td><td>Error por fondos insuficientes</td><td><b>Necesitas más saldo para esta compra</b></td><td>N/A</td></tr>
    <tr><td><code>YPTRX003</code></td><td>Error por cuenta bancaria bloqueada</td><td><b>Tu cuenta asociada a Yape está bloqueada.</b> No se pudo realizar el pago. Comunícate con Yape por WhatsApp al 939 339 299 para brindarte una solución.</td><td>N/A</td></tr>
    <tr><td><code>YPTRX004</code></td><td>Error por timeout en el proceso de transferencia</td><td><b>No se pudo realizar tu compra por internet con Yape.</b> Inténtalo nuevamente.</td><td>N/A</td></tr>
    <tr><td><code>YPTRX013</code></td><td>Error por cuenta bancaria cerrada</td><td><b>Tu cuenta asociada a Yape está cerrada.</b> No se pudo realizar el pago. Comunícate con Yape por WhatsApp al 939 339 299 para brindarte una solución.</td><td>N/A</td></tr>
    <tr><td><code>YPTRX999</code></td><td>Error inesperado ocurrido en el servidor</td><td><b>No se pudo realizar tu compra por internet con Yape.</b> Inténtalo nuevamente.</td><td>N/A</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

***

<br />

## Integra la versión mobile

El front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

<br />

### Crea un nuevo pago

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `yape_oneshot_payment` como método de pago en el body de la solicitud. Además, deberás especificar en el parámetro `origin` que se trata de un pago de tipo `mobile`.

La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, monto, entre otros.

<NotaFirma />

<br />

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la [solicitud de pago](https://docs.prontopaga.com/reference/create-payment).

```json
{
  "currency": "PEN",
  "country": "PE",
  "amount": "100.90",
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "12345678912",
  "paymentMethod": "yape_oneshot_payment",
  "urlConfirmation": "https://www.webhook.com",
  "urlFinal": "https://www.webhook.com",
  "urlRejected": "https://www.webhook.com",
  "order": "XYZ789",
  "origin": "mobile",
  "sign": "Signature of the parameters"
}
```

> 🚧 Límite transaccional
>
> Recuerda que el límite máximo por transacción y por día es de 2000 soles. Esto significa que, si un cliente realiza hoy una compra por ese monto, no podrá hacer otra transacción hasta mañana.

<br />

### Confirmación de un pago

Una vez que el usuario haya completado el pago, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

> 📘 Notificación del estado de la transacción
>
> Para configurar el webhook que irá en el campo `urlConfirmation` y recibir notificaciones con el estado de tu transacción, revisa [este artículo](https://docs.prontopaga.com/docs/webhooks).

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los PayIns](https://docs.prontopaga.com/docs/payins-status).

***

## Prueba tu integración

Contamos con demos que simulan la experiencia de pago del cliente, en donde podrás hacer pruebas. Conócelos aquí:

<Embed url="https://experience.prontopaga.com/" href="https://experience.prontopaga.com/" typeOfEmbed="iframe" height="1000px" width="100%" iframe="true" html="false" />

***

## Certifica tu integración

La certificación de la integración en _sandbox_ es un paso obligatorio que todos los comercios deben realizar antes de recibir sus credenciales de producción. Su propósito es asegurar que la integración cumpla con los estándares técnicos, funcionales y de seguridad requeridos por ProntoPaga. Dentro de esta sección, se establecen los requisitos que deben cumplirse sin excepción para que la certificación sea aprobada.

### Requisitos de certificación

A continuación, encontrarás los distintos requisitos necesarios para completar tu certificación:

<Tabs>
  <Tab title="ID del cliente">
    * ❌ El documento de identidad del cliente no debe ser modificable en ningún punto de la transacción.
    * ✅ Es recomendable que este dato no se muestre en el *checkout*. Solo puede estar disponible en la sección de perfil del usuario autenticado.
    * ⚠️ Esta medida tiene como objetivo prevenir fraudes y evitar que se realicen transacciones en nombre de terceros o menores de edad.
  </Tab>

  <Tab title="Logotipos">
    * 📥 Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu *front-end*. Puedes [descargarlos aquí](https://prontopagalatam-my.sharepoint.com/:f:/g/personal/tahbet_reategui_prontopaga_com/EtPhXrMz3TxAtA11de5jVZEB3yowkpS1i2v6lm_eMKkB7g?e=KXcZX5).
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
