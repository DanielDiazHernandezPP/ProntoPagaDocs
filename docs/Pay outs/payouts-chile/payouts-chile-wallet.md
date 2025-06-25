---
title: Wallet
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: >-
    To make a payout to a wallet in Chile, capture the recipient's data and send
    a request through the API with a bearer token and a secret signature; you
    will receive an identifier and the status of the withdrawal, and you can
    confirm the transaction status through a webhook.
  keywords:
    - wallet payout
    - ' chile'
    - ' guide'
    - ' integration'
    - ' wallet'
    - ' prontopaga'
    - ' how to make a wallet payout'
  robots: index
next:
  description: ''
---
Hacer un retiro a wallet en Chile consiste en capturar los datos necesarios de la persona que recibirá el pago y hacer una solicitud a través de nuestra API con un bearer token y una firma secreta. De esta forma, las transacciones se autentican y se realizan de forma segura.

## Crea un nuevo retiro

Para hacer una solicitud de nuevo retiro a través de nuestra API deberás usar [este endpoint](https://docs.prontopaga.com/reference/withdrawal). La solicitud se envía con tu bearer token, así como con tu firma secreta. 

<NotaFirma />

Además, debes incluir los datos necesarios del cliente al que le mandarás el dinero, como: nombre, apellido, correo electrónico, teléfono, ID, entre otros.

<NotaWebhooks />

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un identificador del retiro en el sistema, el estado del retiro y datos adicionales de la transacción.

### Confirmación de un retiro

Una vez que hayas completado el proceso, ProntoPaga devolverá los datos de la transacción a la URL que especificaste en `confirmationURL`. 

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un retiro en el siguiente enlace: [Estados de los pay outs](https://docs.prontopaga.com/docs/payouts-status).

## Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, también puedes hacer pruebas con [nuestros demos](https://demo.insospa.com/transactions/deposit).