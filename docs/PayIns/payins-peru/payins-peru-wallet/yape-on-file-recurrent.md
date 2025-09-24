---
title: 'Yape On File: Recurrencia'
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: 'Yape On File: Recurrencia | ProntoPaga Docs'
  description: >-
    Recurring Payments allow you to automatically schedule and collect recurring
    payments from customers who authorize them once through the Yape app. After
    successful affiliation via the ProntoPaga API, your system can trigger
    charges to the customer’s Yape wallet without requiring manual confirmation
    each time. The process includes affiliation, payment execution, and
    webhook-based confirmations. 
  image: >-
    https://files.readme.io/8d3b34d145d77ca2df24ad97a29e089b3111b9a4e965c5b4541bceedc1a95d21-Prontopaga_logotipo.png
  keywords:
    - Yape On File Prontopaga
    - recurring payments Yape
    - automatic payments Yape
    - API recurring billing
    - wallet recurring integration
    - charge automation Peru
    - Yape COF
    - suscribirse a Yape
    - integrar yape
    - pagos recurrentes Yape
    - afiliarse a Yape
    - recurrencia Yape
  robots: index
next:
  description: ''
---
Crear pagos recurrentes con Yape On File consiste en hacer una solicitud de afiliación a través de nuestra API. Esta solicitud podrá realizarse tanto para versión web, como para versión mobile. Una vez realizada con éxito la afiliación, podrás llamar a nuestro endpoint de pagos para realizar los cargos a su cuenta de Yape, según lo requieras.

***

## ¿Cómo funciona?

Yape es una aplicación que permite realizar pagos y transferencias de dinero en Perú, utilizando solo el número de celular. Con Yape, los usuarios pueden hacer pagos en línea, recargar saldo en su cuenta o realizar compras en comercios afiliados. Para completar una transacción utilizando este método de pago, el cliente debe seleccionar a Yape como método de pago, tener una cuenta creada y aprobar la suscripción desde su aplicación.

El proceso de pago con **Yape On File: Recurrencia** en Perú consta de las siguientes etapas:

<Image align="center" border={false} src="https://files.readme.io/cbf7e2d3364a3dcfccbde9d3cdbcfb05b15e771ece8e66ba778cf4292d765bff-oneClick-recurrencia_1.jpg" />

1. **Selección de método.** Durante el checkout de un pago de suscripción, el cliente selecciona a Yape como método de pago en tu sitio web o aplicación. La siguiente parte del flujo varía según el dispositivo del cliente y si tu comercio tiene o no activado el servicio de validación de pago de terceros:

**🌐 En web:**

<Cards columns={2}>
  <Card title="Si se tiene desactivado el servicio de validación pago de terceros">
    Se le pide al cliente ingresar su número de celular y hacer clic en el botón de "Solicitar aprobación". Luego se le muestran en pantalla instrucciones para abrir su aplicación de Yape, ir a **Aprobar compras > Solicitudes por aprobar**, seleccionar la indicada y hacer clic en **Aprobar afiliación**.
  </Card>

  <Card title="Si se tiene activado el servicio de validación pago de terceros">
    Se le pide al cliente confirmar su número de celular y hacer clic en el botón de "Solicitar aprobación". Si los datos no coinciden, se le muestra un mensaje de error. Si los datos coinciden, se le manda la solicitud directamente a su aplicación de Yape (por notificación y correo). El cliente ingresa, ve en pantalla las solicitudes por aprobar, selecciona la indicada y hace clic en **Confirmar afiliación**.
  </Card>
</Cards>

**📱En mobile:**

<Cards columns={2}>
  <Card title="Si se tiene desactivado el servicio de validación pago de terceros">
    El cliente debe hacer clic en el botón de "Solicitar aprobación". Luego, será redirigido a la aplicación de Yape mediante un deeplink. Después de ingresar su clave de acceso, aparecerá un modal en la pantalla, donde podrá aprobar la afiliación directamente.
  </Card>

  <Card title="Si se tiene activado el servicio de validación pago de terceros">
    Se le pide al cliente confirmar su número de celular y hacer clic en el botón de "Solicitar aprobación". Si los datos no coinciden, se le muestra un mensaje de error. Si los datos coinciden, el cliente debe hacer clic en el botón de "Abrir Yape" para ser redirigido a la aplicación. El cliente ingresa, ve en pantalla las solicitudes por aprobar, selecciona la indicada y hace clic en **Confirmar afiliación**. Para dispositivos móviles, se debe agregar un deeplink de Yape. Este deeplink redirecciona automáticamente al usuario a la sección de "Código de aprobación" de su aplicación de Yape. La URL del deeplink es: `https://www.yape.com.pe/app/checkout/approval_code`.
  </Card>
</Cards>

