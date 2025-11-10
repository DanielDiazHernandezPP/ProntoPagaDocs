---
title: Acepta pagos con Tarjeta (Payphone)
excerpt: Conoce el paso a paso de cómo crear un pago con tarjeta en Ecuador.
deprecated: false
hidden: false
metadata:
  title: Acepta pagos con Tarjeta (Payphone) | ProntoPaga Docs
  description: >-
    Guide to create a secure card payment in Ecuador using Payphone, involving
    data capture, API requests with authentication, and transaction
    confirmation, while utilizing Cybersource's fraud prevention tools. How to
    integrate the payment system, including necessary data, endpoints, and
    testing procedures. 
  image: >-
    https://files.readme.io/57d893b6bf89e9f7573bd836d536b267ed16c3824d88b1b3d8f8e00d0b1590fb-Prontopaga_logotipo.png
  keywords:
    - payins ecuador
    - ecuador payphone card payments
    - how to make a card payment payphone
    - prontopaga payphone
    - como pagar con tarjeta en ecuador
    - Payphone Ecuador
  robots: index
next:
  description: ''
---
Crear un pago con tarjeta (Payphone) en Ecuador consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un Bearer Token y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.

Además, todas tus transacciones cuentan con la herramienta automatizada Decision Manager (DM) del motor de gestión de riesgos y prevención de fraude de **Cybersource (A Visa Solution)**.

***

<br />

## ¿Cómo funciona?

PayPhone es un método de pago en línea utilizado en Ecuador que permite recibir pagos con tarjetas Visa o Mastercard, de crédito o débito, de cualquier banco. Para completar una transacción utilizando este método de pago, el cliente debe ingresar los datos de su tarjeta (número, fecha de expiración y código CVV).

El proceso de pago con tarjeta (Payphone) en Ecuador consta de cinco etapas principales:

<Image align="center" border={false} src="https://files.readme.io/af15b14a7884f57ab27b9df13f97087233bfe5c854f2af06fbcaa6722a2fa7be-Payment_witch_card_-_Ecuador.jpg" />

1. **Selección de método.** El cliente elige pagar con tarjeta en tu sitio web o aplicación.
2. **Ingreso de datos.** El cliente llena los datos requeridos en el formulario de pago con tarjeta, como: número de tarjeta, fecha de vencimiento, CVV, nombre y correo electrónico.
3. **Validación de datos.** Se verifican los datos con el emisor de la tarjeta.
4. **Autorización y Captura.** Se verifica que existan los fondos suficientes, y se mueven desde el banco del cliente hacia la cuenta de tu comercio.
5. **Confirmación.** El cliente ve en pantalla el resultado de la transacción. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

***

<br />

## Crea un nuevo pago

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar  `ec_card_payment` como método de pago en el body de la solicitud.

La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros.

<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

<NotaWebhooks />

<br />

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "currency": "USD",
  "country": "EC",
  "amount": "25.90",
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "0912345678",
  "clientDocument": "12345678912",
  "paymentMethod": "ec_card_payment",
  "urlConfirmation": "https://www.webhook.com",
  "urlFinal": "https://sandbox.prontopaga.com/successful",
  "urlRejected": "https://sandbox.prontopaga.com/declined",
  "order": "XYZ789",
  "sign": "Signature of the parameters"
}
```

<br />

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un enlace para procesar el pago, así como un identificador de pago del sistema.

<br />

### Confirmación de un pago

Una vez que el usuario haya completado el pago, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los PayIns](https://docs.prontopaga.com/docs/payins-status) .

> ❗️ Incompatibilidad con iFrame
>
> Ten en cuenta que este método de pago no es compatible con el uso de iFrame.

<br />

### Devolución de un pago

Para solicitar la devolución de un pago exitoso realizado con este método, usa [este endpoint](https://docs.prontopaga.com/reference/refunds). A continuación, se muestra un ejemplo del body request que debe llevar:

```json
{
  "reference": "1111111111",
  "clientDocument": "12345678912",
  "amount": "100.90",
  "urlCallbackRefund": "https://www.webhook.com",
  "sign": "Signature of the parameters"
}
```

***

<br />

## Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, puedes hacer pruebas con nuestros demos:

<Embed url="https://experience.prontopaga.com/" href="https://experience.prontopaga.com/" typeOfEmbed="iframe" height="1000px" width="100%" iframe="true" html="false" />

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
    * 📥 Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu *front-end*. Puedes [descargarlos aquí](https://drive.google.com/uc?export=download&id=1eOgEauFj0qIs0JXq0WHpAWWQOYkc9Vn3).
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
