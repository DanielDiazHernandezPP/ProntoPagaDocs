---
title: Transferencia
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: Bank transfer payouts in Peru
  description: >-
    Learn how to make bank transfer payouts in Peru using the Prontopaga API.
    This guide covers how to capture recipient data, authenticate the request
    using a bearer token and secret signature, retrieve bank codes, and confirm
    transactions via webhooks. 
  image: >-
    https://files.readme.io/fdc5ba801b62da5117d8c01d3d898b1e2bd16941f18d48878b69191cdd9b45ff-Prontopaga_logotipo.png
  keywords:
    - payouts Peru
    - bank transfer Peru
    - Prontopaga payout Peru
    - transferencias bancarias Perú
    - Prontopaga bank withdrawal
    - how to withdraw money in Peru
    - hacer retiros por internet
  robots: index
next:
  description: ''
---
Hacer un retiro en Perú por medio de transferencia bancaria consiste en capturar los datos necesarios de la persona que recibirá el pago y hacer una solicitud a través de nuestra API con un bearer token y una firma secreta. De esta forma, las transacciones se autentican y se realizan de forma segura.

## Lista de bancos

Si deseas que en tu front-end se muestren los logos de los bancos disponibles para que tu cliente haga la transferencia, puedes utilizar [este endpoint](https://docs.prontopaga.com/reference/bank-codes) antes de crear el retiro. Si no, el siguiente endpoint hará la redirección al banco seleccionado por el cliente.

## Crea un nuevo retiro

Para hacer una solicitud de nuevo retiro a través de nuestra API deberás usar [este endpoint](https://docs.prontopaga.com/reference/withdrawal). La solicitud se envía con tu bearer token, así como con tu firma secreta.

<NotaFirma />

Además, debes incluir el código bancario obtenido del [endpoint anterior](https://docs.prontopaga.com/reference/bank-codes), así como los datos necesarios del cliente al que le mandarás el dinero, como: nombre, apellido, correo electrónico, teléfono, ID, cuenta, entre otros.

<NotaWebhooks />

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un identificador del retiro en el sistema, el estado del retiro y datos adicionales de la transacción.

### Confirmación de un retiro

Una vez que hayas completado el proceso, ProntoPaga devolverá los datos de la transacción a la URL que especificaste en `confirmationURL`. 

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un retiro en el siguiente enlace: [Estados de los pay outs](https://docs.prontopaga.com/docs/payouts-status).

## Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, también puedes hacer pruebas con [nuestros demos](https://demo.insospa.com/transactions/deposit).