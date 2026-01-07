---
title: Acepta pagos con Pix
excerpt: Conoce el paso a paso de cómo crear un pago con Pix en Brasil.
deprecated: false
hidden: true
metadata:
  title: Acepta pagos con PIX | ProntoPaga Docs
  description: >-
    Learn how to receive payments in Brazil using PIX with the Prontopaga API.
    This guide explains the payin flow, required parameters, webhook
    confirmation, and how to simulate transactions in sandbox.
  image: >-
    https://files.readme.io/9389701d8f5b473614b95d3e6c67b7f71e0c83090528d5bd26eb4c6f4b0efe96-Prontopaga_logotipo.png
  keywords:
    - Prontopaga brasil
    - pix payment
    - integration
    - pay ins Brasil prontopaga
    - crear pagos con Pix Brazil
    - create payments Pix
    - Guide Brasil pay ins
  robots: index
---
Crear un pago en Brasil con Pix consiste en capturar los datos necesarios del cliente para el pago y enviar una solicitud a través de nuestra API con un _Bearer Token_ y una _secretKey_. De esta forma, las transacciones se autentican y se realizan de forma segura.

Para comercios _gambling_, el flujo incluye una validación de pago a terceros, mediante la cual se verifica que la información de la cuenta bancaria del pagador pertenezca al mismo titular del CPF (_Cadastro de Pessoa Física_). Si la validación no se cumple, el pago será rechazado.

***

<br />

## ¿Cómo funciona?

Pix es un sistema de pagos instantáneos, creado y administrado por el Banco Central de Brasil, mediante el cual puedes realizar transacciones en tiempo real, como pagos con código o QR. Para completar una transacción con este método de pago, el cliente debe tener una cuenta bancaria o de una institución financiera en Brasil, registrarse en el sistema PIX y aprobar la transacción desde su aplicación.

El proceso de pago con Pix consta de cinco etapas principales:

<Image align="center" border={false} src="https://files.readme.io/6befce8dcb8b67b10ced2b56a597a9d8094f4a1c79234814f3e2e9f7f3429db9-payin_PIX_updated.jpg" />

1. **Selección de método.** El cliente elige pagar con Pix en tu sitio web o aplicación.
2. **Generación de QR.** ProntoPaga le entrega un QR y un código único al cliente.
3. **Pago en aplicación.** El cliente podrá escanear el QR con la aplicación de su banco,_wallet_, o ingresar directamente el código único en su aplicación o banca en línea. El cliente realiza el pago siguiendo las instrucciones en pantalla.
4. **Captura.** El dinero se mueve desde la cuenta del cliente hacia la cuenta de tu comercio.
5. **Confirmación.** El cliente recibe una confirmación de pago exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación del pago a través de los _webhooks_ que hayas configurado.

***

<br />

## Crea un nuevo pago

Tu _front-end_ será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu _back-end_ estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `br_pix_payment` como método de pago en el body de la solicitud.

La solicitud se envía con tu _Bearer Token_, así como con tu _secretKey_. Además, debes incluir los datos necesarios del cliente para hacer el pago, como nombre, correo electrónico, teléfono, país, moneda, monto, entre otros.

<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

<NotaWebhooks />

<br />

### Tipos de pago

Hay cuatro formas de enviar la solicitud de pago, que dependen de dos factores:

* Si el cliente tiene o no una cuenta bancaria registrada.
* Si el pago se realiza con QR o sin QR.

**Las combinaciones posibles son:**

* Pago con cuenta bancaria registrada y QR.
* Pago con cuenta bancaria registrada sin QR.
* Pago sin cuenta bancaria registrada y QR.
* Pago sin cuenta bancaria registrada sin QR.

***

<br />

### Pagos con cuenta bancaria registrada

A continuación, te mostramos dos ejemplos de _body_ para pagos con cuenta bancaria registrada, con y sin QR.

<Callout icon="👍" theme="okay">
  **accountType**

  El parámetro `accountType` es necesario para pagos con cuentas bancarias registradas.
</Callout>

Estos son los posibles tipos de cuentas que se pueden enviar en el parámetro `accountType`:

