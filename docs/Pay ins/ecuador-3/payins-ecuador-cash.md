---
title: Efectivo
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    To create a cash payment in Ecuador, capture the customer data and make a
    request through the ProntoPaga API with a bearer token and a secret
    signature. Once the payment is made, ProntoPaga will notify the result and
    return the transaction data to the specified URL.
  keywords:
    - cash
    - ' cash payment'
    - ' payin'
    - ' ecuador'
    - ' guide'
    - ' integration'
    - ' prontopaga'
    - ' how to make a cash payment'
  robots: index
next:
  description: ''
---
Crear un pago en efectivo en Ecuador consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un bearer token y una firma secreta. De esta forma, las transacciones se autentican y se realizan de forma segura.

Conoce los puntos físicos de pago disponibles en [este artículo](https://docs.prontopaga.com/docs/physical-points-payins).

## ¿Cómo funciona?

El proceso de pago con efectivo en Ecuador consta de seis etapas principales:

<Image align="center" src="https://files.readme.io/bf07abc6015467c1a8a44d3f2ff1f8f43eaa3c42cd73ae006bfe0bd47c135e6d-Ecuador_-_01.jpg" />

1. **Ingreso de datos.** Después de seleccionar los productos o servicios a comprar, el cliente ingresa sus datos personales en un formulario. 
2. **Selección de método.** El cliente elige pagar con efectivo en tu sitio web o aplicación. 
3. **Hoja de pago**. ProntoPaga le entrega una hoja de pago personalizada al cliente, con un código de pago único, así como la información de los puntos físicos en donde puede realizar el pago. 
4. **Pago en punto físico.** El cliente se dirige a uno de los puntos físicos con su hoja de pago y su identificación, y hace el depósito del efectivo. 
5. **Validación de datos.** ProntoPaga valida la infomación del pago. 
6. **Confirmación.** El cliente recibe una confirmación de pago exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación del pago a través de los webhooks que hayas configurado.

## Crea un nuevo pago

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar el método de pago en efectivo en el body de la solicitud.

La solicitud se envía con tu bearer token, así como con tu firma secreta. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros. 

<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

<NotaWebhooks />

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "currency": "USD",
  "country": "EC",
  "amount": 10,
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "12345678912",
  "paymentMethod": "bemovil_payment",
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

## Demos

Contamos con demos que simulan la experiencia de pago del cliente, en donde podrás hacer pruebas. [Conócelos aquí](https://demo.insospa.com/transactions/deposit).

## Antes de finalizar tu integración

Estos son algunos puntos importantes a tomar en cuenta, antes de finalizar tu integración con nosotros:

* No almacenar datos sensibles del cliente en tu base de datos.
* Enviar todos los datos requeridos en el body request del [endpoint de creación de pago](https://docs.prontopaga.com/reference/create-payment).
* Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu front-end. Puedes [descargarlos aquí](https://drive.google.com/uc?export=download\&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr).
