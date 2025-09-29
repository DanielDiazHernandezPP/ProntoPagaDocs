---
title: Retiros con QR/Wallet PIX
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Retiros con QR/Wallet PIX | ProntoPaga Docs
  description: >-
    To make a payout in Brazil using PIX, capture the recipient's data and send
    a request through the API. This guide explains the payout flow, required
    parameters, webhook confirmation, and how to simulate transactions in
    sandbox. 
  image: >-
    https://files.readme.io/a63b6d5526dcc01eca80047c36552f0b0cff5cf7f499c0f4951385e13496fa3a-Prontopaga_logotipo.png
  keywords:
    - how to make a pix payout
    - Prontopaga brazil
    - pix payouts
    - integration
    - pay outs Brasil prontopaga
    - Pix Brazil
    - create payout Pix
    - Guide Brazil pay outs
  robots: index
next:
  description: ''
---
Hacer un retiro en Brasil por medio de PIX consiste en capturar los datos necesarios de la persona que recibirá el pago y hacer una solicitud a través de nuestra API con un Bearer Token y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.

***

<br />

## ¿Cómo funciona?

PIX es un sistema de pagos instantáneos, creado y administrado por el Banco Central de Brasil, mediante el cual puedes realizar transacciones en tiempo real, tales como, transacciones mediante el uso de códigos QR, claves PIX o transferencias directas. Para completar una transacción utilizando este método de retiro, el cliente debe tener una cuenta bancaria o de una institución financiera en Brasil y registrarse en el sistema PIX.

El proceso de PayOut con QR/Wallet PIX consta de cinco etapas principales:

<Image align="center" border={false} src="https://files.readme.io/8ca29e682667c63a0323926a1ed2216aaec0c665ead429c0f8e043d59b45e92b-Pipx-01.jpg" />

1. **Selección de método.** El cliente elige retirar dinero con PIX en tu sitio web o aplicación.
2. **Ingreso de datos.** El cliente ingresa los datos necesarios para que el retiro sea realizado y confirma la transacción.
3. **Validación de datos.** ProntoPaga valida la infomación e inicia la solicitud del retiro.
4. **Captura.**  Se aprueba el retiro y el dinero se mueve desde la cuenta del comercio hacia la cuenta del cliente.
5. **Confirmación.** El cliente recibe una confirmación de retiro exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

***

<br />

## Crea un nuevo retiro

Para hacer una solicitud de nuevo retiro a través de nuestra API deberás usar [este endpoint](https://docs.prontopaga.com/reference/payout-brazil-pix). La solicitud se envía con tu Bearer Token, así como con tu secretKey.

<NotaFirma />

Además, debes incluir los datos necesarios del cliente al que le mandarás el dinero, como: nombre, apellido, correo electrónico, teléfono, ID, cuenta, entre otros.

<NotaWebhooks />

<br />

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "amount": "100.90",
  "document_id": "12345678912",
  "beneficiaryName": "John",
  "beneficiaryLastName": "Doe",
  "beneficiaryEmail": "johndoe@example.com",
  "beneficiaryPhone": "999999999",
  "accountType": "1",
  "bankCode": "633",
  "data": "XYZ789",
  "confirmationURL": "https://www.webhook.com",
  "currency": "BRL",
  "country": "BR",
  "pagamentoType": 1,
  "type": "beneficiaryPhone",
  "accountNumber": "11111111",
  "agency": "string",
  "ispb": "string",
  "sign": "Signature of the parameters"
}
```

<br />

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un identificador del retiro en el sistema, el estado del retiro y datos adicionales de la transacción.

<br />

### Confirmación de un retiro

Una vez que hayas completado el proceso, ProntoPaga devolverá los datos de la transacción a la URL que especificaste en `confirmationURL`.

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un retiro en el siguiente enlace: [Estados de los PayOuts](https://docs.prontopaga.com/docs/payouts-status).

***

<br />

## Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, también puedes hacer pruebas con [nuestros demos](https://demo.insospa.com/transactions/deposit).

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
