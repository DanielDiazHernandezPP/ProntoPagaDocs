---
title: Retiros con Wallet Payphone
excerpt: Conoce el paso a paso de cómo hacer un retiro con wallet en Ecuador.
deprecated: false
hidden: false
metadata:
  title: Retiros con Wallet Payphone | ProntoPaga Docs
  description: >-
    Learn how to create a payout to a digital wallet in Ecuador using the
    Prontopaga API. This guide covers recipient data capture, authentication
    with bearer token and secret signature, response handling, and webhook
    confirmation.
  image: >-
    https://files.readme.io/f9bddb237fbd699006ff0b0ad028f15cba2733c44cf05c10ed0308f509e4ac51-Prontopaga_logotipo.png
  keywords:
    - wallet payout Ecuador
    - Prontopaga payout Ecuador
    - send money to wallet Ecuador
    - API wallet transfer Ecuador
    - digital wallet withdrawal Ecuador
  robots: index
next:
  description: ''
---
Hacer un retiro a una wallet en Ecuador consiste en capturar los datos necesarios de la persona que recibirá el pago y hacer una solicitud a través de nuestra API con un Bearer Token y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.

***

## ¿Cómo funciona?

Payphone es una billetera digital ecuatoriana que permite recibir pagos, administrar dinero y realizar transacciones desde el celular. Para completar una transacción utilizando este método de retiro, el cliente debe seleccionar la opción "Retiro con Payphone", ingresar su número de teléfono registrado con la cuenta y confirmar la operación.

El proceso de PayOut con Wallet Payphone consta de cuatro etapas principales:

<Image align="center" border={false} src="https://files.readme.io/48d4a30ebbdf1146be448659c39934c68d582a110dbe367a3eef6d9f51cbb84b-Ecuador-03.jpg" />

1. **Selección de método.** El cliente elige retirar dinero por medio de wallet (Payphone) en tu sitio web o aplicación.
2. **Ingreso de datos.** El cliente ingresa los datos necesarios para que el retiro sea realizado y confirma la transacción.
3. **Validación y Captura.** ProntoPaga valida la infomación del retiro, hace la solicitud y mueve el dinero desde la cuenta del comercio hacia la cuenta Payphone del cliente.
4. **Confirmación.** El cliente recibe una confirmación de retiro exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

***

## Crea un nuevo retiro

Para hacer una solicitud de nuevo retiro a través de nuestra API deberás usar [este endpoint](https://docs.prontopaga.com/reference/payout-ecuador-payphone). La solicitud se envía con tu Bearer Token, así como con tu secretKey.

<NotaFirma />

Además, debes incluir los datos necesarios del cliente al que le mandarás el dinero, como: nombre, apellido, correo electrónico, teléfono, ID, entre otros.

<NotaWebhooks />

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
  "accountType": "C",
  "data": "XYZ789",
  "confirmationURL": "https://www.webhook.com",
  "currency": "USD",
  "country": "EC",
  "sign": "Signature of the parameters"
}
```

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un identificador del retiro en el sistema, el estado del retiro y datos adicionales de la transacción.

### Confirmación de un retiro

Una vez que hayas completado el proceso, ProntoPaga devolverá los datos de la transacción a la URL que especificaste en `confirmationURL`.

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un retiro en el siguiente enlace: [Estados de los PayOuts](https://docs.prontopaga.com/docs/payouts-status).

***

## Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, también puedes hacer pruebas con [nuestros demos](https://demo.insospa.com/transactions/deposit).

***

## Certifica tu integración

La certificación de la integración en _sandbox_ es un paso obligatorio que todos los comercios deben realizar antes de recibir sus credenciales de producción. Su propósito es asegurar que la integración cumpla con los estándares técnicos, funcionales y de seguridad requeridos por ProntoPaga. Dentro de esta sección, se establecen los requisitos que deben cumplirse sin excepción para que la certificación sea aprobada.

### Requisitos de certificación

A continuación, encontrarás los distintos requisitos necesarios para completar tu certificación:

<Tabs>
  <Tab title="ID del cliente">
    * ❌ El documento de identidad del cliente no debe ser modificable en ningún punto de la transacción.
    * ✅ Es recomendable que este dato no se muestre en el *checkout*. Solo puede estar disponible en la sección de perfil del usuario autenticado.
    * ⚠️ Esta medida tiene como objetivo prevenir fraudes y evitar que se realicen transacciones en nombre de terceros o menores de edad.
  </Tab>

  <Tab title="Logotipos">
    * 📥 Agregar los logotipos de los diferentes métodos de retiro de ProntoPaga a tu *front-end*. Puedes [descargarlos aquí](https://prontopagalatam-my.sharepoint.com/:u:/g/personal/tahbet_reategui_prontopaga_com/EWC1ijJHq5JKnjpIH9qH0ncBOMEiK2wrNPdxkTdVmyZ7Kg?e=SCuGY4\&download=1).
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
