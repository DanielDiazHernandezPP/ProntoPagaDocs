---
title: 'Yape On File: Recurrencia'
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Crear pagos recurrentes con Yape On File consiste en hacer una solicitud de afiliación a través de nuestra API. Esta solicitud podrá realizarse tanto para versión web, como para versión mobile. Una vez realizada con éxito la afiliación, podrás llamar a nuestro endpoint de pagos para realizar los cargos a su cuenta de Yape, según lo requieras.

## ¿Cómo funciona?

Yape es una aplicación que permite realizar pagos y transferencias de dinero en Perú, utilizando solo el número de celular. Con Yape, los usuarios pueden hacer pagos en línea, recargar saldo en su cuenta o realizar compras en comercios afiliados. Para completar una transacción utilizando este método de pago, el cliente debe seleccionar a Yape como método de pago, tener una cuenta creada y aprobar la suscripción desde su aplicación.

El proceso de pago con **Yape On File: Recurrencia** en Perú consta de seis etapas principales:

1. **Selección de método.** Durante el checkout de un pago de suscripción, el cliente selecciona a Yape como método de pago en tu sitio web o aplicación.
   1. En la versión web, se le pide al cliente ingresar su número de celular y hacer clic en el botón de solicitud de aprobación.
   2. En la versión mobile, el cliente debe hacer clic en el botón de solicitud de aprobación.
2. **Solicitud.** ProntoPaga se comunica con la wallet y genera la solicitud de suscripción.
3. **Aprobación.** El cliente accede a su aplicación de Yape, en donde hará el siguiente proceso:
   1. Autenticarse con su clave o Face ID.
   2. Dirigirse a **Aprobar compras > Solicitudes por aprobar.**
   3. Abrir la solicitud de tu comercio y hacer clic en **Aprobar afiliación.**
   4. Ingresar el código de validación.
4. **Validación y confirmación de la afiliación.** Se valida que el código sea correcto. En caso de serlo, se hace la afiliación, la pantalla de tu comercio se actualiza y se muestra el resultado de la transacción. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.
5. **Recurrencia.** Ahora podrás llamar a nuestro endpoint de cobro de pago para realizar los cargos a su cuenta de Yape, cada vez que lo requieras (según los detalles especificados por el cliente y por tu comercio, sobre su plan de suscripción).
6. **Confirmación de pago recurrente** Tu cliente recibirá notificaciones push en su wallet cada vez que se realice un pago recurrente. A su vez, tu comercio recibirá la confirmación a través de los webhooks que hayas configurado.

## Versiones

Es posible integrar el servicio **Yape On File: Recurrencia** de dos maneras:

* **Versión web.**
* **Versión mobile.**

A continuación, verás las instrucciones para la versión web. Más abajo, dentro de esta misma página, verás los pasos para la versión mobile. Para una navegación más rápida, te sugerimos usar el índice de la derecha.

***

## Integra la versión web

El front-end será el encargado de recopilar los datos necesarios de tu cliente para comenzar el proceso de suscripción, mientras que tu back-end estará integrado con nuestra API, procesando la afiliación y los pagos.

### Crea una afiliación de tipo Recurrencia

Para crear una solicitud de afiliación de tipo Recurrencia, deberás usar [este endpoint](https://docs.prontopaga.com/reference/affiliations) y enviar un body request con los datos necesarios. A continuación, puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "origin": "WEB",
  "document": "12345678",
  "phoneNumber": "999999999",
  "webhookUrl": "https://www.webhook.com",
  "type": "RECURRENT"
}
```

Si la afiliación se realizó con éxito, se mostrará el resultado de la transacción en pantalla. A su vez, tu comercio recibirá la confirmación a través de los webhooks que hayas configurado.

> 🚧 Tiempo de expiración
>
> El cliente debe aprobar la afiliación en menos de 15 minutos. En caso de no hacerse, la afiliación expirará a los 15 minutos.

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
  "amount": 100,
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "12345678912",
  "clientDocumentType": "PP",
  "paymentMethod": "yape_cof_payment",
  "urlConfirmation": "https://www.webhook.com",
  "order": "1234",
  "walletUID": "01JXNCAK8TX6PNBBN7ZNBSAEJH",
  "sign": "Signature of the parameters"
}
```

> 🚧 Límite transaccional
>
> Recuerda que el límite máximo por transacción y por día es de 2000 soles. Esto significa que, si un cliente realiza hoy una compra por ese monto, no podrá hacer otra transacción hasta mañana.

#### Validación de pago de terceros

Para activar el servicio de validación de pago de terceros, deberás solicitar de forma obligatoria el número de teléfono del cliente en el checkout de pago. Esta validación permite verificar que el número ingresado corresponde al titular de la cuenta Yape, previniendo así pagos de terceros y fortaleciendo la seguridad en las transacciones.

#### Confirmación de un pago

Una vez que se haya completado el pago, ProntoPaga le enviará al cliente una notificación push con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

