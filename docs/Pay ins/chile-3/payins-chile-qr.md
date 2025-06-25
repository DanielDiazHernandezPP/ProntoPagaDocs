---
title: QR
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    To create a QR payment in Chile, customer data must be captured and a
    request must be made through the API with a bearer token and a secret
    signature, ensuring authentication and transaction security.
  keywords:
    - qr
    - ' qr payment'
    - ' chile'
    - ' payin'
    - ' guide'
    - ' integration'
    - ' prontopaga'
    - ' how to make a qr payment'
  robots: index
next:
  description: ''
---
Crear un pago por QR en Chile consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un bearer token y una firma secreta. De esta forma, las transacciones se autentican y se realizan de forma segura.

Además, todas tus transacciones cuentan con la herramienta automatizada Decision Manager (DM) del motor de gestión de riesgos y prevención de fraude de **Cybersource (A Visa Solution)**.

## ¿Cómo funciona?

El proceso de pago con QR en Chile consta de cuatro etapas principales:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fc447752eb33caef4a4ec1b20e70f55f4e25426e66b742a21046149de4a7ed65-Chile-05.jpg",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


1. **Selección de método.** El cliente elige pagar con QR a través de una wallet en tu sitio web o aplicación. 
2. **Generación del QR.** ProntoPaga le entrega un QR único al cliente, el cual podrá escanear con la aplicación de la wallet con la que pagará. 
3. **Pago en aplicación.** El cliente abre la aplicación de su wallet, escanea el código QR y hace el pago. El dinero se mueve desde la wallet del cliente hacia la cuenta de tu comercio. 
4. **Confirmación. **El cliente recibe una confirmación de pago exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación del pago a través de los webhooks que hayas configurado.

## Crea un nuevo pago

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `mercadopagoqr_payment` o `mach_payment` según sea el caso, como método de pago en el body de la solicitud.

La solicitud se envía con tu bearer token, así como con tu firma secreta. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros. 

<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

<NotaWebhooks />

### iFrame y QR

El valor del campo `isIframePay` deberá ser enviado como  `true` para este método de pago. De este modo, como respuesta se proporcionará un iFrame y un código QR para que se integre dentro de la página del comercio.

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
  "paymentMethod": "mach_payment",
  "urlConfirmation": "Webhook",
  "urlFinal": "example.com/successful",
  "urlRejected": "example.com/declined",
  "order": "1234",
  "isIframePay": "true",
  "sing": "Signature of the parameters"
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

- No almacenar datos sensibles del cliente en tu base de datos.
- Enviar todos los datos requeridos en el body request del [endpoint de creación de pago](https://docs.prontopaga.com/reference/create-payment).
- Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu front-end. Puedes [descargarlos aquí](https://drive.google.com/uc?export=download&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr).