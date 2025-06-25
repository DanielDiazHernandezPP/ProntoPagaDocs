---
title: Tarjeta
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    To create a payment in Chile with Webpay, customer data must be captured and
    a request made through the ProntoPaga API using a bearer token and a secret
    signature. The front-end collects the customer data and the back-end
    processes the payment, confirming the status of the transaction through
    webhooks.
  keywords:
    - webpay
    - ' card'
    - ' card payment'
    - ' chile'
    - ' payin'
    - ' make a payment in chile'
    - ' prontopaga'
    - ' guide'
    - ' integration'
  robots: index
next:
  description: ''
---
Crear un pago en Chile con Webpay consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un bearer token y una firma secreta. De esta forma, las transacciones se autentican y se realizan de forma segura.

**Hay dos formas de integrar Webpay como método de pago en tu comercio:**

* [Redirección a Webpay (flujo completo)](https://docs.prontopaga.com/docs/payins-chile-card#redirecci%C3%B3n-a-webpay-flujo-completo): En este flujo, el cliente es redirigido desde tu sitio al portal de Webpay para ingresar los datos de su tarjeta y completar el pago. Al finalizar, es redirigido de vuelta a tu sitio web, con el resultado de la transacción.
* [Webpay en iFrame (flujo embebido)](https://docs.prontopaga.com/docs/payins-chile-card#webpay-en-iframe-flujo-embebido): Para quienes desean mantener al cliente dentro del mismo sitio, sin redirecciones. Este flujo permite abrir un iFrame o modal directamente en tu página, integrando el formulario de pago de Webpay en tu interfaz. 

***

# Redirección a Webpay (flujo completo)

En esta modalidad, la transacción se inicia en tu sitio y se redirecciona al entorno de Webpay, en donde el cliente completa el proceso de pago en un ambiente seguro administrado por Transbank. Es decir, esta implementación utiliza el *checkout* de Webpay. Al finalizar el pago, el usuario es redirigido de vuelta a tu sitio, en donde se le muestra el resultado final de la transacción.

## ¿Cómo funciona?

El proceso de pago con tarjeta en Chile consta de seis etapas principales:

<Image align="center" src="https://files.readme.io/142fd0e9bcf0ba84714c8cd3817dbba89c667b35ed12b60fd341a149b7ee125c-Chile-01.png" />

1. **Selección de método.** El cliente elige pagar con tarjeta (Webpay) en tu sitio web o aplicación. 
2. **Redirección a Webpay.** El cliente es redirigido al portal de Webpay, en donde ingresa los datos de su tarjeta. 
3. **Redirección al banco.** El cliente es redirigido al portal de su banco, en donde debe confirmar la transacción.
4. **Validación de datos.** Se verifican los datos con el emisor de la tarjeta. 
5. **Autorización y Captura.** Se verifica que existan los fondos suficientes y el dinero se mueve desde el banco del cliente hacia la cuenta de tu comercio. 
6. **Confirmación.** El cliente es redirigido a tu sitio y se muestra el resultado de la transacción. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

## Crea un nuevo pago (flujo completo)

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago, deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment). La solicitud se envía con tu bearer token, así como con tu firma secreta. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros. 

<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

<NotaWebhooks />

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "currency": "CLP",
  "country": "CL",
  "amount": 1000,
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "111111111-1",
  "paymentMethod": "webpay_payment",
  "urlConfirmation": "Webhook",
  "urlFinal": "example.com/successful",
  "urlRejected": "example.com/declined",
  "order": "1234",
  "sing": "Signature of the parameters"
}
```

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un enlace para procesar el pago, así como un identificador de pago del sistema.

### Confirmación de un pago

Una vez que el usuario haya completado el proceso de pago en el formulario, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`. 

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los pay ins](https://docs.prontopaga.com/docs/payins-status).

***

# Webpay en iFrame (flujo embebido)

En este flujo, el cliente realiza el pago directamente en tu sitio, sin ser redirigido a otra página. Al generar la transacción, se abre un iFrame o modal con el formulario de Webpay integrado, lo que permite mantener la experiencia de compra dentro de tu misma interfaz. 

## Crear un nuevo pago (flujo embebido)

Para crear una solicitud de nuevo pago, deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment). La solicitud se envía con tu bearer token, así como con tu firma secreta. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros. 

<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

<NotaWebhooks />

### Solicitar el iFrame

Para solicitar la generación del iFrame, deberás usar el parámetro de personalización `"theme"` y mandar el parámetro `"type": "iframe"`, tal como se muestra en el ejemplo del body de la solicitud.

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "currency": "CLP",
  "country": "CL",
  "amount": 1000,
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "111111111-1",
  "paymentMethod": "webpay_payment",
  "urlConfirmation": "Webhook",
  "urlFinal": "example.com/successful",
  "urlRejected": "example.com/declined",
  "order": "1234",
  "theme": "{\"type\":\"iframe\"}",
  "sing": "Signature of the parameters"
}
```

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un enlace para procesar el pago, así como un identificador de pago del sistema.

### Confirmación de un pago

Una vez que el usuario haya completado el proceso de pago en el formulario, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`. 

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los pay ins](https://docs.prontopaga.com/docs/payins-status).

***

# Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, también puedes hacer pruebas con [nuestros demos](https://demo.insospa.com/transactions/deposit).

# Antes de finalizar tu integración

Estos son algunos puntos importantes a tomar en cuenta, antes de finalizar tu integración con nosotros:

* No almacenar datos sensibles del cliente en tu base de datos.
* Enviar todos los datos requeridos en el body request del [endpoint de creación de pago](https://docs.prontopaga.com/reference/create-payment).
* Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu front-end. Puedes [descargarlos aquí](https://drive.google.com/uc?export=download\&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr).
