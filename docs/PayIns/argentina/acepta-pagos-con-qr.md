---
title: Acepta pagos con QR
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
Crear un pago con QR en Argentina consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un _Bearer Token_ y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.

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

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `ar_qr_payment` o `ar_qr_2_payment` como método de pago en el _body_ de la solicitud.

La solicitud se envía con tu _Bearer Token_, así como con tu _secretKey_. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros.

<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

<NotaWebhooks />

A continuación puedes ver dos ejemplos de _request_:

**Ejemplo 1**:

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

**Ejemplo 2:**

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

#### Ejemplo de error 400

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

### Confirmar un pago

Una vez que el usuario haya completado el proceso de pago en el formulario, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `APPROVED`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los pay ins](https://docs.prontopaga.com/docs/acepta-pagos-con-qr#/estados).

**Ejemplo de webhook para un pago exitoso**

```json
{
  "checkoutId": "checkout_123456",
  "status": "APPROVED"
}
```

***

### Devolver un pago

Para solicitar la devolución de un pago exitoso realizado con este método, [usa este endpoint](https://docs.prontopaga.com/update/reference/reembolsar-transacci%C3%B3n-qr-argentina#/). A continuación, se muestra un ejemplo del _body request_ que debe llevar:

```json
{
  "checkoutId": "checkout_123456",
  "valueToRefund": "34000.9"
}
```

***

<br />

### Cancelar transacción

Si un cliente generó un QR, pero no realizó el pago al momento, puedes cancelar ese QR para evitar que el cliente intente pagar más tarde con la imagen del QR.

Para cancelarlo, deberás consultar <Anchor label="este endpoint" target="_blank" href="https://docs.prontopaga.com/update/reference/cancelar-un-pago-con-qr-argentina#/">este endpoint</Anchor> con tu `Bearer Token` y mandar el `uid` del pago en la URL de la solicitud.

**Ejemplo de solicitud de cancelación**

```json
{
  "checkoutId": "chk_abc123xyz"
}
```

**Ejemplo de cancelación exitosa**

```json
{
  "checkoutId": "chk_abc123xyz",
  "status": "cancelled",
  "message": "Transaction cancelled successfully",
  "cancelledAt": "2025-11-26T11:00:00Z"
}
```

***

### Estados de transacción

Estos son los posibles estados que pueden tener los PayIns con QR en Argentina.

<table style={{ borderCollapse: 'collapse', width: '100%' }}>
  <thead>
    <tr style={{ backgroundColor: '#ff1f55', color: 'white', textAlign: 'left' }}>
      <th style={{ padding: '10px' }}><b>Estado</b></th>
      <th style={{ padding: '10px' }}><b>Descripción</b></th>
    </tr>
  </thead>

  <tbody>
    <tr style={{ backgroundColor: '#fff' }}>
      <td style={{ padding: '10px' }}><code>PENDING</code></td>
      <td style={{ padding: '10px' }}>Pago o transacción pendiente</td>
    </tr>

    <tr style={{ backgroundColor: '#f9f9f9' }}>
      <td style={{ padding: '10px' }}><code>APPROVED</code></td>
      <td style={{ padding: '10px' }}>Pago o transacción aprobada</td>
    </tr>

    <tr style={{ backgroundColor: '#fff' }}>
      <td style={{ padding: '10px' }}><code>REJECTED</code></td>
      <td style={{ padding: '10px' }}>Pago o transacción rechazada</td>
    </tr>

    <tr style={{ backgroundColor: '#f9f9f9' }}>
      <td style={{ padding: '10px' }}><code>CANCELLED</code></td>
      <td style={{ padding: '10px' }}>Pago o transacción cancelada</td>
    </tr>

    <tr style={{ backgroundColor: '#fff' }}>
      <td style={{ padding: '10px' }}><code>EXPIRED</code></td>
      <td style={{ padding: '10px' }}>Pago expirado</td>
    </tr>

    <tr style={{ backgroundColor: '#f9f9f9' }}>
      <td style={{ padding: '10px' }}><code>PARTIAL\_REFUND</code></td>
      <td style={{ padding: '10px' }}>Reembolso parcial</td>
    </tr>

    <tr style={{ backgroundColor: '#fff' }}>
      <td style={{ padding: '10px' }}><code>REFUNDED</code></td>
      <td style={{ padding: '10px' }}>Reembolso total</td>
    </tr>
  </tbody>
</table>

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
