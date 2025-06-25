---
title: QR/Wallet PIX
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    To make a payout in Brazil using PIX, capture the recipient's data and send
    a request through the API with a bearer token and a secret signature; you
    will receive an identifier and the status of the withdrawal, and you can
    confirm the transaction by checking your webhook.
  keywords:
    - pix
    - ' pix payout'
    - ' payout'
    - ' brazil'
    - ' guide'
    - ' integration'
    - ' how to make a pix payout'
    - ' prontopaga'
  robots: index
next:
  description: ''
---
Hacer un retiro en Brasil por medio de PIX consiste en capturar los datos necesarios de la persona que recibirá el pago y hacer una solicitud a través de nuestra API con un bearer token y una firma secreta. De esta forma, las transacciones se autentican y se realizan de forma segura.

## ¿Cómo funciona?

El proceso de payout con QR/Wallet PIX consta de cinco etapas principales:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8ca29e682667c63a0323926a1ed2216aaec0c665ead429c0f8e043d59b45e92b-Pipx-01.jpg",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


1. **Selección de método. **El cliente elige retirar dinero con PIX en tu sitio web o aplicación. 
2. **Ingreso de datos.** El cliente ingresa los datos necesarios para que el retiro sea realizado y confirma la transacción. 
3. **Validación de datos.** ProntoPaga valida la infomación e inicia la solicitud del retiro.
4. **Captura.**  Se aprueba el retiro y el dinero se mueve desde la cuenta del comercio hacia la cuenta del cliente.  
5. **Confirmación. **El cliente recibe una confirmación de retiro exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

## Crea un nuevo retiro

Para hacer una solicitud de nuevo retiro a través de nuestra API deberás usar [este endpoint](https://docs.prontopaga.com/reference/payout-brazil-pix). La solicitud se envía con tu bearer token, así como con tu firma secreta. 

<NotaFirma />

Además, debes incluir los datos necesarios del cliente al que le mandarás el dinero, como: nombre, apellido, correo electrónico, teléfono, ID, cuenta, entre otros.

<NotaWebhooks />

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "amount": 100,
  "document_id": "12345678912",
  "beneficiaryName": "John",
  "beneficiaryLastName": "Doe",
  "beneficiaryEmail": "johndoe@example.com",
  "beneficiaryPhone": "999999999",
  "accountType": "1",
  "bankCode": "633",
  "data": "1234",
  "confirmationURL": "Webhook",
  "currency": "BRL",
  "country": "BR",
  "sign": "Signature of the parameters",
  "pagamentoType": 1,
  "type": "beneficiaryPhone",
  "accountNumber": "11111111",
  "agency": "string",
  "ispb": "string"
}
```

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un identificador del retiro en el sistema, el estado del retiro y datos adicionales de la transacción.

### Confirmación de un retiro

Una vez que hayas completado el proceso, ProntoPaga devolverá los datos de la transacción a la URL que especificaste en `confirmationURL`. 

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un retiro en el siguiente enlace: [Estados de los pay outs](https://docs.prontopaga.com/docs/payouts-status).

## Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, también puedes hacer pruebas con [nuestros demos](https://demo.insospa.com/transactions/deposit).