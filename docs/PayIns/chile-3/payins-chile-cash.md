---
title: '[DEPRECADO] Efectivo'
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: Create cash payments in Chile
  description: >-
    Learn how to create cash payments in Chile using the Prontopaga API.
    Includes payment flow, API request, test data, and webhook confirmation
    process. 
  image: >-
    https://files.readme.io/bfff8a2c5b9fd5f93b8bde4b0b0332f2529b4b30778099f49e1e916b2042319a-Prontopaga_logotipo.png
  keywords:
    - cash payments Chile
    - Prontopaga cash Chile
    - how to make a cash payment in Chile
    - crear pagos en efectivo Chile
    - usar efectivo para pagos Prontopaga Chile
  robots: index
next:
  description: ''
---
Crear un pago en efectivo en Chile consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un bearer token y una firma secreta. De esta forma, las transacciones se autentican y se realizan de forma segura.

## ¿Cómo funciona?

El proceso de pago con efectivo en Chile consta de seis etapas principales:

<Image align="center" src="https://files.readme.io/e48b22d072db81b882009acc6cdc1de9822b2c99c110558b2677f4d4ba3e3cbc-Chile-02.jpg" />

1. **Ingreso de datos.** Después de seleccionar los productos o servicios a comprar, el cliente ingresa sus datos personales en un formulario.
2. **Selección de método.** El cliente elige pagar con efectivo en tu sitio web o aplicación.
3. **Hoja de pago.** ProntoPaga le entrega una hoja de pago personalizada al cliente, con un código de pago único, así como la información de los puntos físicos en donde puede realizar el pago.
4. **Pago en punto físico.** El cliente se dirige a uno de los puntos físicos con su hoja de pago y su identificación, y hace el depósito del efectivo.
5. **Validación de datos.** ProntoPaga valida la infomación del pago.
6. **Confirmación.** El cliente recibe una confirmación de pago exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación del pago a través de los webhooks que hayas configurado.

## Crea un nuevo pago

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `servifacil_payment` como método de pago en el body de la solicitud.

La solicitud se envía con tu bearer token, así como con tu firma secreta. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros.

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
  "clientDocument": "12345678912",
  "paymentMethod": "servifacil_payment",
  "urlConfirmation": "Webhook",
  "urlFinal": "example.com/successful",
  "urlRejected": "example.com/declined",
  "order": "1234",
  "sing": "Signature of the parameters"
}
```

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un enlace con la hoja de pago, así como un identificador de pago del sistema.

### Hoja de pago

El cliente verá en pantalla y recibirá en su correo electrónico la hoja de pago, que contendrá:

* Monto a pagar
* Código de pago
* Instituciones en las que puede hacer el pago
* Instrucciones para hacer el pago

### Confirmación de un pago

Una vez que el usuario haya realizado el pago en efectivo, ProntoPaga le notificará el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los pay ins](https://docs.prontopaga.com/docs/payins-status).

## Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, también puedes hacer pruebas con [nuestros demos](https://demo.insospa.com/transactions/deposit).

## Antes de finalizar tu integración

Estos son algunos puntos importantes a tomar en cuenta, antes de finalizar tu integración con nosotros:

* No almacenar datos sensibles del cliente en tu base de datos.
* Enviar todos los datos requeridos en el body request del endpoint de [creación de pago](https://docs.prontopaga.com/reference/create-payment).
* Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu front-end. Puedes [descargarlos aquí](https://drive.google.com/uc?export=download\&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr).