---
title: Wallet
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    To create a payment in Chile using a wallet, customer data must be captured
    and a request made through the API with a bearer token and a secret
    signature, ensuring secure and authenticated transactions.
  keywords:
    - wallet
    - ' wallet payment'
    - ' chile'
    - ' pay in'
    - ' guide'
    - ' integration'
    - ' prontopaga'
    - ' how to make a wallet payment'
  robots: index
next:
  description: ''
---
Crear un pago a través de una wallet en Chile consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un bearer token y una firma secreta. De esta forma, las transacciones se autentican y se realizan de forma segura.

Además, todas tus transacciones cuentan con la herramienta automatizada Decision Manager (DM) del motor de gestión de riesgos y prevención de fraude de **Cybersource (A Visa Solution)**.

## ¿Cómo funciona?

El proceso de pago con wallet en Chile consta de cinco etapas principales:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d3c75fd752b1ff12a272919a8fc206ad0cb664c25b35e34488645bab9016f0b0-Chile-04.jpg",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


1. **Selección de método.** El cliente elige pagar con wallet en tu sitio web o aplicación. 
2. **Solicitud.** ProntoPaga se comunica con la wallet y genera la solicitud de pago. 
3. **Wallet.** El cliente es redireccionado a la aplicación de su wallet.
4. **Captura.** El cliente sigue los pasos en su aplicación de wallet y realiza el pago. El dinero se mueve desde la wallet del cliente hacia la cuenta de tu comercio. 
5. **Confirmación.** El cliente es redirigido a tu sitio y se muestra el resultado de la transacción. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

## Crea un nuevo pago

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `mercadopagoqr_payment` o  `mach_payment`según sea el caso, como método de pago en el body de la solicitud.

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
  "paymentMethod": "mercadopagoqr_payment",
  "urlConfirmation": "Webhook",
  "urlFinal": "example.com/successful",
  "urlRejected": "example.com/declined",
  "order": "1234",
  "sing": "Signature of the parameters"
}
```

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un enlace para procesar el pago, así como un identificador de pago del sistema.

### Pago en la wallet

El cliente podrá continuar el proceso siguiendo las instrucciones en pantalla. Deberá abrir la aplicación de su wallet para continuar con el pago.

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