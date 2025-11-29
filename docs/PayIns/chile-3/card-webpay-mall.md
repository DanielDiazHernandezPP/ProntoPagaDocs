---
title: '[DEPRECADO] Webpay Mall'
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: 'Create a payment in Chile with Webpay Mall '
  description: >-
    Learn how to create payments in Chile through Webpay Mall with the
    Prontopaga API. This guide explains the payin flow, required parameters,
    webhook confirmation, and how to simulate transactions in sandbox. 
  keywords:
    - webpay mall Prontopaga
    - create a payin webpay mall
    - make a payment in chile
    - Prontopaga guide Chile
    - crear un pago con webpay mall
  robots: index
next:
  description: ''
---
Crear un pago en Chile con Webpay consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un bearer token y una firma secreta. De esta forma, las transacciones se autentican y se realizan de forma segura.

## ¿Cómo funciona?

El proceso de pago con tarjeta en Chile consta de seis etapas principales:

<Image align="center" src="https://files.readme.io/142fd0e9bcf0ba84714c8cd3817dbba89c667b35ed12b60fd341a149b7ee125c-Chile-01.png" />

1. **Selección de método.** El cliente elige pagar con tarjeta (Webpay) en tu sitio web o aplicación.
2. **Redirección a Webpay.** El cliente es redirigido al portal de Webpay, en donde ingresa los datos de su tarjeta.
3. **Redirección al banco.** El cliente es redirigido al portal de su banco, en donde debe confirmar la transacción.
4. **Validación de datos.** Se verifican los datos con el emisor de la tarjeta.
5. **Autorización y Captura.** Se verifica que existan los fondos suficientes y el dinero se mueve desde el banco del cliente hacia la cuenta de tu comercio.
6. **Confirmación.** El cliente es redirigido a tu sitio y se muestra el resultado de la transacción. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

## Crea un nuevo pago con Webpay Mall

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago, deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment-chile-webpay-mall). La solicitud se envía con tu bearer token, así como con tu firma secreta. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros.

<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

<NotaWebhooks />

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "currency": "CLP",
  "country": "CL",
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "9999999999",
  "clientDocument": "111111111-1",
  "paymentMethod": "webpay_mall_payment",
  "urlConfirmation": "Webhook",
  "urlFinal": "example.com/successful",
  "urlRejected": "example.com/declined",
  "order": "1234",
  "transactions": [
    {
      "amount": 60000,
      "order_id": "order_12345"
    },
    {
      "amount": 25000,
      "order_id": "order_12346"
    },
    {
      "amount": 55000,
      "order_id": "order_12347"
    }
  ],
  "sign": "Signature of the parameters"
}
```

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un enlace para procesar el pago, así como un identificador de pago del sistema.

### Confirmación de un pago

Una vez que el usuario haya completado el proceso de pago en el formulario, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los pay ins](https://docs.prontopaga.com/docs/payins-status).

## Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, también puedes hacer pruebas con [nuestros demos](https://demo.insospa.com/transactions/deposit).

## Antes de finalizar tu integración

Estos son algunos puntos importantes a tomar en cuenta, antes de finalizar tu integración con nosotros:

* No almacenar datos sensibles del cliente en tu base de datos.
* Enviar todos los datos requeridos en el body request del [endpoint de creación de pago](https://docs.prontopaga.com/reference/create-payment).
* Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu front-end. Puedes [descargarlos aquí](https://drive.google.com/uc?export=download\&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr).