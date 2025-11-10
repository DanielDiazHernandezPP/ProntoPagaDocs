---
title: Recibe pagos con QR
excerpt: Conoce el paso a paso de cómo crear un pago con QR en Perú.
deprecated: false
hidden: false
metadata:
  title: Recibe pagos con QR | ProntoPaga Docs
  description: >-
    Learn how to create QR payments in Peru using the Prontopaga API. This guide
    covers the payment flow, API requests, test data, and webhook confirmation
    process.
  image: >-
    https://files.readme.io/329c05b4f9ab2db95dc597445b1674784ae56c6d25c7bc9d6530709733295c30-Prontopaga_logotipo.png
  keywords:
    - QR payments Peru
    - Prontopaga QR Peru
    - how to make a QR payment in Peru
    - create QR payments Peru
    - use QR Prontopaga Peru
    - Yape QR
    - Plin QR
  robots: index
next:
  description: ''
---
Crear un pago en Perú con QR consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un Bearer Token y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.

Además, todas tus transacciones cuentan con la herramienta automatizada Decision Manager (DM) del motor de gestión de riesgos y prevención de fraude de **Cybersource (A Visa Solution)**.

**Hay dos formas de integrar este método en tu comercio:**

* [QR con interfaz estándar (flujo completo)](https://docs.prontopaga.com/docs/payins-peru-qr#qr-con-interfaz-est%C3%A1ndar-flujo-completo): Para quienes desean usar nuestra interfaz ya construida, en donde se genera y se muestra el QR automáticamente al usuario final. Incluye experiencia visual y seguimiento del estado del pago.
* [QR embebido (solo datos QR)](https://docs.prontopaga.com/docs/payins-peru-qr#qr-embebido-solo-datos-qr): Para quienes necesitan solo el código QR en formato base64, para integrarlo en su interfaz personalizada. Ideal si tienes tu propio front-end o flujo de usuario, y solo necesitas el QR para mostrarlo en donde prefieras.

***

## QR con interfaz estándar (flujo completo)

Para quienes buscan una integración práctica y eficiente, contamos con una interfaz completamente lista para usar, que genera y muestra automáticamente el código QR al usuario final. Esta solución ofrece una experiencia visual atractiva, además de permitir hacer el monitoreo en tiempo real del estado del pago, facilitando así una implementación rápida sin comprometer la calidad ni la experiencia del usuario.

***

## ¿Cómo funciona?

Los pagos con QR son una forma de pago digital utilizada en Perú que permite realizar transacciones escaneando un código QR desde una aplicación de billetera digital en el celular. Para utilizar este método, el cliente debe seleccionar la opción "Paga con QR", tener una cuenta activa en una billetera digital compatible y aprobar la transacción desde su aplicación. Para conocer el listado de billeteras disponibles, puedes consultarlo [aquí](https://docs.prontopaga.com/docs/payins-peru-qr#listado-de-wallets).

El proceso de pago con QR en Perú consta de cuatro etapas principales:

<Image align="center" border={false} src="https://files.readme.io/b2e065728089a44d6cc0c2806bd8eb118b1f570b023d80dabb029066cf433682-peru_-_05.jpg" />

1. **Selección de método.** El cliente elige pagar con QR en tu sitio web o aplicación.
2. **Generación del QR.** ProntoPaga le entrega un QR único al cliente, el cual podrá escanear con la aplicación de la wallet con la que pagará.
3. **Pago en aplicación.** El cliente abre la aplicación de su wallet, escanea el código QR y hace el pago. El dinero se mueve desde la wallet del cliente hacia la cuenta de tu comercio.
4. **Confirmación.** El cliente recibe una confirmación de pago exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación del pago a través de los webhooks que hayas configurado.

***

## Crea un nuevo pago (flujo completo)

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `pe_qr_payment` como método de pago en el body de la solicitud.

La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros.

<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

<NotaWebhooks />

### Personalización del formulario

Puedes ajustar la apariencia de tu formulario con el parámetro `theme` cambiando el color de fondo o creando versiones modo claro y modo oscuro.

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "currency": "PEN",
  "country": "PE",
  "amount": "100.90",
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "12345678912",
  "paymentMethod": "pe_qr_3_payment",
  "urlConfirmation": "https://www.webhook.com",
  "urlFinal": "https://sandbox.prontopaga.com/successful",
  "urlRejected": "https://sandbox.prontopaga.com/declined",
  "order": "XYZ789",
  "sign": "Signature of the parameters"
}
```

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un enlace para procesar el pago, así como un identificador de pago del sistema.

### Confirmación de un pago

Una vez que el usuario haya completado el proceso de pago en el formulario, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los PayIns](https://docs.prontopaga.com/docs/payins-status).

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

### Cancelar un pago con QR

Si un cliente generó un QR y le tomó captura de pantalla, pero no realizó el pago al momento, puedes cancelar ese QR para evitar que el cliente intente pagar más tarde con la imagen del QR.

Para cancelarlo, deberás consultar [este endpoint](https://docs.prontopaga.com/reference/cancel-qr-peru) con tu `Bearer Token` y mandar el `uid` del pago en la URL de la solicitud.

### Personalizar el formulario de pago

Para modificar el estilo del formulario de pago, usa este <Anchor label="endpoint" target="_blank" href="https://docs.prontopaga.com/reference/create-payment#/">endpoint</Anchor>. A continuación, se muestra un ejemplo del body request:

```json
{
  "currency": "PEN",
  "country": "PE",
  "amount": "100.90",
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "12345678912",
  "paymentMethod": "pe_qr_3_payment",
  "urlConfirmation": "https://www.webhook.com",
  "urlFinal": "https://sandbox.prontopaga.com/successful",
  "urlRejected": "https://sandbox.prontopaga.com/declined",
  "order": "XYZ789",
  "theme": {
    "bgColor": "transparent", 
    "mode": "dark"
	},
  "sign": "Signature of the parameters"
}
```

***

## QR embebido (solo datos QR)

Si únicamente requieres el código QR en formato base64, esta opción es perfecta para ti. Está pensada especialmente para quienes ya cuentan con una interfaz personalizada o un flujo de usuario propio, y solo necesitan incorporar la imagen del QR en el lugar que más les convenga. Es una solución ideal si ya tienes resuelto el front-end y buscas simplemente insertar el QR sin complicaciones adicionales.

> 🚧 Monto no precargado
>
> Esta modalidad no carga automáticamente el monto en la wallet, por lo tanto, el cliente debe ingresarlo de manera manual.

***

## Crea un nuevo pago (solo datos QR)

En esta modalidad, al hacer una solicitud de pago y mandar dentro del `"theme"` el parámetro `"type": "qr"`, los comercios recibirán en la respuesta de la solicitud el código QR, el cual podrán presentar directamente en su página web o aplicación, dentro de una etiqueta IMG.

De este modo, para crear una solicitud de nuevo pago con este formato, deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `pe_qr_payment` como método de pago en el body de la solicitud.

La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros.

<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

<NotaWebhooks />

### Solicitar el QR

Para recibir el código QR en la respuesta, deberás usar el parámetro de personalización `"theme"` y mandar el parámetro `"type": "qr"`, tal como se muestra en el ejemplo del body de la solicitud.

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "currency": "PEN",
  "country": "PE",
  "amount": "100.90",
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "12345678912",
  "paymentMethod": "pe_qr_3_payment",
  "urlConfirmation": "https://www.webhook.com",
  "urlFinal": "https://sandbox.prontopaga.com/successful",
  "urlRejected": "https://sandbox.prontopaga.com/declined",
  "order": "XYZ789",
  "theme": "{\"type\":\"qr\"}",
  "sign": "Signature of the parameters"
}
```

### Respuesta

Como respuesta a una solicitud de pago exitosa recibirás el enlace para procesar el pago, un identificador de pago del sistema y el código QR, el cual podrás insertar directamente en tu página web o aplicación, usando una etiqueta IMG.

#### Ejemplo de respuesta para pago exitoso

```json
{
    "urlPay": "https://prontopaga.com/payment/rest/01JRAZYTH4A55JB5R9GQ",
    "uid": "01JRAZYTH4A55JB59GQ",
    "reference": "1743461",
    "height": {
        "desktop": {
            "width": "500px",
            "height": "730px"
        },
        "mobile": {
            "width": "100%",
            "height": "730px"
        }
    },
    "qrCode": "data:image/png;base64,code"
}
```

### Confirmación de un pago

Una vez que el usuario haya completado el proceso de pago en el formulario, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los PayIns](https://docs.prontopaga.com/docs/payins-status).

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

### Cancelar un pago con QR

Si un cliente generó un QR y le tomó captura de pantalla, pero no realizó el pago al momento, puedes cancelar ese QR para evitar que el cliente intente pagar más tarde con la imagen del QR.

Para cancelarlo, deberás consultar [este endpoint](https://docs.prontopaga.com/reference/cancel-qr-peru) con tu `Bearer Token` y mandar el `uid` del pago en la URL de la solicitud.

***

## Listado de wallets

Este es un listado de las wallets disponibles para hacer pagos con QR en Perú:

* Yape
* Plin
* Wayki
* Financiera Efectiva

***

## Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, puedes hacer pruebas con nuestros demos:

<Embed typeOfEmbed="iframe" url="https://experience.prontopaga.com/" href="https://experience.prontopaga.com/" html="false" iframe="true" height="1000px" width="100%" />

***

## Certifica tu integración

La certificación de la integración en _sandbox_ es un paso obligatorio que todos los comercios deben realizar antes de recibir sus credenciales de producción. Su propósito es asegurar que la integración cumpla con los estándares técnicos, funcionales y de seguridad requeridos por ProntoPaga. Dentro de esta sección, se establecen los requisitos que deben cumplirse sin excepción para que la certificación sea aprobada.

## Requisitos de certificación

A continuación, encontrarás los distintos requisitos necesarios para completar tu certificación:

<Tabs>
  <Tab title="ID del cliente">
    * ❌ El documento de identidad del cliente no debe ser modificable en ningún punto de la transacción.
    * ✅ Es recomendable que este dato no se muestre en el *checkout*. Solo puede estar disponible en la sección de perfil del usuario autenticado.
    * ⚠️ Esta medida tiene como objetivo prevenir fraudes y evitar que se generen transacciones realizadas por menores de edad o a su nombre.
  </Tab>

  <Tab title="Logotipos">
    * 📥 Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu *front-end*. Puedes [descargarlos aquí](https://drive.google.com/uc?export=download\&id=1eOgEauFj0qIs0JXq0WHpAWWQOYkc9Vn3).
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

<br />