> 📘 Notificación del estado de la transacción
>
> Para configurar el webhook que irá en el campo `urlConfirmation` y recibir notificaciones con el estado de tu transacción, revisa [este artículo](https://docs.prontopaga.com/docs/webhooks).

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los pay ins](https://docs.prontopaga.com/docs/payins-status).

### Motivos de rechazo de un pago

A continuación, se listan los posibles motivos de rechazo para un pago de tipo Recurrencia, así como las acciones de Yape al respecto.

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

### Devolución de un pago de una Recurrencia

Para solicitar la devolución de un pago exitoso realizado con este método, usa [este endpoint](https://docs.prontopaga.com/reference/refunds). A continuación, se muestra un ejemplo del body request que debe llevar:

```json
{
  "reference": "1111111111",
  "clientDocument": "12345678912",
  "amount": 300,
  "urlCallbackRefund": "https://www.webhook.com",
  "sign": "Signature of the parameters"
}
```

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

### Lista de afiliaciones

Puedes obtener una lista con las afiliaciones de tipo Recurrencia activas de cierto cliente, haciendo una consulta con su número de documento. Utiliza [este endpoint](https://docs.prontopaga.com/reference/affiliations-list) para ello.

### Detalle de una afiliación

Consulta el detalle del estado de una afiliación de tipo Recurrencia, usando el identificador único (UID) de la afiliación de la wallet del cliente. Utiliza [este endpoint](https://docs.prontopaga.com/reference/affiliation-details) para conocer el detalle.

### Cancelar una afiliación de tipo Recurrencia

Para cancelar la afiliación de un cliente, y que éste ya no reciba más cargos recurrentes, haz una solicitud a [este endpoint](https://docs.prontopaga.com/reference/affiliation-cancel).

Para ello, deberás enviar el identificador único (UID) de la afiliación de la wallet del cliente en el path. Una vez finalizado el proceso de cancelación de forma exitosa, el cliente recibirá una notificación push de Yape, confirmando el proceso.

***

## Integra la versión mobile

El front-end será el encargado de recopilar los datos necesarios de tu cliente para comenzar el proceso de suscripción, mientras que tu back-end estará integrado con nuestra API, procesando la afiliación y los pagos.

### Crea una afiliación de tipo Recurrencia

Para crear una solicitud de afiliación de tipo Recurrencia, deberás usar [este endpoint](https://docs.prontopaga.com/reference/affiliations) y enviar un body request con los datos necesarios. A continuación, puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "origin": "MOBILE",
  "document": "12345678",
  "webhookUrl": "https://www.webhook.com",
  "type": "RECURRENT"
}
```

Si la recurrencia se realizó con éxito, se mostrará el resultado de la transacción en pantalla. A su vez, tu comercio recibirá la confirmación a través de los webhooks que hayas configurado.

> 🚧 Tiempo de expiración
>
> El cliente debe aprobar la afiliación en menos de 15 minutos. En caso de no hacerse, la afiliación expirará a los 15 minutos.

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
  "amount": 100,
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "12345678912",
  "clientDocumentType": "PP",
  "paymentMethod": "yape_cof_payment",
  "urlConfirmation": "https://www.webhook.com",
  "order": "1234",
  "walletUID": "01JXNCAK8TX6PNBBN7ZNBSAEJH",
  "sign": "Signature of the parameters"
}
```

> 🚧 Límite transaccional
>
> Recuerda que el límite máximo por transacción y por día es de 2000 soles. Esto significa que, si un cliente realiza hoy una compra por ese monto, no podrá hacer otra transacción hasta mañana.

#### Validación de pago de terceros

Para activar el servicio de validación de pago de terceros, deberás solicitar de forma obligatoria el número de teléfono del cliente en el checkout de pago. Esta validación permite verificar que el número ingresado corresponde al titular de la cuenta Yape, previniendo así pagos de terceros y fortaleciendo la seguridad en las transacciones.

#### Confirmación de un pago

Una vez que se haya completado el pago, ProntoPaga le enviará al cliente una notificación push con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

> 📘 Notificación del estado de la transacción
>
> Para configurar el webhook que irá en el campo `urlConfirmation` y recibir notificaciones con el estado de tu transacción, revisa [este artículo](https://docs.prontopaga.com/docs/webhooks).

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los pay ins](https://docs.prontopaga.com/docs/payins-status).

### Motivos de rechazo de un pago

A continuación, se listan los posibles motivos de rechazo para un pago de tipo Recurrencia, así como las acciones de Yape al respecto.

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

### Devolución de un pago de una Recurrencia

Para solicitar la devolución de un pago exitoso realizado con este método, usa [este endpoint](https://docs.prontopaga.com/reference/refunds). A continuación, se muestra un ejemplo del body request que debe llevar:

```json
{
  "reference": "1111111111",
  "clientDocument": "12345678912",
  "amount": 300,
  "urlCallbackRefund": "https://www.webhook.com",
  "sign": "Signature of the parameters"
}
```

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

### Lista de afiliaciones

Puedes obtener una lista con las afiliaciones de tipo Recurrencia activas de cierto cliente, haciendo una consulta con su número de documento. Utiliza [este endpoint](https://docs.prontopaga.com/reference/affiliations-list) para ello.

### Detalle de una afiliación

Consulta el detalle del estado de una afiliación de tipo Recurrencia, usando el identificador único (UID) de la afiliación de la wallet del cliente. Utiliza [este endpoint](https://docs.prontopaga.com/reference/affiliation-details) para conocer el detalle.

### Cancelar una afiliación de tipo Recurrencia

Para cancelar la afiliación de un cliente, y que éste ya no reciba más cargos recurrentes, haz una solicitud a [este endpoint](https://docs.prontopaga.com/reference/affiliation-cancel).

Para ello, deberás enviar el identificador único (UID) de la afiliación de la wallet del cliente en el path. Una vez finalizado el proceso de cancelación de forma exitosa, el cliente recibirá una notificación push de Yape, confirmando el proceso.