2. **Confirmación de la afiliación.** Se hace la afiliación, la pantalla de tu comercio se actualiza y se muestra el resultado de la transacción. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.
3. **Recurrencia.** Ahora podrás llamar a nuestro endpoint de cobro de pago para realizar los cargos a su cuenta de Yape, cada vez que lo requieras (según los detalles especificados por el cliente y por tu comercio, sobre su plan de suscripción).
4. **Confirmación de pago recurrente** Tu cliente recibirá notificaciones push en su wallet cada vez que se realice un pago recurrente. A su vez, tu comercio recibirá la confirmación a través de los webhooks que hayas configurado.

***

<br />

## Versiones

Es posible integrar el servicio **Yape On File: Recurrencia** de dos maneras:

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

El front-end será el encargado de recopilar los datos necesarios de tu cliente para comenzar el proceso de suscripción, mientras que tu back-end estará integrado con nuestra API, procesando la afiliación y los pagos.

<br />

### Crea una afiliación de tipo Recurrencia

Para crear una solicitud de afiliación de tipo Recurrencia, deberás usar [este endpoint](https://docs.prontopaga.com/reference/affiliations) y enviar un body request con los datos necesarios. A continuación, puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "origin": "WEB",
  "document": "12345678",
  "phoneNumber": "999999999",
  "webhookUrl": "https://www.webhook.com",
  "type": "RECURRENT",
  "clientName": "John Doe",
  "clientDocumentType": "PP"
}
```

Si la afiliación se realizó con éxito, se mostrará el resultado de la transacción en pantalla. A su vez, tu comercio recibirá la confirmación a través de los webhooks que hayas configurado.

> 🚧 Tiempo de expiración
>
> El cliente debe aprobar la afiliación en menos de 15 minutos. En caso de no hacerse, la afiliación expirará a los 15 minutos.

<br />

### Haz un pago recurrente

Una vez que tu cliente esté afiliado correctamente, tu comercio podrá realizar los pagos según lo requiera. Para solicitar un pago, deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `yape_cof_payment` como método de pago en el body de la solicitud, así como agregar el identificador único (UID) de la afiliación de la wallet del cliente en el parámetro `walletUID`.

La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, monto, entre otros.

<NotaFirma />

#### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la [solicitud de pago recurrente](https://docs.prontopaga.com/reference/create-payment):

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
  "walletUID": "01JXNCAK8TX6PNBBN7ZNBSAEJH",
  "sign": "Signature of the parameters"
}
```

> 🚧 Límite transaccional
>
> Recuerda que el límite máximo por transacción y por día es de 2000 soles. Esto significa que, si un cliente realiza hoy una compra por ese monto, no podrá hacer otra transacción hasta mañana.

#### Confirmación de un pago

Una vez que se haya completado el pago, ProntoPaga le enviará al cliente una notificación push con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

