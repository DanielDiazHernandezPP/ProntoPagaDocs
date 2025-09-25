---
title: Recibe pagos con QR (COPY)
deprecated: false
hidden: true
metadata:
  title: Recibe pagos con QR | ProntoPaga Docs
  description: >-
    Learn how to create QR payments in Chile using the Prontopaga API. Includes
    payment flow, API request, test data, and webhook confirmation process.
  image: >-
    https://files.readme.io/e7102ae1763d4239412e57076b3ac3f6c760e58fb6caffb099e5205ff816db72-Prontopaga_logotipo.png
  keywords:
    - QR payments Chile
    - Prontopaga QR Chile
    - how to make a QR payment in Chile
    - crear pagos con QR Chile
    - usar QR Prontopaga Chile
  robots: index
---
Crear un pago por QR en Chile consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un Bearer Token y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.

Además, todas tus transacciones cuentan con la herramienta automatizada Decision Manager (DM) del motor de gestión de riesgos y prevención de fraude de **Cybersource (A Visa Solution)**.

***

<br />

## ¿Cómo funciona?

MACH y Mercado Pago son billeteras digitales utilizadas en Chile que permiten realizar pagos en línea a través de sus aplicaciones. Para completar una transacción utilizando estos métodos de pago, el cliente debe seleccionar la opción "Paga con QR/Wallet - MACH" o "Paga con QR/Wallet - MercadoPago", tener una cuenta creada con saldo disponible o un medio de pago vinculado, y aprobar el pago desde la aplicación.

El proceso de pago con QR en Chile consta de cuatro etapas principales:

<Image align="center" border={false} src="https://files.readme.io/fc447752eb33caef4a4ec1b20e70f55f4e25426e66b742a21046149de4a7ed65-Chile-05.jpg" />

1. **Selección de método.** El cliente elige pagar con QR a través de una wallet en tu sitio web o aplicación.

<Callout icon="📘" theme="info">
  **Selección de método versión mobile 📱**

  Si se detecta que el dispositivo del cliente es mobile, se mostrarán dos botones con las opciones de pago:

  1. MACH
  2. BCI 

  El cliente elegirá según sus preferencias y se abrirá la aplicación correspondiente.

  _Esto solo ocurre cuando el cliente selecciona la opción "Paga con QR/Wallet - MACH"._
</Callout>

2. **Generación del QR.** ProntoPaga le entrega un QR único al cliente, el cual podrá escanear con la aplicación de la wallet con la que pagará.

En el caso de **MACH**, el flujo varía dependiendo de la versión utilizada:

<Cards columns={2}>
  <Card title="🌐 En web">
    Se genera un QR para que el cliente lo escaneé y es redirigido a la web para continuar con el pago.
  </Card>

  <Card title="📱En mobile">
    Se abre la aplicación de MACH y se valida al cliente a través de biometría o PIN para continuar con el pago.
  </Card>
</Cards>

3. **Pago en aplicación.** El cliente abre la aplicación de su wallet, escanea el código QR y hace el pago. El dinero se mueve desde la wallet del cliente hacia la cuenta de tu comercio.
4. **Confirmación.** El cliente recibe una confirmación de pago exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación del pago a través de los webhooks que hayas configurado.

En el caso de **MACH**, el flujo varía dependiendo de la versión utilizada:

<Cards columns={2}>
  <Card title="🌐 En web">
    El cliente finaliza el pago dentro del navegador para obtener la confirmación de pago exitoso, y a su vez, tu comercio recibe la confirmación del pago a través de los webhooks que hayas configurado.
  </Card>

  <Card title="📱En mobile">
    La confirmación de pago exitoso ocurre dentro de la aplicación, y a su vez tu comercio recibe la confirmación del pago a través de los webhooks que hayas configurado.
  </Card>
</Cards>

***

<br />

## Crea un nuevo pago

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `mercadopagoqr_payment` o `mach_payment` según sea el caso, como método de pago en el body de la solicitud.

La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros.

<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

<NotaWebhooks />

<br />

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "currency": "CLP",
  "country": "CL",
  "amount": "25500",
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "11111111-1",
  "paymentMethod": "mach_payment",
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

Una vez que el usuario haya completado el proceso de pago en el formulario, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los PayIns](https://docs.prontopaga.com/docs/payins-status).

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
    * 📥 Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu *front-end*. Puedes [descargarlos aquí](https://prontopagalatam-my.sharepoint.com/:u:/g/personal/tahbet_reategui_prontopaga_com/ESSezIFfGzxArH2s5zmajoEBkGiSmK6xkxjh7bLDhFOGzg?e=SVAXYW\&download=1).
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
