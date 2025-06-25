---
title: Transferencia
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    To make a payout in Ecuador by bank transfer, capture the recipient's data
    and make a request through the API with a bearer token and a secret
    signature; the transaction is authenticated and secure. You can test the
    integration using test data and demos provided.
  keywords:
    - bank transfer payout
    - ' transfer payout'
    - ' wire transfer payout'
    - ' payouts'
    - ' ecuador'
    - ' guide'
    - ' integration'
    - ' prontopaga'
    - ' how to make a wire transfer payout'
  robots: index
next:
  description: ''
---
Hacer un retiro en Ecuador por medio de transferencia bancaria consiste en capturar los datos necesarios de la persona que recibirá el pago y hacer una solicitud a través de nuestra API con un bearer token y una firma secreta. De esta forma, las transacciones se autentican y se realizan de forma segura.

## ¿Cómo funciona?

El proceso de payout con transferencia en Ecuador consta de cuatro etapas principales:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e179fa877d2c9653fa04ffd4e76a1a6ddefcc1b2e1ea46d41c1a57dd31d3d8f3-Ecuador-02.jpg",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


1. **Selección de método.** El cliente elige retirar dinero por medio de transferencia en tu sitio web o aplicación. 
2. **Ingreso de datos.** El cliente ingresa los datos necesarios para que el retiro sea realizado (como banco, número y tipo de cuenta) y confirma la transacción. 
3. **Validación y Captura. **ProntoPaga valida la información del retiro, hace la solicitud de transferencia al banco y mueve el dinero desde la cuenta del comercio hacia la cuenta del cliente.  
4. **Confirmación.** El cliente recibe una confirmación de retiro exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

## Lista de bancos

La lista de códigos bancarios para pay outs de tipo transferencia la puedes encontrar en [este artículo](https://docs.prontopaga.com/docs/bank-codes-transfer), dividida por países. El código bancario debe enviarse en el campo `bankCode` del endpoint de creación de un retiro.

## Crea un nuevo retiro

Para hacer una solicitud de nuevo retiro a través de nuestra API deberás usar [este endpoint](https://docs.prontopaga.com/reference/payout). La solicitud se envía con tu bearer token, así como con tu firma secreta.

<NotaFirma />

Además, debes incluir los datos necesarios del cliente al que le mandarás el dinero, como: nombre, apellido, correo electrónico, teléfono, ID, cuenta, entre otros.

<NotaWebhooks />

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "amount": "200",
  "document_id": "12345678912",
  "beneficiaryName": "John",
  "beneficiaryLastName": "Doe",
  "beneficiaryEmail": "johndoe@example.com",
  "beneficiaryPhone": "999999999",
  "accountNumber": "10070010030000",
  "accountType": "AHO",
  "accountType_id": "P",
  "bankCode": "10",
  "data": "1234",
  "confirmationURL": "Webhook",
  "currency": "USD",
  "country": "EC",
  "sign": "Signature of the parameters"
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