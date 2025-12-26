---
title: Retira instántaneos con Pix
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

<br />

### Confirmación de un retiro

Una vez que hayas completado el proceso, ProntoPaga devolverá los datos de la transacción a la URL que especificaste en `confirmationURL`.

Para confirmar si una transacción fue exitosa, debes verificar que en tu _webhook_ el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un retiro en el siguiente enlace: [Estados de los PayOuts](https://docs.prontopaga.com/docs/payouts-status).

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
    * 📥 Agregar los logotipos de los diferentes métodos de retiro de ProntoPaga a tu *front-end*. Puedes [descargarlos aquí](https://prontopagalatam-my.sharepoint.com/:f:/g/personal/tahbet_reategui_prontopaga_com/EtPhXrMz3TxAtA11de5jVZEB3yowkpS1i2v6lm_eMKkB7g?e=KXcZX5).
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