> 📘 Notificación del estado de la transacción
>
> Para configurar el webhook que irá en el campo `urlConfirmation` y recibir notificaciones con el estado de tu transacción, revisa [este artículo](https://docs.prontopaga.com/docs/webhooks).

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los PayIns](https://docs.prontopaga.com/docs/payins-status).

<br />

### Motivos de rechazo de un pago

A continuación, se listan los posibles motivos de rechazo para un pago de tipo Recurrencia, así como las acciones de Yape al respecto.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Motivo</b></th>
      <th><b>Acción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Error por suscripción confirmada no existente</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
    <tr><td>Error por no coincidencia del código de comercio de la suscripción</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
    <tr><td>Error por monto máximo por compra excedido</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
    <tr><td>Error por autorización detectada como fraude</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
    <tr><td>Error por fondos insuficientes</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
    <tr><td>Error por cuenta bancaria bloqueada</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
		<tr><td>Error por timeout en el proceso de transferencia</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
    <tr><td>Error por cuenta yapera no encontrada</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
    <tr><td>Error por cuenta bancaria cerrada</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
		<tr><td>Error inesperado ocurrido en el servidor</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

<br />

### Devolución de un pago de una Recurrencia

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

Puedes obtener una lista con las afiliaciones de tipo Recurrencia activas de cierto cliente, haciendo una consulta con su número de documento. Utiliza [este endpoint](https://docs.prontopaga.com/reference/affiliations-list) para ello.

<br />

### Detalle de una afiliación

Consulta el detalle del estado de una afiliación de tipo Recurrencia, usando el identificador único (UID) de la afiliación de la wallet del cliente. Utiliza [este endpoint](https://docs.prontopaga.com/reference/affiliation-details) para conocer el detalle.

<br />

### Cancelar una afiliación de tipo Recurrencia

Para cancelar la afiliación de un cliente, y que éste ya no reciba más cargos recurrentes, haz una solicitud a [este endpoint](https://docs.prontopaga.com/reference/affiliation-cancel).

Para ello, deberás enviar el identificador único (UID) de la afiliación de la wallet del cliente en el path. Una vez finalizado el proceso de cancelación de forma exitosa, el cliente recibirá una notificación push de Yape, confirmando el proceso.

***

<br />

## Integra la versión mobile

El front-end será el encargado de recopilar los datos necesarios de tu cliente para comenzar el proceso de suscripción, mientras que tu back-end estará integrado con nuestra API, procesando la afiliación y los pagos.

### Crea una afiliación de tipo Recurrencia

Para crear una solicitud de afiliación de tipo Recurrencia, deberás usar [este endpoint](https://docs.prontopaga.com/reference/affiliations) y enviar un body request con los datos necesarios. A continuación, puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "origin": "MOBILE",
  "document": "12345678",
  "webhookUrl": "https://www.webhook.com",
  "type": "RECURRENT",
  "clientName": "John Doe",
  "clientDocumentType": "PP"
}
```

Si la recurrencia se realizó con éxito, se mostrará el resultado de la transacción en pantalla. A su vez, tu comercio recibirá la confirmación a través de los webhooks que hayas configurado.

> 🚧 Tiempo de expiración
>
> El cliente debe aprobar la afiliación en menos de 15 minutos. En caso de no hacerse, la afiliación expirará a los 15 minutos.

<br />

### Haz un pago recurrente

Una vez que tu cliente esté afiliado correctamente, tu comercio podrá realizar los pagos según lo requiera. Para solicitar un pago, deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `yape_cof_payment` como método de pago en el body de la solicitud, así como agregar el identificador único (UID) de la afiliación de la wallet del cliente en el parámetro `walletUID`.

La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, monto, entre otros.

<NotaFirma />

<br />

#### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la [solicitud de pago recurrente](https://docs.prontopaga.com/reference/create-payment):

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
  "walletUID": "01JXNCAK8TX6PNBBN7ZNBSAEJH",
  "sign": "Signature of the parameters"
}
```

> 🚧 Límite transaccional
>
> Recuerda que el límite máximo por transacción y por día es de 2000 soles. Esto significa que, si un cliente realiza hoy una compra por ese monto, no podrá hacer otra transacción hasta mañana.

<br />

#### Confirmación de un pago

Una vez que se haya completado el pago, ProntoPaga le enviará al cliente una notificación push con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

> 📘 Notificación del estado de la transacción
>
> Para configurar el webhook que irá en el campo `urlConfirmation` y recibir notificaciones con el estado de tu transacción, revisa [este artículo](https://docs.prontopaga.com/docs/webhooks).

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los PayIns](https://docs.prontopaga.com/docs/payins-status).

<br />

### Motivos de rechazo de un pago

A continuación, se listan los posibles motivos de rechazo para un pago de tipo Recurrencia, así como las acciones de Yape al respecto.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Motivo</b></th>
      <th><b>Acción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Error por suscripción confirmada no existente</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
    <tr><td>Error por no coincidencia del código de comercio de la suscripción</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
    <tr><td>Error por monto máximo por compra excedido</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
    <tr><td>Error por autorización detectada como fraude</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
    <tr><td>Error por fondos insuficientes</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
    <tr><td>Error por cuenta bancaria bloqueada</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
		<tr><td>Error por timeout en el proceso de transferencia</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
    <tr><td>Error por cuenta yapera no encontrada</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
    <tr><td>Error por cuenta bancaria cerrada</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
		<tr><td>Error inesperado ocurrido en el servidor</td><td>Yape notifica sobre la transacción denegada por email</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

| Motivo                                                             | Acción                                                |
| :----------------------------------------------------------------- | :---------------------------------------------------- |
| Error por suscripción confirmada no existente                      | Yape notifica sobre la transacción denegada por email |
| Error por no coincidencia del código de comercio de la suscripción | Yape notifica sobre la transacción denegada por email |
| Error por monto máximo por compra excedido                         | Yape notifica sobre la transacción denegada por email |
| Error por autorización detectada como fraude                       | Yape notifica sobre la transacción denegada por email |
| Error por fondos insuficientes                                     | Yape notifica sobre la transacción denegada por email |
| Error por cuenta bancaria bloqueada                                | Yape notifica sobre la transacción denegada por email |
| Error por timeout en el proceso de transferencia                   | Yape notifica sobre la transacción denegada por email |
| Error por cuenta yapera no encontrada                              | Yape notifica sobre la transacción denegada por email |
| Error por cuenta bancaria cerrada                                  | Yape notifica sobre la transacción denegada por email |
| Error inesperado ocurrido en el servidor                           | Yape notifica sobre la transacción denegada por email |

<br />

### Devolución de un pago de una Recurrencia

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

Puedes obtener una lista con las afiliaciones de tipo Recurrencia activas de cierto cliente, haciendo una consulta con su número de documento. Utiliza [este endpoint](https://docs.prontopaga.com/reference/affiliations-list) para ello.

<br />

### Detalle de una afiliación

Consulta el detalle del estado de una afiliación de tipo Recurrencia, usando el identificador único (UID) de la afiliación de la wallet del cliente. Utiliza [este endpoint](https://docs.prontopaga.com/reference/affiliation-details) para conocer el detalle.

<br />

### Cancelar una afiliación de tipo Recurrencia

Para cancelar la afiliación de un cliente, y que éste ya no reciba más cargos recurrentes, haz una solicitud a [este endpoint](https://docs.prontopaga.com/reference/affiliation-cancel).

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
