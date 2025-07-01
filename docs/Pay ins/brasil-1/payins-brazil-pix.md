---
title: PIX
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    To create a payment in Brazil with PIX, customer data must be captured and a
    request made through the API with a bearer token and a secret signature. In
    addition, an iFrame and QR code must be integrated on the merchant's page,
    and the transaction status must be confirmed through a webhook.
  keywords:
    - pix
    - ' brazil'
    - ' pix payment'
    - ' integration'
    - ' guide'
    - ' payin'
    - ' prontopaga'
  robots: index
next:
  description: ''
---
Crear un pago en Brasil con PIX consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un Bearer Token y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.

Además, todas tus transacciones cuentan con la herramienta automatizada Decision Manager (DM) del motor de gestión de riesgos y prevención de fraude de **Cybersource (A Visa Solution)**.

## ¿Cómo funciona?

PIX es un sistema de pagos instantáneos, creado y administrado por el Banco Central de Brasil, mediante el cual puedes realizar transacciones en tiempo real, tales como, transacciones mediante el uso de códigos QR, claves PIX o transferencias directas. Para completar una transacción utilizando este método de pago, el cliente debe tener una cuenta bancaria o de una institución financiera en Brasil, registrarse en el sistema PIX y aprobar la transacción desde su aplicación.

El proceso de pago con PIX consta de cinco etapas principales:

<Image align="center" src="https://files.readme.io/8ff54b7f2a0598877938bd9a05c37b4c396b18875671ba29ee5ae5abb3f3062d-Pipx-01.png" />

1. **Selección de método.** El cliente elige pagar con PIX en tu sitio web o aplicación.
2. **Generación de QR.** ProntoPaga le entrega un QR y un código único al cliente.
3. **Pago en aplicación.** El cliente podrá escanear el QR con la aplicación de su banco o wallet, o ingresar directamente el código único en la aplicación indicada. El cliente realiza el pago siguiendo las instrucciones en pantalla.
4. **Captura.** El dinero se mueve desde la cuenta del cliente hacia la cuenta de tu comercio.
5. **Confirmación.** El cliente recibe una confirmación de pago exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación del pago a través de los webhooks que hayas configurado.

## Crea un nuevo pago

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `pix_payment` como método de pago en el body de la solicitud.

La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros.

<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

<NotaWebhooks />

### iFrame y QR

El valor del campo `isIframePay` deberá ser enviado como  `true` para este método de pago. De este modo, como respuesta se proporcionará un iFrame y un código QR para que se integre dentro de la página del comercio.

### Tipo de pago

El campo  `typePixPayment` es requerido para este método de pago. Este campo se refiere al tipo de pago que ofrecemos al cliente. Entre ellos se encuentran:

| Valor | Descripción                                                           |
| :---- | :-------------------------------------------------------------------- |
| 1     | Pago inmediato                                                        |
| 2     | Pago con fecha de vencimiento (temporalmente deshabilitado)           |
| 3     | Pago por lotes con fecha de vencimiento (temporalmente deshabilitado) |

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "currency": "BRL",
  "country": "BR",
  "amount": 1000,
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "33177110000",
  "paymentMethod": "pix_payment",
  "urlConfirmation": "Webhook",
  "urlFinal": "example.com/successful",
  "urlRejected": "example.com/declined",
  "order": "1234",
  "sing": "Signature of the parameters",
  "typePixPayment": 1,
  "isIframePay": "true"
}
```

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un enlace de iFrame para incrustar en tu comercio, así como un código PIX que se puede convertir en QR, y un identificador de pago del sistema.

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