* `payment`
* `checking`
* `salary`
* `savings`

<br />

#### Body de la solicitud - QR

A continuación, puedes ver un ejemplo del _body_ que se envía en la solicitud para **pagos con cuenta bancaria registrada y QR**:

```json
{
  "currency": "BRL",
  "country": "BR",
  "amount": "150.90",
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientDocument": "12345678901",
  "clientPhone": "999999999",
  "paymentMethod": "br_pix_payment",
  "urlConfirmation": "https://www.webhook.com/confirmation",
  "urlFinal": "https://www.webhook.com/final",
  "urlRejected": "https://www.webhook.com/rejected",
  "order": "1234",
  "addressLine1": "Rua Haddock Lobo, 50",
  "codePostal": "01234-005",
  "city": "São Paulo",
  "bankCode": "30980539",
  "branchCode": "1",
  "accountType": "payment",
  "accountNumber": "100000284277",
  "theme": "{\"type\":\"qr\"}",
  "sign": "Signature of the parameters"
}
```

<Callout icon="📘" theme="info">
  **Parámetro `theme`**

  El campo `theme`:`"{\"type\":\"qr\"}"`es obligatorio para crear pagos con QR.
</Callout>

<br />

#### Body de la solicitud - sin QR

A continuación, puedes ver un ejemplo del body que se envía en la solicitud para **pagos con cuenta bancaria registrada sin QR**.

```json
{
  "currency": "BRL",
  "country": "BR",
  "amount": "150.90",
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientDocument": "12345678901",
  "clientPhone": "999999999",
  "paymentMethod": "br_pix_payment",
  "urlConfirmation": "https://www.webhook.com/confirmation",
  "urlFinal": "https://www.webhook.com/successful",
  "urlRejected": "https://www.webhook.com/rejected",
  "addressLine1": "Rua Haddock Lobo, 50",
  "codePostal": "01234-005",
  "city": "São Paulo",
  "bankCode": "30980539",
  "branchCode": "1",
  "accountType": "payment",
  "accountNumber": "100000284277",
  "sign": "Signature of the parameters"
}
```

***

<br />

### Pagos sin cuenta bancaria registrada

A continuación, te mostramos dos ejemplos de _body_ para pagos sin cuenta bancaria registrada, con y sin QR.

#### Body de la solicitud - QR

```json
{
  "currency": "BRL",
  "country": "BR",
  "amount": "150.90",
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientDocument": "12345678901",
  "clientPhone": "999999999",
  "paymentMethod": "br_pix_payment",
  "urlConfirmation": "https://www.webhook.com/confirmation",
  "urlFinal": "https://www.webhook.com/final",
  "urlRejected": "https://www.webhook.com/rejected",
  "order": "1234",
  "theme": "{\"type\":\"qr\"}",
  "sign": "Signature of the parameters"
}
```

<Callout icon="📘" theme="info">
  **Parámetro `theme`**

  El campo `theme`:`"{\"type\":\"qr\"}"`es obligatorio para crear pagos con QR.
</Callout>

<br />

#### Body de la solicitud - sin QR

```json
{
  "currency": "BRL",
  "country": "BR",
  "amount": "150.90",
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientDocument": "12345678901",
  "clientPhone": "999999999",
  "paymentMethod": "br_pix_payment",
  "urlConfirmation": "https://www.webhook.com/confirmation",
  "urlFinal": "https://www.webhook.com/final",
  "urlRejected": "https://www.webhook.com/rejected",
  "order": "1234",
  "sign": "Signature of the parameters"
}
```

***

<br />

### Reglas de validación

