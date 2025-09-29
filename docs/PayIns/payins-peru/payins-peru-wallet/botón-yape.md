---
title: Botón Yape v1
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Botón Yape v1 | ProntoPaga Docs
  description: >-
    Integrate secure wallet payments in Peru using ProntoPaga’s API and the Yape
    app. Capture customer data, authenticate with bearer token and secretKey,
    and support flows via iFrame or full API. Confirm transactions via webhook
    and test with sandbox data.
  image: >-
    https://files.readme.io/2d0fa5f2c1fa12d2f9d9b6f7eee64d73d70918f7de0815a7b98a0fc2cb01d28f-Prontopaga_logotipo.png
  keywords:
    - Yape wallet payment Peru
    - ProntoPaga API
    - integrate Yape
    - pay with Yape
    - wallet integration Peru
    - Yape One Shot
    - wallet checkout Peru
    - pagar con Yape Perú
    - integrar Yape Perú
  robots: index
next:
  description: ''
---
Crear un pago por wallet en Perú consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un Bearer Token y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.

***

## ¿Cómo funciona?

Yape es una aplicación que permite realizar pagos y transferencias de dinero en Perú, utilizando solo el número de celular. Con Yape, los usuarios pueden hacer pagos en línea, recargar saldo en su cuenta o realizar compras en comercios afiliados. Para completar una transacción utilizando este método de pago, el cliente debe seleccionar la opción "Paga con Yape", tener una cuenta creada y aprobar la compra desde su aplicación.

El proceso de pago con wallet en Perú consta de cinco etapas principales:

<Image align="center" border={false} src="https://files.readme.io/933d0090646d5cc0354e287b4d84eccd245130527f44959c81db060d5744af76-peru_-_04.jpg" />

1. **Selección de método.** El cliente elige pagar con wallet (Yape) en tu sitio web o aplicación.
2. **Solicitud.** ProntoPaga se comunica con la wallet y genera la solicitud de pago.
3. **Aprobación.** Se le solicita al cliente un código de aprobación. Puede ingresar a su aplicación a través de un botón de acceso rápido, obtener el código y luego ingresarlo para aprobar el pago.
4. **Validación.** ProntoPaga valida que el código sea correcto. En caso de serlo, se hace el pago y el dinero se mueve desde la wallet del cliente hacia la cuenta de tu comercio.
5. **Confirmación.** El cliente es redirigido a tu sitio y se muestra el resultado de la transacción. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

***

## Integración de Yape

Es posible integrar el servicio de pago con Botón Yape de dos formas en ProntoPaga:

* Usando nuestro iFrame para el front-end.
* Vía 100% API, sin usar nuestro iFrame (tu comercio tendrá el manejo total del front-end del checkout).

***

## Validación pago terceros

ProntoPaga cuenta con un servicio de validación de pago de terceros, el cual confirma que el número de teléfono celular ingresado coincida con los datos de la cuenta del cliente, evitando que se realicen pagos de terceros, y maximizando la seguridad de tus transacciones.

Esta validación se asigna de forma automática a ciertos comercios integrados con nosotros. Si deseas activarla o desactivarla, comunícate con nuestro equipo de integración. Toma en cuenta las diferencias que existen en la experiencia del cliente para cada caso. Esas diferencias están descritas en la sección de **¿Cómo funciona?** de este artículo, en la parte superior.

### Motivos de rechazo de validación pago terceros

A continuación, se listan los posibles motivos de validación pago terceros, así como los mensajes que se mostrarán.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Motivo</b></th>
      <th><b>Mensaje</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>El número de celular y el documento de identidad no están asociados.</td><td><code>The user's phone number and identity document do not match</code></td></tr>
    <tr><td>El usuario no tiene una cuenta de Yape activa.</td><td><code>The user does not have an active Yape account</code></td></tr>
    <tr><td>El tipo de documento de identidad proporcionado del servicio de validación es distinto al enviado por el comercio.</td><td><code>The Document Type provided by the validation service does not match the one sent by the Merchant</code></td></tr>
    <tr><td>El servicio de validación no está respondiendo correctamente.</td><td><code>The validation service is currently unavailable. Please try again, and if the error persists, contact your KAM</code></td></tr>
  </tbody>
</table>
`}</HTMLBlock>

***

## Crea un nuevo pago con iFrame

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `yape_payment` como método de pago en el body de la solicitud.

La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros.

<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

<NotaWebhooks />

### Personalización del formulario

Puedes ajustar la apariencia de tu formulario con el parámetro `theme` cambiando el color de fondo o creando versiones modo claro y modo oscuro.

<Image align="center" border={false} width="200px" src="https://files.readme.io/51e88becc4a1e257996cb45407d291f16c63f89f2a34baee995ee4a95f82c6ef-yapepersonaliz.png" />

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
  "paymentMethod": "yape_payment",
  "urlConfirmation": "https://www.webhook.com",
  "urlFinal": "https://sandbox.prontopaga.com/successful",
  "urlRejected": "https://sandbox.prontopaga.com/declined",
  "order": "XYZ789",
  "theme": "[{\"bgColor\": \"transparent\", \"mode\": \"dark\"}]",
  "sign": "Signature of the parameters"
}
```

> 🚧 Límite transaccional
>
> Recuerda que el límite máximo por transacción y por día es de 2000 soles. Esto significa que, si un cliente realiza hoy una compra por ese monto, no podrá hacer otra transacción hasta mañana.

### Pago en la wallet

El cliente podrá continuar el proceso siguiendo las instrucciones en pantalla. Se redireccionará al cliente al sitio web o aplicación de la wallet, en donde podrá iniciar sesión y hacer el pago.

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un enlace para procesar el pago, así como un identificador de pago del sistema.

### Confirmación de un pago

Una vez que el usuario haya completado el pago, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

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

***

## Crea un nuevo pago sin iFrame

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `yape_payment` como método de pago en el body de la solicitud.

La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros.

<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

<NotaWebhooks />

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
  "paymentMethod": "yape_payment",
  "urlConfirmation": "https://www.webhook.com",
  "urlFinal": "https://sandbox.prontopaga.com/successful",
  "urlRejected": "https://sandbox.prontopaga.com/declined",
  "order": "XYZ789",
  "sign": "Signature of the parameters"
}
```

### Procesa el pago

Para procesar el pago creado con el endpoint anterior (sin usar nuestro iFrame), deberás consultar [este endpoint](https://docs.prontopaga.com/reference/create-payment-peru-yape-api) y enviar el`uid` del pago recién creado como path paramether. Ese `uid` se recibe como respuesta en la solicitud de crear un pago.

La solicitud para procesar un pago se envía con tu Bearer Token. Además, debes incluir los datos necesarios del cliente para procesar el pago, como: teléfono del cliente y código OTP.

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "phoneNumber": "999999999",
  "otp": 123456
}
```

> 🚧 Número de teléfono
>
> Tu comercio ya tiene registrado el número de teléfono del usuario (tu cliente) al crear el pago. Por lo que en este paso, recomendamos que el campo de teléfono **no sea editable en tu front-end.** Por lo tanto, el número de teléfono que se envíe en el request de este endpoint debe ser el mismo que el usado al crear el pago.

### Respuesta

Como respuesta a una solicitud de procesamiento de pago exitosa recibirás el `uid`, el estatus del pago, así como el tipo de acción (en este caso, API).

En caso de ocurrir un error, nuestro sistema te enviaré el código y mensaje de error, el cual podrás mostrar en tu front-end.

> 🚧 Tipos de rechazo y datos de prueba
>
> Consulta los posibles tipos de rechazo para este método, su código y detalle en [esta página](https://docs.prontopaga.com/docs/payins-rejections#yape---primarios). Además, consulta los datos de prueba con diferentes escenarios [aquí.](https://docs.prontopaga.com/docs/test-data-cards-peru#bot%C3%B3n-yape)

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

### Recomendaciones generales para tu front-end

Si estás integrando pagos con Yape sin nuestro iFrame, estas son algunas recomendaciones generales que te damos para construir el front-end de tu checkout:

* Que el logo de Yape aparezca hasta arriba.
* Que haya un texto describiendo brevemente lo que el cliente debe hacer.
* Que la zona para ingresar el celular esté separada en espacio para el código de país y espacio para el número de teléfono.
* Que en la parte en donde se debe ingresar el OTP, el número de teléfono no sea editable (es decir, que sea el mismo que se mandó durante la creación del pago).
* Que el OTP valide que solo se puedan ingresar números, y que solo sean dígitos del 1 al 9, si se ajustan celdas una a una. También se puede crear una sola celda que valide que sean 6 dígitos numéricos máximo.
* Que exista un mensaje debajo del OTP, diciendo que pueden encontrar ese código en el menú de su aplicación de Yape. Para dispositivos móviles, agregar un deeplink de Yape al lado o debajo del OTP, con el mensaje "Abre tu Yape". Este deeplink redirecciona automáticamente al usuario a la sección de "Código de aprobación" de su aplicación de Yape. La URL del deeplink es: `https://www.yape.com.pe/app/checkout/approval_code`.
* Que el botón de pago diga "Yapear" en vez de "Pagar", para mayor personalización, así como el monto exacto.

Puedes ver un ejemplo de las anteriores recomendaciones aplicadas en esta imagen:

<Image align="center" border={false} width="300px" src="https://files.readme.io/933b1e6be8cf3243b46a018e64cf2c8f87c2ad05a2873fcfc4cc9579b6eed6b7-yapesintelef.jpg" />

***

## Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, puedes hacer pruebas con nuestros demos:

<Embed url="https://experience.prontopaga.com/" href="https://experience.prontopaga.com/" typeOfEmbed="iframe" height="1000px" width="100%" iframe="true" html="false" />

***

## Certifica tu integración

La certificación de la integración en _sandbox_ es un paso obligatorio que todos los comercios deben realizar antes de recibir sus credenciales de producción. Su propósito es asegurar que la integración cumpla con los estándares técnicos, funcionales y de seguridad requeridos por ProntoPaga. Dentro de esta sección, se establecen los requisitos que deben cumplirse sin excepción para que la certificación sea aprobada.

### Requisitos de certificación

A continuación, encontrarás los distintos requisitos necesarios para completar tu certificación:

<Tabs>
  <Tab title="ID del cliente">
    * ❌ El documento de identidad del cliente no debe ser modificable en ningún punto de la transacción.
    * ✅ Es recomendable que este dato no se muestre en el *checkout*. Solo puede estar disponible en la sección de perfil del usuario autenticado.
    * ⚠️ Esta medida tiene como objetivo prevenir fraudes y evitar que se generen transacciones realizadas por menores de edad.
  </Tab>

  <Tab title="Logotipos">
    * 📥 Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu *front-end*. Puedes [descargarlos aquí](https://prontopagalatam-my.sharepoint.com/:u:/g/personal/tahbet_reategui_prontopaga_com/EWC1ijJHq5JKnjpIH9qH0ncB42rHOzcbXWdiOlyQQHciCA?e=3taLCb\&download=1).
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
