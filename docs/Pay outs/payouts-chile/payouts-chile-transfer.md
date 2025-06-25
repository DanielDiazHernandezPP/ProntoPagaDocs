---
title: Transferencia
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    To make a payout in Chile by bank transfer, the recipient's data must be
    captured and a request made through the API with a bearer token and a secret
    signature, ensuring secure transactions. In addition, you can display logos
    of available banks and test the integration with test data and demos.
  keywords:
    - bank transfer
    - ' transfer payout'
    - ' payout'
    - ' chile'
    - ' wire transfer payout'
    - ' how to make a wire transfer payout'
    - ' guide'
    - ' integration'
    - ' prontopaga'
  robots: index
next:
  description: ''
---
Hacer un retiro en Chile por medio de transferencia bancaria consiste en capturar los datos necesarios de la persona que recibirá el pago y hacer una solicitud a través de nuestra API con un bearer token y una firma secreta. De esta forma, las transacciones se autentican y se realizan de forma segura.

## Lista de bancos

La lista de códigos bancarios para pay outs de tipo transferencia la puedes encontrar en [este artículo](https://docs.prontopaga.com/docs/bank-codes-transfer), dividida por países. El código bancario debe enviarse en el campo `bankCode` del endpoint de creación de un retiro.

## Crea un nuevo retiro

Para hacer una solicitud de nuevo retiro a través de nuestra API deberás usar [este endpoint](https://docs.prontopaga.com/reference/payout). La solicitud se envía con tu bearer token, así como con tu firma secreta. 

<NotaFirma />

Además, debes incluir el código bancario, así como los datos necesarios del cliente al que le mandarás el dinero, como: nombre, apellido, correo electrónico, teléfono, ID, cuenta, entre otros.

<NotaWebhooks />

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "amount": "2000",
  "document_id": "12345678912",
  "beneficiaryName": "John",
  "beneficiaryLastName": "Doe",
  "beneficiaryEmail": "johndoe@example.com",
  "beneficiaryPhone": "999999999",
  "accountNumber": "10070010030000",
  "accountType": "C",
  "bankCode": "1",
  "data": "1234",
  "confirmationURL": "Webhook",
  "currency": "CLP",
  "country": "CL",
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
