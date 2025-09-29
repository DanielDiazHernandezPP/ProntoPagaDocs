---
title: Recibe pagos en efectivo
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Recibe pagos en efectivo | ProntoPaga Docs
  description: >-
    Learn how to accept or process cash payments in Ecuador using the Prontopaga
    API. This guide includes payment flow, API request format, test data, and
    webhook response handling.
  image: >-
    https://files.readme.io/bb512f737c6f69878c2747206617052931fdd19d98ad91d396faf642989c0417-Prontopaga_logotipo.png
  keywords:
    - cash payments Ecuador
    - Prontopaga cash Ecuador
    - how to make a cash payment in Ecuador
    - crear pagos en efectivo Ecuador
    - usar efectivo para pagos Prontopaga Ecuador
    - Western Union
    - Red Activa
    - BeMovil
    - PonleMás
  robots: index
next:
  description: ''
---
Crear un pago en efectivo en Ecuador consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un Bearer Token y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.

Conoce los puntos físicos de pago disponibles en [este artículo](https://docs.prontopaga.com/docs/physical-points-payins).

***

<br />

## ¿Cómo funciona?

Red Activa / Western Union, BeMovil y PonleMás son redes y plataformas que operan en Ecuador y permiten realizar pagos en efectivo para servicios, recargas y otras transacciones. Para completar una transacción con cualquiera de estos métodos, el usuario debe seleccionar la opción correspondiente:

* Paga con Efectivo - Western Union | Red Activa
* Paga con Efectivo - BeMovil
* Paga con Efectivo - PonleMás

Luego, debe acudir al punto de atención más cercano con su código de pago y una identificación válida (cédula nacional, cédula de extranjería o pasaporte).

El proceso de pago con efectivo en Ecuador consta de seis etapas principales:

<Image align="center" border={false} src="https://files.readme.io/bf07abc6015467c1a8a44d3f2ff1f8f43eaa3c42cd73ae006bfe0bd47c135e6d-Ecuador_-_01.jpg" />

1. **Ingreso de datos.** Después de seleccionar los productos o servicios a comprar, el cliente ingresa sus datos personales en un formulario.
2. **Selección de método.** El cliente elige pagar con efectivo en tu sitio web o aplicación.
3. **Hoja de pago**. ProntoPaga le entrega una hoja de pago personalizada al cliente, con un código de pago único, así como la información de los puntos físicos en donde puede realizar el pago.
4. **Pago en punto físico.** El cliente se dirige a uno de los puntos físicos con su hoja de pago y su identificación, y hace el depósito del efectivo.
5. **Validación de datos.** ProntoPaga valida la infomación del pago.
6. **Confirmación.** El cliente recibe una confirmación de pago exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación del pago a través de los webhooks que hayas configurado.

***

<br />

## Crea un nuevo pago

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar el método de pago en efectivo en el body de la solicitud.

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
  "paymentMethod": "bemovil_payment",
  "urlConfirmation": "https://www.webhook.com",
  "urlFinal": "https://sandbox.prontopaga.com/successful",
  "urlRejected": "https://sandbox.prontopaga.com/declined",
  "order": "XYZ789",
  "sign": "Signature of the parameters"
}
```

<br />

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un enlace con la hoja de pago, así como un identificador de pago del sistema.

<br />

### Hoja de pago

El cliente verá en pantalla y recibirá en su correo electrónico la hoja de pago, que contendrá:

* Monto a pagar
* Código de pago
* Instituciones en las que puede hacer el pago
* Instrucciones para hacer el pago

<br />

### Confirmación de un pago

Una vez que el usuario haya realizado el pago en efectivo, ProntoPaga le notificará el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

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
