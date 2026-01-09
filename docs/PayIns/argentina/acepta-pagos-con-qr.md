---
title: Acepta pagos con QR/Wallet
excerpt: Conoce el paso a paso de cómo crear un pago con QR en Argentina.
deprecated: false
hidden: true
metadata:
  title: Crea pagos con QR en Argentina | ProntoPaga Docs
  description: >-
    Learn how to create secure QR payments in Argentina using the Prontopaga
    API. Includes full process flow, test data, error codes, webhook examples,
    and certification requirements.
  image: >-
    https://files.readme.io/c85c58f4672246336aeb066769381b9b130bacabdce866d86eddc3508b6aa65a-Captura_de_pantalla_2025-09-08_a_las_4.24.49_p._m..png
  keywords:
    - QR payments Argentina
    - webhook examples Argentina
    - crear pagos con QR Argentina
    - Bearer Token Argentina
    - secretKey Argentina
    - endpoint Argentina Prontopaga
  robots: index
---
Crear un pago con QR/Wallet en Argentina consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un _Bearer Token_ y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.

***

## ¿Cómo funciona?

<Image align="center" border={false} src="https://files.readme.io/7d966bb565600eafff1fcf1853cb066728a04ee3589007318fd1cb8944962887-Argentina_MODO.jpg" />

El proceso de pago con wallet en Argentina consta de cuatro etapas principales:

1. **Selección de método.** El cliente elige pagar con código QR en tu sitio web.

<Callout icon="📘" theme="info">
  **Versión _mobile_ 📱**

  Si el dispositivo del cliente es _mobile_ deberá elegir la opción de pago con _wallet_ que abrirá la aplicación correspondiente para la confirmación del pago.
</Callout>

2. **Generación del QR.** ProntoPaga le entrega un QR único al cliente, el cual podrá escanear con la aplicación de la wallet con la que pagará.

Ten en cuenta que el flujo varía dependiendo de la versión utilizada:

<Cards columns={2}>
  <Card title="🌐 En web">
    Se genera un código QR para que el cliente lo escanee desde la apliación de su celular.
  </Card>

  <Card title="📱En mobile">
    La opción de pago con wallet abre la aplicación del cliente y se valida la identidad para confirmar el pago.
  </Card>
</Cards>

3. **Pago en aplicación.** El cliente abre la aplicación de su _wallet_, escanea el código QR y hace el pago. El dinero se mueve desde la _wallet_ del cliente hacia la cuenta de tu comercio.
4. **Confirmación.** El cliente recibe una confirmación de pago exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación del pago a través de los _webhooks_ que hayas configurado.

***

## Crear un nuevo pago

Tu _front-end_ será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu _back-end_ estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `ar_qr_payment` para pagos con QR web o `ar_qr_2_payment` para pagos con QR _mobile_, como método de pago en el _body_ de la solicitud.

La solicitud se envía con tu _Bearer Token_, así como con tu _secretKey_. Además, debes incluir los datos necesarios del cliente para hacer el pago, como nombre, correo electrónico, teléfono, país, moneda, monto, entre otros.

<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

<NotaWebhooks />

A continuación puedes ver dos ejemplos de _request_:

**Ejemplo QR web**:

```json
{
    "currency": "ARS",
    "country": "AR",
    "amount": "34000.90",
    "clientName": "John Doe",
    "clientEmail": "johndoe@example.com",
    "clientPhone": "999999999",
    "clientDocument": "12345678912",
    "paymentMethod": "ar_qr_payment",
    "urlConfirmation": "https://www.webhook.com",
    "urlFinal": "https://sandbox.prontopaga.com/successful",
    "urlRejected": "https://sandbox.prontopaga.com/declined",
    "order": "XYZ789"
}
```

**Ejemplo QR _mobile_:**

```json
{
"currency": "ARS",
    "country": "AR",
    "amount": "34000.90",
    "clientName": "John Doe",
    "clientEmail": "johndoe@example.com",
    "clientPhone": "999999999",
    "clientDocument": "12345678912",
    "paymentMethod": "ar_qr_2_payment",
    "urlConfirmation": "https://www.webhook.com",
    "urlFinal": "https://sandbox.prontopaga.com/successful",
    "urlRejected": "https://sandbox.prontopaga.com/declined",
    "order": "XYZ789"
}
```

***

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un enlace para procesar el pago, así como un identificador de pago del sistema.

#### Ejemplo de respuesta para solicitud exitosa

```json
{
    "uid": "01KB5Q3HCRQZVPFXZTKESCRHDK",
    "reference": "17643498227932",
    "urlPay": "https://www.webhook.com"
}
```

#### Ejemplo de respuesta de pago rechazado

```json
{ 
   "uid": "ID in our services",
   "status": "rejected",
   "reference": "Reason for rejection" 
}
```

#### Ejemplo de error

```json
{
  "statusCode": 400,
  "message": "Validation failed",
  "errors": [
    {
      "field": "amount",
      "message": "Amount must be a positive number"
    }
  ],
  "timestamp": "2025-04-25T07:00:00.000Z",
  "path": "/transaction/create"
}
```

***

### Consultar un pago

Una vez que el usuario haya completado el proceso de pago en el formulario, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `SUCCESS`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los pay ins](https://docs.prontopaga.com/docs/acepta-pagos-con-qr#/estados).

**Ejemplo de pago exitoso**

```json
{
  "status": "SUCCESS"
}
```

***

<br />

### Cancelar transacción

Si un cliente generó un QR o código, pero no realizó el pago al momento, puedes cancelarlo para evitar que el cliente intente pagar después. El _endpoint_ responde con una página HTML de ProntoPaga, donde se muestra el estado cancelado de la transacción.

Para cancelar un pago, consulta [estos endpoints](https://docs.prontopaga.com/reference/argentina) con tu `Bearer Token` y mandar el `uid` del pago en la URL de la solicitud.

<Callout icon="❗️" theme="error">
  **Ten en cuenta que**

  Los pagos con estado final `SUCCESS` o `REJECTED` no pueden ser cancelados.
</Callout>

***

### Visualizar el flujo final de un pago

Este [_endpoint_](https://docs.prontopaga.com/update/reference/ver-un-pago-finalizado-con-qr-argentina) se utiliza para visualizar el flujo final de **pago con QR en Argentina**. Busca el pago mediante su `uid` y redirige a la página de ProntoPaga. No realiza validaciones adicionales ni modifica el estado de la transacción.

***

### Validación de pago a terceros

ProntoPaga cuenta con un servicio de validación de pago de terceros, el cual confirma que el número de teléfono celular ingresado coincide con los datos de la cuenta del cliente, evitando que se realicen pagos de terceros y maximizando la seguridad de tus transacciones.

Esta validación se asigna de forma automática a ciertos comercios integrados con nosotros. Si deseas activarla o desactivarla, comunícate con nuestro equipo de integración.

***

<br />

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
    * ⚠️ Esta medida tiene como objetivo prevenir fraudes y evitar que se realicen transacciones en nombre de terceros o menores de edad.
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
