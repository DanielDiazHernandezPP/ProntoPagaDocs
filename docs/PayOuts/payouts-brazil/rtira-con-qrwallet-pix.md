---
title: Retiros instántaneos con Pix
excerpt: Conoce el paso a paso de cómo hacer un retiro con Pix en Brasil.
deprecated: false
hidden: true
metadata:
  robots: index
---
Hacer un retiro en Brasil por medio de **Pix** consiste en capturar los datos necesarios de la persona que recibirá el pago y realizar una solicitud a través de nuestra API con un _Bearer Token_ y una _secretKey_. De esta forma, las transacciones se autentican y se realizan de forma segura.

El flujo incluye una validación de pago a terceros, mediante la cual se verifica que la cuenta de destino pertenece al mismo titular del CPF. Si la validación no se cumple, el retiro no se procesará.

***

## ¿Cómo funciona?

Pix es un sistema de pagos instantáneos, creado y administrado por el Banco Central de Brasil, que permite realizar transacciones en tiempo real mediante códigos QR, claves Pix o transferencias directas. Para completar una transacción con este método de retiro, el cliente debe tener una cuenta bancaria o de una institución financiera en Brasil y registrarse en el sistema Pix.

El proceso de PayOut con QR/Wallet Pix consta de cinco etapas principales:

<Image align="center" border={false} src="https://files.readme.io/8ca29e682667c63a0323926a1ed2216aaec0c665ead429c0f8e043d59b45e92b-Pipx-01.jpg" />

1. **Selección de método.** El cliente elige retirar dinero con Pix en tu sitio web o aplicación.
2. **Ingreso de datos.** El cliente ingresa los datos necesarios para realizar el retiro y confirma la transacción.
3. **Validación de datos.** ProntoPaga valida la información e inicia la solicitud del retiro.
4. **Captura.**  Se aprueba el retiro y el dinero se mueve desde la cuenta del comercio hacia la cuenta del cliente.
5. **Confirmación.** El cliente recibe una confirmación de retiro exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación a través de los _webhooks_ que hayas configurado.

***

## Crea un nuevo retiro

Para hacer una solicitud de nuevo retiro a través de nuestra API deberás usar [este endpoint](https://docs.prontopaga.com/reference/payout-brazil-pix). La solicitud se envía con tu _Bearer Token_, así como con tu _secretKey_.

<NotaFirma />

Además, debes incluir los datos necesarios del cliente al que le mandarás el dinero, como nombre, apellido, correo electrónico, teléfono, ID, cuenta, entre otros.

<NotaWebhooks />

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
    "amount": "150.90",
    "document_id":"123.456.789-12",
    "beneficiaryName": "John",
    "beneficiaryLastName":"Doe",
    "beneficiaryEmail": "johndoe@example.com",
    "beneficiaryPhone" : "55999999999",
    "accountType" :"SL",
    "bankCode" : "001",
    "data": "XYZ789",
    "confirmationURL": "https://www.webhook.com",
    "currency": "BRL",
    "country": "BR",
    "pagamentoType": "1",
    "Type": "payment",
    "accountNumber" :"11111111",
    "agency": "0001",
    "ispb":'30880529',
    "sign": "Signature of the parameters"
}
```

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un identificador del retiro en el sistema (`uid`), el estado del retiro y los datos adicionales de la transacción.

#### Ejemplo de respuesta exitosa

```json
{
    "uid": "01KCQ208BJ2VK463NMS1Z6CYAT",
    "status": "new",
    "data": "1675967931",
    "reference": 15503
}
```

***

<br />

### Confirmación de un retiro

Una vez que hayas completado el proceso, ProntoPaga devolverá los datos de la transacción a la URL que especificaste en `confirmationURL`.

Para confirmar si una transacción fue exitosa, debes verificar que en tu _webhook_ el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un retiro en el siguiente enlace: [Estados de los PayOuts](https://docs.prontopaga.com/docs/payouts-status).

***

### Códigos bancarios

Los pagos Pix a través de ProntoPaga están disponibles para los principales bancos brasileños, incluidos Banco do Brasil, Itaú, Bradesco, Santander, Nubank, Caixa Econômica Federal, entre otros.

```
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Bank name</b></th>
      <th><b>Bank code</b></th>
      <th><b>Acronym</b></th>
      <th><b>Country</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Banco do Brasil S.A.</td><td>001</td><td>BB</td><td>BR</td></tr>
    <tr><td>Banco BRB</td><td>070</td><td>BRB</td><td>BR</td></tr>
    <tr><td>Caixa Econômica Federal</td><td>104</td><td>CEF</td><td>BR</td></tr>
    <tr><td>Banco Inter S.A.</td><td>077</td><td>INTER</td><td>BR</td></tr>
    <tr><td>Sicredi</td><td>748</td><td>SIC</td><td>BR</td></tr>
    <tr><td>Banco Cooperativo Sicoob S.A.</td><td>756</td><td>SICOOB</td><td>BR</td></tr>
    <tr><td>Goldman Sachs do Brasil</td><td>064</td><td>GS</td><td>BR</td></tr>
    <tr><td>Banco Inbursa S.A.</td><td>012</td><td>INB</td><td>BR</td></tr>
    <tr><td>Banco do Nordeste do Brasil S.A.</td><td>004</td><td>BNB</td><td>BR</td></tr>
    <tr><td>PicPay Bank S.A.</td><td>380</td><td>PICPAY</td><td>BR</td></tr>
    <tr><td>Banco Agibank S.A.</td><td>121</td><td>AGI</td><td>BR</td></tr>
    <tr><td>Paraná Banco S.A.</td><td>254</td><td>PB</td><td>BR</td></tr>
    <tr><td>Banco Mercantil do Brasil S.A.</td><td>389</td><td>BMB</td><td>BR</td></tr>
    <tr><td>Banco Digio S.A.</td><td>335</td><td>DIGIO</td><td>BR</td></tr>
    <tr><td>Banco do Estado do Espírito Santo S.A.</td><td>021</td><td>BANESTES</td><td>BR</td></tr>
    <tr><td>Banco BTG Pactual S.A.</td><td>208</td><td>BTG</td><td>BR</td></tr>
    <tr><td>Banco C6 S.A.</td><td>336</td><td>C6</td><td>BR</td></tr>
    <tr><td>Banco XP S.A.</td><td>348</td><td>XP</td><td>BR</td></tr>
    <tr><td>Banco Safra S.A.</td><td>422</td><td>SAFRA</td><td>BR</td></tr>
    <tr><td>Banco Pan S.A.</td><td>623</td><td>PAN</td><td>BR</td></tr>
    <tr><td>Banco Votorantim S.A.</td><td>655</td><td>BV</td><td>BR</td></tr>
    <tr><td>Itaú Unibanco S.A.</td><td>341</td><td>ITAU</td><td>BR</td></tr>
    <tr><td>Banco Bradesco S.A.</td><td>237</td><td>BBDC</td><td>BR</td></tr>
    <tr><td>Banco Crefisa S.A.</td><td>069</td><td>CREFISA</td><td>BR</td></tr>
    <tr><td>Banco BMG S.A.</td><td>318</td><td>BMG</td><td>BR</td></tr>
    <tr><td>Banco Daycoval S.A.</td><td>707</td><td>DAYCOVAL</td><td>BR</td></tr>
    <tr><td>Banco Santander S.A.</td><td>033</td><td>SAN</td><td>BR</td></tr>
    <tr><td>Banco do Estado do Rio Grande do Sul S.A.</td><td>041</td><td>BANRISUL</td><td>BR</td></tr>
    <tr><td>Banco Original S.A.</td><td>212</td><td>ORIG</td><td>BR</td></tr>
    <tr><td>Nubank</td><td>260</td><td>NU</td><td>BR</td></tr>
  </tbody>
</table>

```

<br />

```json
[
  {
    "name": "Banco do Brasil S.A.",
    "code": "001",
    "country": "BR",
    "acronym": "BB",
    "pay_with_your_bank": 0
  },
  {
    "name": "Banco BRB",
    "code": "070",
    "country": "BR",
    "acronym": "BRB",
    "pay_with_your_bank": 0
  },
  {
    "name": "Caixa Econômica Federal",
    "code": "104",
    "country": "BR",
    "acronym": "CEF",
    "pay_with_your_bank": 0
  },
  {
    "name": "Banco Inter S.A.",
    "code": "077",
    "country": "BR",
    "acronym": "INTER",
    "pay_with_your_bank": 0
  },
  {
    "name": "Sicredi",
    "code": "748",
    "country": "BR",
    "acronym": "SIC",
    "pay_with_your_bank": 0
  },
  {
    "name": "Banco Cooperativo Sicoob S.A.",
    "code": "756",
    "country": "BR",
    "acronym": "SICOOB",
    "pay_with_your_bank": 0
  },
  {
    "name": "Goldman Sachs do Brasil",
    "code": "064",
    "country": "BR",
    "acronym": "GS",
    "pay_with_your_bank": 0
  },
  {
    "name": "Banco Inbursa S.A.",
    "code": "012",
    "country": "BR",
    "acronym": "INB",
    "pay_with_your_bank": 0
  },
  {
    "name": "Banco do Nordeste do Brasil S.A.",
    "code": "004",
    "country": "BR",
    "acronym": "BNB",
    "pay_with_your_bank": 0
  },
  {
    "name": "PicPay Bank S.A.",
    "code": "380",
    "country": "BR",
    "acronym": "PICPAY",
    "pay_with_your_bank": 0
  },
  {
    "name": "Banco Agibank S.A.",
    "code": "121",
    "country": "BR",
    "acronym": "AGI",
    "pay_with_your_bank": 0
  },
  {
    "name": "Paraná Banco S.A.",
    "code": "254",
    "country": "BR",
    "acronym": "PB",
    "pay_with_your_bank": 0
  },
  {
    "name": "Banco Mercantil do Brasil S.A.",
    "code": "389",
    "country": "BR",
    "acronym": "BMB",
    "pay_with_your_bank": 0
  },
  {
    "name": "Banco Digio S.A.",
    "code": "335",
    "country": "BR",
    "acronym": "DIGIO",
    "pay_with_your_bank": 0
  },
  {
    "name": "Banco do Estado do Espírito Santo S.A.",
    "code": "021",
    "country": "BR",
    "acronym": "BANESTES",
    "pay_with_your_bank": 0
  },
  {
    "name": "Banco BTG Pactual S.A.",
    "code": "208",
    "country": "BR",
    "acronym": "BTG",
    "pay_with_your_bank": 0
  },
  {
    "name": "Banco C6 S.A.",
    "code": "336",
    "country": "BR",
    "acronym": "C6",
    "pay_with_your_bank": 0
  },
  {
    "name": "Banco XP S.A.",
    "code": "348",
    "country": "BR",
    "acronym": "XP",
    "pay_with_your_bank": 0
  },
  {
    "name": "Banco Safra S.A.",
    "code": "422",
    "country": "BR",
    "acronym": "SAFRA",
    "pay_with_your_bank": 0
  },
  {
    "name": "Banco Pan S.A.",
    "code": "623",
    "country": "BR",
    "acronym": "PAN",
    "pay_with_your_bank": 0
  },
  {
    "name": "Banco Votorantim S.A.",
    "code": "655",
    "country": "BR",
    "acronym": "BV",
    "pay_with_your_bank": 0
  },
  {
    "name": "Itaú Unibanco S.A.",
    "code": "341",
    "country": "BR",
    "acronym": "ITAU",
    "pay_with_your_bank": 0
  },
  {
    "name": "Banco Bradesco S.A.",
    "code": "237",
    "country": "BR",
    "acronym": "BBDC",
    "pay_with_your_bank": 0
  },
  {
    "name": "Banco Crefisa S.A.",
    "code": "069",
    "country": "BR",
    "acronym": "CREFISA",
    "pay_with_your_bank": 0
  },
  {
    "name": "Banco BMG S.A.",
    "code": "318",
    "country": "BR",
    "acronym": "BMG",
    "pay_with_your_bank": 0
  },
  {
    "name": "Banco Daycoval S.A.",
    "code": "707",
    "country": "BR",
    "acronym": "DAYCOVAL",
    "pay_with_your_bank": 0
  },
  {
    "name": "Banco Santander S.A.",
    "code": "033",
    "country": "BR",
    "acronym": "SAN",
    "pay_with_your_bank": 0
  },
  {
    "name": "Banco do Estado do Rio Grande do Sul S.A.",
    "code": "041",
    "country": "BR",
    "acronym": "BANRISUL",
    "pay_with_your_bank": 0
  },
  {
    "name": "Banco Original S.A.",
    "code": "212",
    "country": "BR",
    "acronym": "ORIG",
    "pay_with_your_bank": 0
  },
  {
    "name": "Nubank",
    "code": "260",
    "country": "BR",
    "acronym": "NU",
    "pay_with_your_bank": 0
  }
]

```

<br />

***

## Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, también puedes hacer pruebas con [nuestros demos](https://demo.insospa.com/transactions/deposit).

***

## Certifica tu integración

La certificación de la integración en _sandbox_ es un paso obligatorio que todos los comercios deben realizar antes de recibir sus credenciales de producción. Su propósito es asegurar que la integración cumpla con los estándares técnicos, funcionales y de seguridad requeridos por ProntoPaga. Dentro de esta sección, se establecen los requisitos que deben cumplirse sin excepción para que la certificación sea aprobada.

### Requisitos de certificación

A continuación, encontrarás los distintos requisitos necesarios para completar tu certificación:

<br />

<Tabs>
  <Tab title="ID del cliente">
    * ❌ El documento de identidad del cliente no debe ser modificable en ningún punto de la transacción.
    * ✅ Es recomendable que este dato no se muestre en el *checkout*. Solo puede estar disponible en la sección de perfil del usuario autenticado.
    * ⚠️ Esta medida tiene como objetivo prevenir fraudes y evitar que se realicen transacciones en nombre de terceros o menores de edad.
  </Tab>

  <Tab title="Logotipos">
    * 📥 Agregar los logotipos de los diferentes métodos de retiro de ProntoPaga a tu *front-end*. Puedes [descargarlos aquí](https://drive.google.com/uc?export=download\&id=1MmsVaugP7ztzRXA_dK9wNrwKJOfHSL59).
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