A continuación, te mostramos las reglas que debes tener en cuenta para los valores en el _body_ de la solicitud.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Campo</b></th>
      <th><b>Regla de validación</b></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>accountType</code></td>
      <td>Obligatorio para pagos con cuentas bancarias registradas.</td>
    </tr>
    <tr>
      <td><code>accountNumber</code></td>
      <td>Debe contener exactamente <b>7, 10, 12 o 15 dígitos</b>.</td>
    </tr>
    <tr>
      <td><code>clientDocument</code></td>
      <td>Acepta números, puntos y guiones.</td>
    </tr>
    <tr>
      <td><code>branchCode</code></td>
      <td>Debe contener entre <b>1 y 4 dígitos</b>.</td>
    </tr>
    <tr>
      <td><code>address</code></td>
      <td>Se admiten entre <b>0 y 256 caracteres</b>.</td>
    </tr>
    <tr>
      <td><code>city</code></td>
      <td>Se admiten entre <b>0 y 50 caracteres</b>.</td>
    </tr>
    <tr>
      <td><code>bankCode</code></td>
      <td>
        Debe contener entre <b>5 y 8 dígitos</b>. Corresponde al
        <b> número ISPB</b> del banco en Brasil.
      </td>
    </tr>
  </tbody>
</table>
`}</HTMLBlock>

***

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un enlace para procesar el pago, así como un identificador de pago del sistema.

Para pagos con QR, recibirás un _QR code_ plano y un QR código base 64 que puedes renderizar en tu propia interfaz. 

***

<br />

### Confirmación de un pago

Una vez que el usuario haya completado el proceso de pago en el formulario, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

Para confirmar si una transacción fue exitosa, debes verificar que en tu _webhook_ el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los PayIns](https://docs.prontopaga.com/docs/payins-status).

***

## Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, puedes hacer pruebas con nuestros demos:

<Embed url="https://experience.prontopaga.com/" href="https://experience.prontopaga.com/" typeOfEmbed="iframe" height="1000px" width="100%" iframe="true" html="false" />

***

## Certifica tu integración

La certificación de la integración en _Sandbox_ es un paso obligatorio que todos los comercios deben realizar antes de recibir sus credenciales de producción. Su propósito es asegurar que la integración cumpla con los estándares técnicos, funcionales y de seguridad requeridos por ProntoPaga. Dentro de esta sección, se establecen los requisitos que deben cumplirse sin excepción para que la certificación sea aprobada.

### Requisitos de certificación

A continuación, encontrarás los distintos requisitos necesarios para completar tu certificación:

<Tabs>
  <Tab title="ID del cliente">
    * ❌ El documento de identidad del cliente no debe ser modificable en ningún punto de la transacción.
    * ✅ Es recomendable que este dato no se muestre en el *checkout*. Solo puede estar disponible en la sección de perfil del usuario autenticado.
    * ⚠️ Esta medida tiene como objetivo prevenir fraudes y evitar que se realicen transacciones en nombre de terceros o menores de edad.
  </Tab>

  <Tab title="Logotipos">
    * 📥 Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu *front-end*. Puedes [descargarlos aquí.](https://drive.google.com/uc?export=download\&id=1eOgEauFj0qIs0JXq0WHpAWWQOYkc9Vn3)

    ***

    * 🔎 Todos los nombres y logos de los métodos de pago habilitados deben mostrarse de forma clara, sin modificaciones visuales o estilísticas que puedan generar confusión o inducir a errores.
    * ✅ Se recomienda ordenarlos según su popularidad o frecuencia de uso, para mejorar la experiencia del usuario y optimizar la conversión.
  </Tab>

  <Tab title="Mensajes al usuario">
    * ✅ El *checkout* debe incluir mensajes claros y visibles que orienten al usuario durante todo el proceso.

    ❗ Es obligatorio mostrar:

    * ℹ️ Montos mínimos y máximos permitidos para cada método de pago.
    * ℹ️ Estados transaccionales con claridad: por ejemplo, **Transacción aprobada** o **Transacción rechazada**, junto con una sugerencia de los pasos a seguir en caso de que corresponda.
  </Tab>

  <Tab title="Consideraciones importantes">
    * ❌ No almacenar datos sensibles del cliente en tu base de datos.
    * ✅ La certificación se otorga únicamente si estos requisitos se cumplen en su totalidad en el entorno de *sandbox*.
    * 💻 Una vez validada la integración, se habilitarán las credenciales para el entorno productivo.
    * ⚠️ El incumplimiento de estos requisitos podrá resultar en la denegación de la certificación.
  </Tab>
</Tabs>
