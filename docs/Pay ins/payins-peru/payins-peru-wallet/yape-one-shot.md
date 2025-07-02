---
title: 'Botón Yape: One Shot'
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
Crear un pago con **Botón Yape: One Shot** en Perú consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un Bearer Token y una secretKey. Esta solicitud podrá realizarse tanto para versión web, como para versión mobile. Además, el flujo de pago del cliente también varía ligeramente, dependiendo del dispositivo que esté usando.

## ¿Cómo funciona?

Yape es una aplicación que permite realizar pagos y transferencias de dinero en Perú, utilizando solo el número de celular. Con Yape, los usuarios pueden hacer pagos en línea, recargar saldo en su cuenta o realizar compras en comercios afiliados. Para completar una transacción utilizando este método de pago, el cliente debe seleccionar la opción "Paga con Yape", tener una cuenta creada y aprobar la compra desde su aplicación.

El proceso de pago con wallet en Perú consta de cinco etapas principales:

1. **Selección de método.** Durante el checkout, el cliente elige pagar con Yape en tu sitio web o aplicación.
2. **Solicitud.** ProntoPaga se comunica con la wallet y genera la solicitud de pago.
3. **Aprobación.** El flujo de aprobación del pago depende del dispositivo que esté usando el cliente:
   1. En web: Se le pide al cliente ingresar su número de celular para solicitar el pago. Luego se le muestra en pantalla un instructivo para abrir su aplicación y aprobar el pago en la sección de "Aprobar compras". Además, se rellena en automático el código de validación.
   2. En mobile: El cliente ve el botón de "Abrir Yape", el cual lo redireccionará a la aprobación del pago en su aplicación. Además, se rellena en automático el código de validación.
4. **Validación.** Se valida que la información sea correcta, se hace el pago y el dinero se mueve desde la wallet del cliente hacia la cuenta de tu comercio.
5. **Confirmación.** Se le informa el resultado de la transacción al cliente. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

## Versiones

Es posible integrar el servicio **Botón Yape: One Shot** de dos maneras:

* **Versión web.**
* **Versión mobile.**

A continuación, verás las instrucciones para la versión web. Más abajo, dentro de esta misma página, verás los pasos para la versión mobile. Para una navegación más rápida, te sugerimos usar el índice de la derecha.

***

## Integra la versión web

El front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

### Crea un nuevo pago

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `yape_oneshot_payment` como método de pago en el body de la solicitud. Además, deberás especificar en el parámetro `origin` que se trata de un pago de tipo `web`.

La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, monto, entre otros.

<NotaFirma />

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la [solicitud de pago](https://docs.prontopaga.com/reference/create-payment).

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
  "paymentMethod": "yape_oneshot_payment",
  "urlConfirmation": "https://www.webhook.com",
  "order": "1234",
  "origin": "web",
  "sign": "Signature of the parameters"
}
```

> 🚧 Límite transaccional
>
> Recuerda que el límite máximo por transacción y por día es de 2000 soles. Esto significa que, si un cliente realiza hoy una compra por ese monto, no podrá hacer otra transacción hasta mañana.

#### Confirmación de un pago

Una vez que el usuario haya completado el pago, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

> 📘 Notificación del estado de la transacción
>
> Para configurar el webhook que irá en el campo `urlConfirmation` y recibir notificaciones con el estado de tu transacción, revisa [este artículo](https://docs.prontopaga.com/docs/webhooks).

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los pay ins](https://docs.prontopaga.com/docs/payins-status).

### Devolución de un pago

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

***

## Integra la versión mobile

El front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

### Crea un nuevo pago

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `yape_oneshot_payment` como método de pago en el body de la solicitud. Además, deberás especificar en el parámetro `origin` que se trata de un pago de tipo `mobile`.

La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, monto, entre otros.

<NotaFirma />

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la [solicitud de pago](https://docs.prontopaga.com/reference/create-payment).

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
  "paymentMethod": "yape_oneshot_payment",
  "urlConfirmation": "https://www.webhook.com",
  "order": "1234",
  "origin": "mobile",
  "sign": "Signature of the parameters"
}
```

> 🚧 Límite transaccional
>
> Recuerda que el límite máximo por transacción y por día es de 2000 soles. Esto significa que, si un cliente realiza hoy una compra por ese monto, no podrá hacer otra transacción hasta mañana.

#### Confirmación de un pago

Una vez que el usuario haya completado el pago, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

> 📘 Notificación del estado de la transacción
>
> Para configurar el webhook que irá en el campo `urlConfirmation` y recibir notificaciones con el estado de tu transacción, revisa [este artículo](https://docs.prontopaga.com/docs/webhooks).

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los pay ins](https://docs.prontopaga.com/docs/payins-status).

### Devolución de un pago

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