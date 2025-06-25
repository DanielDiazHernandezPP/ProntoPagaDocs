---
title: Efectivo
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    The document describes how to make payouts in Ecuador through Payphone,
    Bemovil, and Ponle más using the ProntoPaga API, including capturing
    recipient data, authentication with bearer token and secret signature, and
    verification of successful transactions through webhooks.
  keywords:
    - cash payouts
    - ' cash payout'
    - ' cash'
    - ' ecuador'
    - ' guide'
    - ' integration'
    - ' prontopaga'
    - ' how to make a cash payout'
  robots: index
next:
  description: ''
---
En Ecuador puedes crear retiros en efectivo a través de los siguientes servicios:

- [Red Activa / Western Union](https://docs.prontopaga.com/docs/payouts-ecuador-cash#red-activa--western-union)
- [Bemovil](https://docs.prontopaga.com/docs/payouts-ecuador-cash#bemovil)
- [Ponle más](https://docs.prontopaga.com/docs/payouts-ecuador-cash#ponle-m%C3%A1s)

## ¿Cómo funciona?

El proceso de payout con efectivo en Ecuador consta de seis etapas principales:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8e05caca6fb699284abb15ec89188e5b6774f796319ab08cf642d6236b711c4c-Ecuador-01.jpg",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


1. **Selección de método.** El cliente elige en tu sitio web o aplicación la opción de retirar dinero en efectivo. 
2. **Cantidad.** El cliente selecciona la cantidad que desea retirar y confirma la transacción. 
3. **Hoja de confirmación.** El cliente recibe una hoja con un código único de retiro, así como con las instrucciones de dónde y cómo recibir el dinero en efectivo.  
4. **Validación de datos.** ProntoPaga separa el dinero en tu balance, y cuando el cliente acude al punto físico a retirarlo, valida los datos. 
5. **Retiro.**  Si los datos son correctos, ProntoPaga mueve el dinero desde la cuenta de tu comercio hacia ese punto físico y se le entrega el efectivo al cliente. 
6. **Confirmación.** El cliente recibe una confirmación de retiro exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

## Red Activa / Western Union

Hacer un retiro en Ecuador por medio de Red Activa consiste en capturar los datos necesarios de la persona que recibirá el pago y hacer una solicitud a través de nuestra API con un bearer token y una firma secreta. De esta forma, las transacciones se autentican y se realizan de forma segura.

Conoce los puntos físicos de pago disponibles en [este artículo](https://docs.prontopaga.com/docs/physical-points-payouts).

### Crea un nuevo retiro

Para hacer una solicitud de nuevo retiro a través de nuestra API deberás usar [este endpoint](https://docs.prontopaga.com/reference/payout-ecuador-redactiva). La solicitud se envía con tu bearer token, así como con tu firma secreta. 

<NotaFirma />

Además, debes incluir los datos necesarios del cliente al que le mandarás el dinero, como: nombre, apellido, correo electrónico, ID, entre otros.

<NotaWebhooks />

#### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "amount": 200,
  "document_id": "12345678912",
  "beneficiaryName": "John",
  "beneficiaryLastName": "Doe",
  "beneficiaryEmail": "johndoe@example.com",
  "beneficiaryPhone": "999999999",
  "data": "1234",
  "confirmationURL": "Webhook",
  "currency": "USD",
  "country": "EC",
  "sign": "Signature of the parameters"
}
```

#### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un identificador del retiro en el sistema, el estado del retiro y datos adicionales de la transacción.

#### Confirmación de un retiro

Una vez que hayas completado el proceso, ProntoPaga devolverá los datos de la transacción a la URL que especificaste en `confirmationURL`. 

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un retiro en el siguiente enlace: [Estados de los pay outs](https://docs.prontopaga.com/docs/payouts-status).

### Demos

Contamos con demos que simulan la experiencia de retiro del cliente, en donde podrás hacer pruebas. [Conócelos aquí](https://demo.insospa.com/transactions/withdrawal).

## Bemovil

Hacer un retiro en Ecuador por medio de Bemovil consiste en capturar los datos necesarios de la persona que recibirá el pago y hacer una solicitud a través de nuestra API con un bearer token y una firma secreta. De esta forma, las transacciones se autentican y se realizan de forma segura.

Conoce los puntos físicos de pago disponibles en [este artículo](https://docs.prontopaga.com/docs/physical-points-payouts).

### Crea un nuevo retiro

Para hacer una solicitud de nuevo retiro a través de nuestra API deberás usar [este endpoint](https://docs.prontopaga.com/reference/payout-ecuador-bemovil). La solicitud se envía con tu bearer token, así como con tu firma secreta.

Además, debes incluir el número de teléfono asociado a la cuenta de Bemovil a la que harás el depósito, así como los datos necesarios del cliente al que le mandarás el dinero, como: nombre, apellido, correo electrónico, ID, entre otros.

#### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "amount": 200,
  "document_id": "12345678912",
  "beneficiaryName": "John",
  "beneficiaryLastName": "Doe",
  "beneficiaryEmail": "johndoe@example.com",
  "beneficiaryPhone": "999999999",
  "data": "1234",
  "confirmationURL": "Webhook",
  "currency": "USD",
  "country": "EC",
  "sign": "Signature of the parameters"
}
```

#### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un identificador del retiro en el sistema, el estado del retiro y datos adicionales de la transacción.

#### Confirmación de un retiro

Una vez que hayas completado el proceso, ProntoPaga devolverá los datos de la transacción a la URL que especificaste en `confirmationURL`. 

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un retiro en el siguiente enlace: [Estados de los pay outs](https://docs.prontopaga.com/docs/payouts-status).

### Demos

Contamos con demos que simulan la experiencia de retiro del cliente, en donde podrás hacer pruebas. [Conócelos aquí](https://demo.insospa.com/transactions/withdrawal).

## Ponle más

Hacer un retiro en Ecuador por medio de Ponle más consiste en capturar los datos necesarios de la persona que recibirá el pago y hacer una solicitud a través de nuestra API con un bearer token y una firma secreta. De esta forma, las transacciones se autentican y se realizan de forma segura.

Conoce los puntos físicos de pago disponibles en [este artículo](https://docs.prontopaga.com/docs/physical-points-payouts).

### Crea un nuevo retiro

Para hacer una solicitud de nuevo retiro a través de nuestra API deberás usar [este endpoint](https://docs.prontopaga.com/reference/payout-ecuador-ponle-mas). La solicitud se envía con tu bearer token, así como con tu firma secreta.

Además, debes incluir el número de teléfono asociado a la cuenta de Ponle más a la que harás el depósito, así como los datos necesarios del cliente al que le mandarás el dinero, como: nombre, apellido, correo electrónico, ID, entre otros.

#### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "amount": 200,
  "document_id": "12345678912",
  "beneficiaryName": "John",
  "beneficiaryLastName": "Doe",
  "beneficiaryEmail": "johndoe@example.com",
  "beneficiaryPhone": "999999999",
  "data": "1234",
  "confirmationURL": "Webhook",
  "currency": "USD",
  "country": "EC",
  "sign": "Signature of the parameters"
}
```

#### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un identificador del retiro en el sistema, el estado del retiro y datos adicionales de la transacción.

#### Confirmación de un retiro

Una vez que hayas completado el proceso, ProntoPaga devolverá los datos de la transacción a la URL que especificaste en `confirmationURL`. 

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un retiro en el siguiente enlace: [Estados de los pay outs](https://docs.prontopaga.com/docs/payouts-status).

### Demos

Contamos con demos que simulan la experiencia de retiro del cliente, en donde podrás hacer pruebas. [Conócelos aquí](https://demo.insospa.com/transactions/withdrawal).