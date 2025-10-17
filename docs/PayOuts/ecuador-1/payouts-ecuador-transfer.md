---
title: Retiros por Transferencia
excerpt: Conoce el paso a paso de cómo hacer un retiro por transferencia en Ecuador.
deprecated: false
hidden: false
metadata:
  title: Retiros por Transferencia | ProntoPaga Docs
  description: >-
    To make a payout in Ecuador via bank transfer, capture the recipient's
    information and send a request via the API. This guide explains the
    withdrawal flow, required parameters, webhook confirmation, and how to
    simulate transactions in a test environment. 
  image: >-
    https://files.readme.io/94fe2ba4a30f9e23130f6ddd7378efb1a4b41ecbdfa1306513b27dafd47c9d90-Prontopaga_logotipo.png
  keywords:
    - bank transfer Ecuador
    - transfer payout
    - Ecuador wire transfer payout
    - how to make a wire transfer payout
    - Prontopaga
    - cómo hacer un payout Ecuador
    - hacer payout
    - retiros Prontopaga
  robots: index
next:
  description: ''
---
Hacer un retiro en Ecuador por medio de transferencia bancaria consiste en capturar los datos necesarios de la persona que recibirá el pago y hacer una solicitud a través de nuestra API con un Bearer Token y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.

***

<br />

## ¿Cómo funciona?

Transferencia es una forma de retirar fondos en Ecuador mediante transferencias bancarias. Para completar una transacción utilizando este método de retiro, el cliente debe seleccionar la opción "Transferencia Bancaria", ingresar su número de cuenta bancaria, seleccionar el banco, el tipo de cuenta, y confirmar la operación.

El proceso de Payout con transferencia en Ecuador consta de cuatro etapas principales:

<Image align="center" border={false} src="https://files.readme.io/e179fa877d2c9653fa04ffd4e76a1a6ddefcc1b2e1ea46d41c1a57dd31d3d8f3-Ecuador-02.jpg" />

1. **Selección de método.** El cliente elige retirar dinero por medio de transferencia en tu sitio web o aplicación.
2. **Ingreso de datos.** El cliente ingresa los datos necesarios para que el retiro sea realizado (como banco, número y tipo de cuenta) y confirma la transacción.
3. **Validación y Captura.** ProntoPaga valida la información del retiro, hace la solicitud de transferencia al banco y mueve el dinero desde la cuenta del comercio hacia la cuenta del cliente.
4. **Confirmación.** El cliente recibe una confirmación de retiro exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

***

<br />

## Lista de bancos

La lista de códigos bancarios para PayOuts de tipo transferencia la puedes encontrar en [este artículo](https://docs.prontopaga.com/docs/bank-codes-transfer), dividida por países. El código bancario debe enviarse en el campo `bankCode` del endpoint de creación de un retiro.

***

<br />

## Crea un nuevo retiro

Para hacer una solicitud de nuevo retiro a través de nuestra API deberás usar [este endpoint](https://docs.prontopaga.com/reference/payout). La solicitud se envía con tu Bearer Token, así como con tu secretKey.

<NotaFirma />

Además, debes incluir los datos necesarios del cliente al que le mandarás el dinero, como: nombre, apellido, correo electrónico, teléfono, ID, cuenta, entre otros.

<NotaWebhooks />

<br />

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "amount": "25.90",
  "document_id": "12345678912",
  "beneficiaryName": "John",
  "beneficiaryLastName": "Doe",
  "beneficiaryEmail": "johndoe@example.com",
  "beneficiaryPhone": "999999999",
  "accountNumber": "10070010030000",
  "accountType": "AHO",
  "accountType_id": "P",
  "bankCode": "10",
  "data": "XYZ789",
  "confirmationURL": "https://www.webhook.com",
  "currency": "USD",
  "country": "EC",
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
