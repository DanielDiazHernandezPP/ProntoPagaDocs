---
title: Retiros en Efectivo
excerpt: Conoce el paso a paso de cómo hacer un retiro en efectivo en Ecuador.
deprecated: false
hidden: false
metadata:
  title: Retiros en Efectivo | ProntoPaga Docs
  description: >-
    The document describes how to make payouts in Ecuador through Payphone,
    Bemovil, and Ponle más using the ProntoPaga API, including capturing
    recipient data, authentication with bearer token and secret signature, and
    verification of successful transactions through webhooks.
  image: >-
    https://files.readme.io/ad21ddc93ed82e4243a9ed07e5612fd1e4dab1a60bd8e61f16f275a8697995c6-Prontopaga_logotipo.png
  keywords:
    - how to make a cash payout
    - cash payout Ecuador
    - Prontopaga payout Ecuador
    - send money in cash Ecuador
    - API cash Ecuador
    - cash withdrawal Ecuador
  robots: index
next:
  description: ''
---
En Ecuador puedes crear retiros en efectivo a través de los siguientes servicios:

* [Red Activa / Western Union](https://docs.prontopaga.com/docs/payouts-ecuador-cash#red-activa--western-union)
* [Bemovil](https://docs.prontopaga.com/docs/payouts-ecuador-cash#bemovil)
* [Ponle más](https://docs.prontopaga.com/docs/payouts-ecuador-cash#ponle-m%C3%A1s)

***

<br />

## ¿Cómo funciona?

Red Activa / Western Union, BeMovil y PonleMás son redes y plataformas que operan en Ecuador y permiten realizar retiros en efectivo. Para completar un retiro utilizando cualquiera de estos métodos, el usuario debe seleccionar la opción correspondiente:

* Retiro con Efectivo - Red Activa
* Retiro con Efectivo - PonleMás
* Retiro con Efectivo - BeMovil

Luego, debe acudir al punto de atención más cercano con su código de retiro y una identificación válida (cédula nacional, cédula de extranjería o pasaporte). Para conocer el listado de los puntos físicos de retiro, puedes consultarlo [aquí](https://docs.prontopaga.com/docs/physical-points-payouts).

El proceso de PayOut con efectivo en Ecuador consta de seis etapas principales:

<Image align="center" border={false} src="https://files.readme.io/8e05caca6fb699284abb15ec89188e5b6774f796319ab08cf642d6236b711c4c-Ecuador-01.jpg" />

1. **Selección de método.** El cliente elige en tu sitio web o aplicación la opción de retirar dinero en efectivo.
2. **Cantidad.** El cliente selecciona la cantidad que desea retirar y confirma la transacción.
3. **Hoja de confirmación.** El cliente recibe una hoja con un código único de retiro, así como con las instrucciones de dónde y cómo recibir el dinero en efectivo.
4. **Validación de datos.** ProntoPaga separa el dinero en tu balance, y cuando el cliente acude al punto físico a retirarlo, valida los datos.
5. **Retiro.**  Si los datos son correctos, ProntoPaga mueve el dinero desde la cuenta de tu comercio hacia ese punto físico y se le entrega el efectivo al cliente.
6. **Confirmación.** El cliente recibe una confirmación de retiro exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

***

<br />

## Red Activa / Western Union

Hacer un retiro en Ecuador por medio de Red Activa consiste en capturar los datos necesarios de la persona que recibirá el pago y hacer una solicitud a través de nuestra API con un Bearer Token y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.

Conoce los puntos físicos de pago disponibles en [este artículo](https://docs.prontopaga.com/docs/physical-points-payouts).

<br />

### Crea un nuevo retiro

Para hacer una solicitud de nuevo retiro a través de nuestra API deberás usar [este endpoint](https://docs.prontopaga.com/reference/payout-ecuador-redactiva). La solicitud se envía con tu Bearer Token, así como con tu secretKey.

<NotaFirma />

Además, debes incluir los datos necesarios del cliente al que le mandarás el dinero, como: nombre, apellido, correo electrónico, ID, entre otros.

<NotaWebhooks />

<br />

#### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "amount": "25.90",
  "document_id": "12345678912",
  "beneficiaryName": "John",
  "beneficiaryLastName": "Doe",
  "beneficiaryEmail": "johndoe@example.com",
  "beneficiaryPhone": "999999999",
  "data": "XYZ789",
  "confirmationURL": "https://www.webhook.com",
  "currency": "USD",
  "country": "EC",
  "sign": "Signature of the parameters"
}
```

<br />

#### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un identificador del retiro en el sistema, el estado del retiro y datos adicionales de la transacción.

<br />

#### Confirmación de un retiro

Una vez que hayas completado el proceso, ProntoPaga devolverá los datos de la transacción a la URL que especificaste en `confirmationURL`.

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un retiro en el siguiente enlace: [Estados de los PayOuts](https://docs.prontopaga.com/docs/payouts-status).

<br />

### Demos

Contamos con demos que simulan la experiencia de retiro del cliente, en donde podrás hacer pruebas. [Conócelos aquí](https://demo.insospa.com/transactions/withdrawal).

***

<br />

## Bemovil

Hacer un retiro en Ecuador por medio de Bemovil consiste en capturar los datos necesarios de la persona que recibirá el pago y hacer una solicitud a través de nuestra API con un Bearer Token y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.

Conoce los puntos físicos de pago disponibles en [este artículo](https://docs.prontopaga.com/docs/physical-points-payouts).

<br />

### Crea un nuevo retiro

Para hacer una solicitud de nuevo retiro a través de nuestra API deberás usar [este endpoint](https://docs.prontopaga.com/reference/payout-ecuador-bemovil). La solicitud se envía con tu Bearer Token, así como con tu secretKey.

Además, debes incluir el número de teléfono asociado a la cuenta de Bemovil a la que harás el depósito, así como los datos necesarios del cliente al que le mandarás el dinero, como: nombre, apellido, correo electrónico, ID, entre otros.

<br />

#### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "amount": "25.90",
  "document_id": "12345678912",
  "beneficiaryName": "John",
  "beneficiaryLastName": "Doe",
  "beneficiaryEmail": "johndoe@example.com",
  "beneficiaryPhone": "999999999",
  "data": "XYZ789",
  "confirmationURL": "https://www.webhook.com",
  "currency": "USD",
  "country": "EC",
  "sign": "Signature of the parameters"
}
```

<br />

#### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un identificador del retiro en el sistema, el estado del retiro y datos adicionales de la transacción.

<br />

#### Confirmación de un retiro

Una vez que hayas completado el proceso, ProntoPaga devolverá los datos de la transacción a la URL que especificaste en `confirmationURL`.

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un retiro en el siguiente enlace: [Estados de los PayOuts](https://docs.prontopaga.com/docs/payouts-status).

<br />

### Demos

Contamos con demos que simulan la experiencia de retiro del cliente, en donde podrás hacer pruebas. [Conócelos aquí](https://demo.insospa.com/transactions/withdrawal).

***

<br />

## Ponle más

Hacer un retiro en Ecuador por medio de Ponle más consiste en capturar los datos necesarios de la persona que recibirá el pago y hacer una solicitud a través de nuestra API con un Bearer Token y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.

Conoce los puntos físicos de pago disponibles en [este artículo](https://docs.prontopaga.com/docs/physical-points-payouts).

<br />

### Crea un nuevo retiro

Para hacer una solicitud de nuevo retiro a través de nuestra API deberás usar [este endpoint](https://docs.prontopaga.com/reference/payout-ecuador-ponle-mas). La solicitud se envía con tu Bearer Token, así como con tu secretKey.

Además, debes incluir el número de teléfono asociado a la cuenta de Ponle más a la que harás el depósito, así como los datos necesarios del cliente al que le mandarás el dinero, como: nombre, apellido, correo electrónico, ID, entre otros.

<br />

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
  "confirmationURL": "https://www.webhook.com",
  "currency": "USD",
  "country": "EC",
  "sign": "Signature of the parameters"
}
```

<br />

#### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un identificador del retiro en el sistema, el estado del retiro y datos adicionales de la transacción.

<br />

#### Confirmación de un retiro

Una vez que hayas completado el proceso, ProntoPaga devolverá los datos de la transacción a la URL que especificaste en `confirmationURL`.

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un retiro en el siguiente enlace: [Estados de los PayOuts](https://docs.prontopaga.com/docs/payouts-status).

<br />

### Demos

Contamos con demos que simulan la experiencia de retiro del cliente, en donde podrás hacer pruebas. [Conócelos aquí](https://demo.insospa.com/transactions/withdrawal).

***

<br />

## Certifica tu integración

La certificación de la integración en _sandbox_ es un paso obligatorio que todos los comercios deben realizar antes de recibir sus credenciales de producción. Su propósito es asegurar que la integración cumpla con los estándares técnicos, funcionales y de seguridad requeridos por ProntoPaga. Dentro de esta sección, se establecen los requisitos que deben cumplirse sin excepción para que la certificación sea aprobada.

<br />

### Requisitos de certificación

A continuación, encontrarás los distintos requisitos necesarios para completar tu certificación:

<Tabs>
  <Tab title="ID del cliente">
    * ❌ El documento de identidad del cliente no debe ser modificable en ningún punto de la transacción.
    * ✅ Es recomendable que este dato no se muestre en el *checkout*. Solo puede estar disponible en la sección de perfil del usuario autenticado.
    * ⚠️ Esta medida tiene como objetivo prevenir fraudes y evitar que se realicen transacciones en nombre de terceros o menores de edad.
  </Tab>

  <Tab title="Logotipos">
    * 📥 Agregar los logotipos de los diferentes métodos de retiro de ProntoPaga a tu *front-end*. Puedes [descargarlos aquí](https://prontopagalatam-my.sharepoint.com/:u:/g/personal/tahbet_reategui_prontopaga_com/EWC1ijJHq5JKnjpIH9qH0ncB42rHOzcbXWdiOlyQQHciCA?e=3taLCb\&download=1).
    * 🔎 Todos los nombres y logos de los métodos de retiro habilitados deben mostrarse de forma clara, sin modificaciones visuales o estilísticas que puedan generar confusión o inducir a errores.
    * ✅ Se recomienda ordenarlos según su popularidad o frecuencia de uso, para mejorar la experiencia del usuario y optimizar la conversión.
  </Tab>

  <Tab title="Mensajes al usuario">
    * ✅ El *checkout* debe incluir mensajes claros y visibles que orienten al usuario durante todo el proceso.

    ❗ Es obligatorio mostrar:

    * ℹ️ Montos mínimos y máximos permitidos para cada método de retiro.
    * ℹ️ Estados transaccionales con claridad: por ejemplo, **Transacción aprobada** o **Transacción rechazada**, junto con una sugerencia de los pasos a seguir en caso de que corresponda.
  </Tab>

  <Tab title="Consideraciones importantes">
    * ❌ No almacenar datos sensibles del cliente en tu base de datos.
    * ✅ La certificación se otorga únicamente si estos requisitos se cumplen en su totalidad en el entorno de *sandbox*.
    * 💻 Una vez validada la integración, se habilitarán las credenciales para el entorno productivo.
    * ⚠️ El incumplimiento de estos requisitos podrá resultar en la denegación de la certificación.
  </Tab>
</Tabs>