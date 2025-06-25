---
title: Wallet
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    To create a wallet payment in Ecuador, customer data must be captured and a
    request must be made through the ProntoPaga API with a bearer token and a
    secret signature, ensuring secure and authenticated transactions.
  keywords:
    - wallet
    - ' wallet payment'
    - ' payin'
    - ' ecuador'
    - ' guide'
    - ' integration'
    - ' prontopaga'
    - ' how to make a wallet payment'
  robots: index
next:
  description: ''
---
Crear un pago por wallet en Ecuador consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un Bearer Token y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.

Además, todas tus transacciones cuentan con la herramienta automatizada Decision Manager (DM) del motor de gestión de riesgos y prevención de fraude de **Cybersource (A Visa Solution)**.

## ¿Cómo funciona?

Payphone es una billetera digital ecuatoriana que permite recibir pagos, administrar dinero y realizar transacciones desde el celular. Para completar una transacción utilizando este método de pago, el cliente debe seleccionar "Paga con QR/Wallet - Payphone", tener la aplicación instalada en su dispositivo móvil, una cuenta creada con saldo disponible o un medio de pago vinculado, y aprobar el pago desde la aplicación.

El proceso de pago con wallet en Ecuador consta de cuatro etapas principales:

<Image align="center" src="https://files.readme.io/3490310339d9a60072aef598a1df7b2c241f3e63745d72763a64503622931cd4-Ecuador_-_03.jpg" />

1. **Selección de método.** El cliente elige pagar con wallet (Payphone) en tu sitio web o aplicación. 
2. **Solicitud.** ProntoPaga se comunica con la wallet y genera la solicitud de pago. 
3. **Wallet.** El cliente recibe una notificación de pago en su aplicación de Payphone, y la abre para realizar el pago. El dinero se mueve desde la wallet del cliente hacia la cuenta de tu comercio. 
4. **Confirmación.** El cliente es redirigido a tu sitio y se muestra el resultado de la transacción. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

## Crea un nuevo pago

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar  `payphone_payment` como método de pago en el body de la solicitud.

La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros. 

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
  "paymentMethod": "payphone_payment",
  "urlConfirmation": "Webhook",
  "urlFinal": "example.com/successful",
  "urlRejected": "example.com/declined",
  "order": "1234",
  "sing": "Signature of the parameters"
}
```

### Pago en la wallet

El cliente podrá continuar el proceso siguiendo las instrucciones en pantalla. Se redireccionará al cliente al sitio web o aplicación de la wallet, en donde podrá iniciar sesión y hacer el pago.

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un enlace para procesar el pago, así como un identificador de pago del sistema.

### Confirmación de un pago

Una vez que el usuario haya completado el pago, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`. 

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los pay ins](https://docs.prontopaga.com/docs/payins-status).

## Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, también puedes hacer pruebas con [nuestros demos](https://demo.insospa.com/transactions/deposit).

## Antes de finalizar tu integración

Estos son algunos puntos importantes a tomar en cuenta, antes de finalizar tu integración con nosotros:

* No almacenar datos sensibles del cliente en tu base de datos.
* Enviar todos los datos requeridos en el body request del [endpoint de creación de pago](https://docs.prontopaga.com/reference/create-payment).
* Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu front-end. Puedes [descargarlos aquí](https://drive.google.com/uc?export=download\&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr).
