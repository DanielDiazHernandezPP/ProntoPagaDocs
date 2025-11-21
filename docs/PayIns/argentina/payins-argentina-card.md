---
title: Acepta pagos con tarjeta
excerpt: Conoce el paso a paso de cómo crear un pago con tarjeta en Argentina.
deprecated: false
hidden: true
metadata:
  title: Crea pagos con tarjeta en Argentina | ProntoPaga Docs
  description: >-
    Learn how to create secure card payments in Argentina using the Prontopaga
    API. Includes full process flow, test data, error codes, webhook examples,
    and certification requirements.
  image: >-
    https://files.readme.io/90f9c2e90398791f651316ccf7ab6b66a91e0dcea89214c6719d73af0e5060ba-Prontopaga_logotipo.png
  keywords:
    - card payments Argentina
    - webhook examples Argentina
    - crear pagos con tarjeta Argentina
    - Bearer Token Argentina
    - secretKey Argentina
    - endpoint Argentina Prontopaga
  robots: index
next:
  description: ''
---
Crear un pago con tarjeta en Argentina consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un Bearer Token y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.

Los pagos con tarjeta cuentan con la herramienta automatizada Decision Manager (DM) del motor de gestión de riesgos y prevención de fraude de Cybersource (A Visa Solution), junto con el sistema 3DS, el cual activa los desafíos (_challenges_) correspondientes para validar o rechazar transacciones.

***

## ¿Cómo funciona?

El proceso de pago con tarjeta en Argentina consta de cinco etapas principales:

<Image align="center" border={true} src="https://files.readme.io/e1dacb24c1b77701ec92c84ea97b1a91d502e6a450bc53e992490a26a3bde650-image_4.png" className="border" />

1. **Selección de método.** El cliente elige pagar con tarjeta en tu sitio web o aplicación.
2. **Ingreso de datos.** El cliente llena los datos requeridos en el formulario de pago con tarjeta, como: número de tarjeta, fecha de vencimiento, CVV, nombre y correo electrónico.
3. **Validación de datos.** Se verifican los datos con el emisor de la tarjeta.
4. **Autorización y Captura.** Se verifica que existan los fondos suficientes, y se mueven desde el banco del cliente hacia la cuenta de tu comercio.
5. **Confirmación.** El cliente ve en pantalla el resultado de la transacción. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

***

## Crea un nuevo pago

Tu _front-end_ será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu _back-end_ estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `latam_chk_card_payment` como método de pago en el body de la solicitud.

La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros.

<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

<NotaWebhooks />

A continuación puedes el ejemplo de request:

**Ejemplo 1:**

```json
{ 
  "currency": "ARS", 
  "country": "AR", 
  "amount": "34000.90",
  "clientName" : "John Doe", 
  "clientEmail" : "johndoe@example.com", 
  "clientPhone" : "999999999", 
  "clientDocument" : "12345678912", 
  "paymentMethod" : "latam_chk_card_payment", 
  "urlConfirmation" : "https://www.webhook.com", 
  "urlFinal" : "https://sandbox.prontopaga.com/successful", 
  "urlRejected" : "https://sandbox.prontopaga.com/declined", 
  "order" : "XYZ789" 
}
```

***

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un enlace para procesar el pago, así como un identificador de pago del sistema.

#### Ejemplo de respuesta para pago exitoso:

```json
{ 
   "urlPay" : "Link to redirect or Iframe to insert",
   "uid" : "ID in our services",
   "reference": "Reference in our services" 
}
```

#### Ejemplos de respuestas de pagos rechazados:

```json
{ 
   "uid": "ID in our services",
   "status": "rejected",
   "reference": "Reason for rejection" 
}
```

***

### Confirmación de un pago

Una vez que el usuario haya completado el proceso de pago en el formulario, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los pay ins](https://docs.prontopaga.com/docs/payins-status).

Ejemplo de **webhook para un pago exitoso**:

```json
{ 
  "uid":"01HZ7HFEJZ0GN2TYNDDXC456F", 
  "status":"success", 
  "amount":36400.90, 
  "method":"AR Tarjeta", 
  "reference":"1687348107370523",
  "clientEmail" : "johndoe@example.com",
  "clientDocument" : "999999999",         
  "order":"XYZ789", 
  "currency":"ARS", 
  "country":"AR", 
  "method_type":"TDD", 
  "method_detail":"6623 VD", 
  "hash":"25aGF34G33HG34H41111",
  "note":"Transaction successful", 
  "sign":"e6f27650e5e7703949b0f2be41dde1aeab84145595c4183271e0a42f1500aa"
} 
```

### Detalles de un pago

Si así lo deseas, puedes consultar [este endpoint](https://docs.prontopaga.com/reference/payment-details) para conocer los detalles del pago. De ser exitosa la consulta, obtendrás una respuesta similar a la siguiente:

```json
{ 
  "uid": [string] // Transaction Identifier 
  "status": [string] // Transaction status 
  "amount": [integer] // Transaction amount 
  "method": [string] // Payment method used 
  "reference": [string] // Reference of the transaction 
  "clientEmail": [string] // Client's email address 
  "clientDocument": [string] // Customer's ID number 
  "order": [string] // Payment identifier to be associated with 
  "currency": [string] // ISO currency code 
  "country": [string] // International Country Format 
  "method_type": [string] // Method type 
  "method_detail": [string] // Method details 
	"hash": [string] // Security hash parameter
 	"note": [string] // Transaction note
  "sign": [string] // Signature of the parameters
}
```

### Motivos de rechazo

A continuación se muestran varios posibles casos de rechazo, junto con su descripción.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Mensaje de rechazo</b></th>
      <th><b>Descripción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>INSUFFICIENT_FUNDS</td><td>Saldo insuficiente para realizar la transacción.</td></tr>
    <tr><td>RECHAZADO POR EL BANCO</td><td>Tu banco rechazó la transacción. Contáctate con ellos para más información.</td></tr>
    <tr><td>DO_NOT_HONOR</td><td>Tu banco rechazó la transacción. Intenta con otra tarjeta o contacta a tu banco.</td></tr>
<tr><td>INVALID_SECURITY_CODE</td><td>El código CVV ingresado no es correcto. Verifica e inténtalo nuevamente.</td></tr>
    <tr><td>INVALID_CARD_DATA</td><td>Los datos de la tarjeta ingresados son incorrectos. Revisa los datos e inténtalo de nuevo.</td></tr>
    <tr><td>REPORTED_STOLEN</td><td>No se puede realizar la transacciones. La tarjeta ha sido reportada como robada. Contacta a tu banco para más información.</td></tr>
    <tr><td>ERROR</td><td>Se ha producido un error en la transacción. Inténtalo nuevamente o usa otro método de pago.</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

***

## Otros ejemplos:

## Crea un nuevo pago

Puedes probar tu integración con estos datos de prueba. **Para crear una solicitud de nuevo pago** deberás usar [este endpoint](https://docs.prontopaga.com/reference/crear-un-nuevo-pago-argentina#/) y hacer una solicitud POST a la siguiente ruta: `/integration-fiserv/api/v1/transaction/fiserv/{country}/create` como método de pago en el body de la solicitud. Este endpoint admite diferentes tipos de transacción (SALE, PREAUTH, etc.)

 Una vez validada la información (monto, moneda, token de tarjeta, etc.), el sistema genera un `checkoutId` único que identifica la transacción y devuelve su estado inicial. Para ver la estructura completa del request body, parámetros y respuestas del endpoint, consulta la [API Reference correspondiente](https://docs.prontopaga.com/reference/crear-un-nuevo-pago-argentina#/).

Para pagos con tarjeta necesitas:

* Datos del cliente
* Token o tarjeta
* Monto y moneda.
* Si lo requieres, también puedes habilitar cuotas o 3D Secure.

Al finalizar, obtendrás un `checkoutId`, que es el identificador que usarás en los siguientes pasos del flujo (consulta, captura, reversa, etc.).

> 🚧 **Firma de la transacción**
>
> Puedes ver el detalle de cómo firmar los parámetros de la transacción con tu _secretKey_ en [este artículo](https://docs.prontopaga.com/docs/sign-transactions)

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

> 📘 Notificación del estado de la transacción
>
> Para configurar el webhook que irá en el campo `confirmationURL` y recibir notificaciones con el estado de tu transacción, revisa [este artículo](https://docs.prontopaga.com/docs/webhooks).

### Request body

A continuación puedes ver un ejemplo de **request body**:

```json
{
  "checkoutId": "checkout_ms_dev_0_64",
  "customer": {
    "id": "C123",
    "name": "Johnsasas",
    "lastName": "Johnsas",
    "email": "john.doe@example.com",
    "phone": "1234567890",
    "documentType": "dni",
    "documentNumber": "12345678"
  },
  "amount": 900,
  "currency": "ARS",
  "transactionType": "SALE",
  "cardToken": "8103D0B5-9274-4415-8E15-B2092A215E21"
}
```

Para ver otros ejemplos de request body, [consulta la API Reference](https://docs.prontopaga.com/reference/crear-un-nuevo-pago-argentina#/).

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un enlace para procesar el pago, así como un identificador de pago del sistema.

#### Ejemplo de transacción de preautorización (Preauth):

```json
{
  "checkoutId": "checkout_local_preauth_01",
  "status": "PENDING",
  "transactionType": "PREAUTH",
  "amount": 2500,
  "currency": "ARS",
  "cardFunction": "CREDIT"
}
```

#### Ejemplo de respuesta para transacción creada correctamente:

```json
{
  "checkoutId": "checkout_local_normal_60",
  "status": "APPROVED",
  "transactionType": "SALE",
  "amount": 1000.34,
  "currency": "ARS",
  "cardFunction": "CREDIT"
}
```

#### Ejemplos de respuestas de pagos rechazados

A continuación te mostramos un ejemplo de respuesta para pagos rechazados. 

**Ejemplo de error de validación**

```json
{
  "statusCode": 400,
  "timestamp": "2025-07-29T20:43:59.770Z",
  "path": "/integration-firserv/api/v1/transaction/fiserv/ar/create",
  "errorCode": "VALIDATION_ERROR",
  "message": [
    "amount must be a positive number",
    "amount must be a number conforming to the specified constraints"
  ]
}
```

Revisa [otros tipos de respuesta](https://docs.prontopaga.com/reference/crear-un-nuevo-pago-argentina#/) para la creación de las transacciones.

## Capturar el monto de una transacción

Este _endpoint_  te permite capturar el importe de una transacción que fue previamente preautorizada. Para capturar una transacción preautorizada se debe realizar una solicitud POST a la siguiente ruta: `/api/v1/transaction/fiserv/{{country}}/capture`

Solo puedes realizar la captura total o parcial sobre transacciones con estado `PREAUTHORIZED` (`PREAUTH`) y debes ejecutarlas antes que venza la autorización (dentro de los 21 días). El monto de la captura debe ser menor o igual al monto preautorizado. Una vez realizada la captura, el estado de la transacción cambiará a `CAPTURED`. Además: 

* El `checkoutId` debe existir y pertenecer al `credential_code` proporcionado.
* La transacción debe tener un estado válido para ser capturada.
* El monto de la captura no debe exceder el monto preautorizado disponible.
* No debe superar el tiempo límite para la captura.
* El cuerpo de la solicitud debe incluir el monto a capturar y el `credential_code.`
* El parámetro `country` (_código ISO 3166-1 alfa-3_) debe ser proporcionado en la ruta.

> 🚧 Débito
>
> Las tarjetas de débito **no soportan preautorizaciones ni capturas**.

Para ver el endpoint de capturas parciales y respuestas, revisa [este artículo](https://docs.prontopaga.com/reference/crear-un-nuevo-pago-argentina#/). 

### Ejemplo de Request body: 

Esto ejemplo muesta los datos necesarios para registrar una captura completa:

```json
{
  "checkoutId": "checkout_local_normal_64",
  "valueToCapture": 600
}
```

Esto ejemplo muesta los datos necesarios para registrar una captura parcial:

```json
{
  "checkoutId": "checkout_local_normal_64",
  "valueToCapture": 300
}
```

### Respuesta: 

#### Ejemplo de transacción capturada correctamente

Este ejemplo muestra una captura completa exitosa.

```json
{
  "checkoutId": "checkout_local_normal_64",
  "status": {
    "transactionId": "84623663578",
    "statusTransaction": "APPROVED",
    "transactionType": "POSTAUTH",
    "amount": 600,
    "currency": "ARS",
    "updatedAt": "2025-07-21T12:18:15.000Z"
  }
}
```

#### Ejemplo de errores de captura:

Este ejemplo muestra un **estado no válido para la captura**:

```
{
  "message": "Action \"capture\" is not allowed for transaction type \"SALE\" and status \"REJECTED\"",
  "errorCode": "STATUS_NOT_ALLOWED",
  "statusCode": 400
}
```

Para ver otros estados, consulta la [API reference](https://docs.prontopaga.com/reference/crear-un-nuevo-pago-argentina#/).

## Confirmación de un pago

Una vez que el usuario haya completado el proceso de pago en el formulario, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los pay ins](https://docs.prontopaga.com/docs/payins-status).

Ejemplo de **webhook para un pago exitoso**:

## Detalles de un pago

Contamos con dos _endpoints_ para obtener información de las transacciones. Uno para obtener el _status_ actual y el otro que detalla los diferentes _status_ por los cuales pasó la transacción. 

Para obtener el status actual debes realizar una solicitud GET a la siguiente ruta:`/api/v1/transaction/fiserv/{{country}}/{checkout_id}`. 

**Características principales:**

* Devuelve el estado más reciente de la transacción.
* Útil para consultar el estado actual, por ejemplo: APROBADA, PENDIENTE, RECHAZADA. 
* Requiere el país y el ID de pago como parámetros de ruta. 
* El ID de pago debe existir y pertenecer al código de credenciales proporcionado.
* La transacción debe ser accesible con las credenciales que la solicitan. 
* El parámetro de país (código ISO 3166-1 alfa-3) y el ID de pago deben proporcionarse en la ruta.
* El ID de pago debe ser un identificador válido.

### Respuesta

#### Ejemplo de status actual

Este _endpoint_ recupera el estado actual de una transacción mediante su ID de pago..

```json
{
  "checkoutId": "checkout_local_normal_64",
  "status": {
    "transactionId": "160",
    "statusTransaction": "APPROVED",
    "transactionType": "POSTAUTH",
    "amount": 600,
    "currency": "ARS",
    "updatedAt": "2025-07-21T12:18:15.000Z"
  }
}
```

#### Ejemplo de transacción con múltiples estados

Este _endpoint_ `/api/v1/transaction/fiserv/{{country}}/{checkout_id}` recupera el historial de estado detallado de una transacción utilizando su ID de pago.

```json
{
  "checkoutId": "checkout_local_normal_64",
  "statusDetail": [
    {
      "transactionId": "190",
      "statusTransaction": "APPROVED",
      "transactionType": "POSTAUTH",
      "amount": 600,
      "currency": "ARS",
      "updatedAt": "2025-07-21T12:18:15.000Z"
    },
    {
      "transactionId": "189",
      "statusTransaction": "APPROVED",
      "transactionType": "PREAUTH",
      "amount": 900,
      "currency": "ARS",
      "updatedAt": "2025-07-21T12:12:10.000Z"
    }
  ]
}
```

## Datos de tokenización

Este _endpoint_ devuelve la estructura **requerida para la tokenización de datos de tarjetas de pago** según el proveedor de pagos. Se utiliza para tokenizar de forma segura los datos de la tarjeta antes de procesar pagos. Para obtener información de la estructura de tokenización, solicita un GET a `/integration-fiserv/api/v1/transaction/fiserv/{country}/structure/data-tokenization`

Además:

* Proporciona la estructura esperada de _headers_ y _request body_ para las solicitudes de tokenización.
* Requiere el parámetro `country` (código ISO 3166-1 alfa-3) en la ruta.
* El parámetro `country` debe ser válido, soportado y proporcionado en la ruta.
* La solicitud debe estar autenticada con una _API key_ válida.

### Respuesta

#### Ejemplo de estructura de tokenización

Este ejemplo muestra un formato básico requerido para generar un token seguro de tarjeta.

```json
{
  "header": {
    "Content-Type": "application/json",
    "Api-Key": "your-api-key",
    "Client-Request-Id": "unique-request-id",
    "Timestamp": "2025-07-21T12:00:00.000Z",
    "Message-Signature": "signature-value"
  },
  "body": {
    "requestType": "PaymentCardPaymentTokenizationRequest",
    "storeId": "5925031902",
    "paymentCard": {
      "number": "{{ TOKEN | extract : card }}",
      "securityCode": "{{ TOKEN | extract : cvv }}",
      "expiryDate": {
        "month": "{{ TOKEN | extract:expiration | date:MM}}",
        "year": "{{ TOKEN | extract:expiration | date:YY}}"
      }
    },
    "createToken": {
      "reusable": true,
      "declineDuplicates": false
    }
  }
}
```

## Actualizar transacción

Permite actualizar manualmente el estado de una transacción existente, por ejemplo, en casos donde se requiere intervención administrativa o la corrección de estados atípicos.
Este endpoint es útil en situaciones donde el flujo automático no pudo completar la actualización del estado o cuando es necesario forzar un cambio por motivos operativos o de conciliación.

Características principales

Puede utilizarse para marcar una transacción como APPROVED, REJECTED, CANCELLED, entre otros.

Es posible asociar el cambio de estado a un identificador de transacción del IPG, si corresponde.

El uso de este endpoint debe ser controlado y auditado, ya que impacta directamente en la integridad de los registros de transacciones.

Requisitos

Requiere credenciales válidas y el código de país (ISO 3166-1 alfa-3) donde se procesó la transacción.

Request body

```json
{
  "transactionType": "VOID",
  "ipgTransactionId": "123456789"
}
```

Respuestas:

El estado de la transacción se actualizó correctamente.

```json
{
  "checkoutId": "checkout_local_normal_63",
  "status": {
    "transactionId": "84623663173",
    "statusTransaction": "APPROVED",
    "transactionType": "RETURN",
    "amount": 1000.34,
    "currency": "ARS",
    "updatedAt": "2025-07-21T12:10:40.000Z"
  }
}
```

Validation or business rule error

```json
{
  "message": [
    "checkoutId must not be empty",
    "checkoutId must be a string"
  ],
  "errorCode": "BAD_REQUEST",
  "statusCode": 400
}
```

<br />

## 3DS

⚠️ IMPORTANTE:

Este endpoint solo funciona después de ejecutar primero el método form.
Si se ejecuta manualmente sin la ejecución previa del método form, no tendrá ningún efecto.

Propósito

Endpoint específico para validar transacciones 3DS de Fiserv.
Este proceso forma parte del flujo de autenticación 3D Secure, el cual requiere la ejecución previa del método form para generar los datos necesarios.

Flujo requerido

Ejecutar el método form (obligatorio).

Obtener threeDSMethodData.

Llamar a este endpoint utilizando los datos generados.

Características

Válido solo para transacciones Fiserv 3DS.

Requiere un checkoutId válido.

Necesita datos del método 3DS generados previamente.

Es un endpoint público (no requiere autenticación).

Body request:

```json
 {
  "threeDSMethodData": "eyJ0aHJlZURTTWV0aG9kRGF0YSI6InNhbXBsZV9kYXRhIn0="
}
```

Respuestas:

3DS transaction successfully validated

```json
{
  "checkoutId": "checkout_local_normal_64",
  "transactionType": "SALE",
  "status": "APPROVED",
  "amount": 1000.34,
  "currency": "ARS"
}
```

<br />

## Cancelar un pago:

Para cancelar una transacción se debe realizar una solicitud POST a la siguiente ruta: `/api/v1/transaction/fiserv/{{country}}/void`.

Este punto de conexión permite cancelar (anular) una transacción previamente autorizada o capturada. **Características principales:** - **ANULACIÓN DE VENTA:** - Solo se puede realizar el mismo día de la transacción de VENTA. - Se permite hasta las 23:30 (hora local). - Elimina el movimiento antes del cierre del lote; el cliente no ve el cargo. - **ANULACIÓN DE PREAUTORIZACIÓN:** - Se puede realizar hasta 21 días después de la PREAUTORIZACIÓN. - Sin límite de tiempo durante el día. - Solo es posible si no se ha realizado la POSTAUTICIÓN. **Reglas de negocio:** - El checkoutId debe existir y pertenecer al credential_code proporcionado. - La transacción debe estar en un estado válido para la anulación. - La solicitud de anulación debe realizarse dentro del plazo permitido para el tipo de operación. - El parámetro de país (código ISO 3166-1 alfa-3) debe proporcionarse en la ruta. **Validaciones:** - El cuerpo de la solicitud debe incluir el checkoutId y el credencial. - El parámetro de país debe proporcionarse en la ruta.

Datos necesarios para anular la transacción:

Body request

```json
{
  "checkoutId": "checkout_local_normal_64"
}
```

Ejemplo de Transaction voided successfully, para ver más ejemplos, consutla la api reference:

```json
{
  "checkoutId": "checkout_local_normal_64",
  "status": {
    "transactionId": "84623663578",
    "statusTransaction": "APPROVED",
    "transactionType": "VOID",
    "amount": 600,
    "currency": "ARS",
    "updatedAt": "2025-07-21T12:18:15.000Z"
  }
}
```

## Reembolsar transacción

Permite solicitar un reembolso para una transacción ya procesada. Es útil en casos donde el cliente devuelve un producto o se requiere reintegrar el dinero. Para cancelar una transacción se debe realizar una solicitud POST a la siguiente ruta:`{baseUrl}/api/v1/transaction/fiserv/{country}/refund`

**Características principales:** - Admite reembolsos totales y parciales. - El importe del reembolso no debe superar el importe registrado. - La solicitud de reembolso debe realizarse dentro de los **180 días** posteriores a la fecha de registro. - La transacción debe estar en un estado reembolsable (p. ej., REGISTRADA, APROBADA). **Reglas de negocio:** - El checkoutId debe existir y pertenecer al credential_code proporcionado. - La transacción debe estar en un estado válido para el reembolso. - El valor a reembolsar debe ser un número positivo y no superar el importe reembolsable. - La solicitud de reembolso debe realizarse dentro de los **180 días** posteriores al registro original. - El parámetro de país (código ISO 3166-1 alfa-3) debe proporcionarse en la ruta. **Validaciones:** - El cuerpo de la solicitud debe incluir el importe a reembolsar y el código de credencial. - El parámetro de país debe proporcionarse en la ruta.

**Request body de reembolso total:**

```json
{
  "checkoutId": "checkout_local_normal_63",
  "valueToRefund": 1000.34
}
```

### Respuestas:

Reembolso total exitoso

```json
{
  "checkoutId": "checkout_local_normal_63",
  "status": {
    "transactionId": "84623663173",
    "statusTransaction": "APPROVED",
    "transactionType": "RETURN",
    "amount": 1000.34,
    "currency": "ARS",
    "updatedAt": "2025-07-21T12:10:40.000Z"
  }
}
```

Errores de reembolso:

CheckoutID inválido:

```json
{
  "message": [
    "checkoutId must not be empty",
    "checkoutId must be a string"
  ],
  "errorCode": "BAD_REQUEST",
  "statusCode": 400
}
```

<br />

<br />

<br />

## Prueba tu integración

que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, puedes hacer pruebas con nuestros demos:

<Embed url="https://experience.prontopaga.com/" href="https://experience.prontopaga.com/" typeOfEmbed="iframe" height="1000px" width="100%" iframe="true" html="false" />

***

## Certifica tu integración

La certificación de la integración en _Sandbox_ es un paso obligatorio que todos los comercios deben realizar antes de recibir sus credenciales de producción. Su propósito es asegurar que la integración cumpla con los estándares técnicos, funcionales y de seguridad requeridos por ProntoPaga. Dentro de esta sección, se establecen los requisitos que deben cumplirse sin excepción para que la certificación sea aprobada.

### Requisitos de certificación

A continuación, encontrarás los distintos requisitos necesarios para completar tu certificación:

<Tabs>
  <Tab title="ID del cliente">
    * ❌ El documento de identidad del cliente no debe ser modificable en ningún punto de la transacción.
    * ✅ Es recomendable que este dato no se muestre en el *checkout*. Solo puede estar disponible en la sección de perfil del usuario autenticado.
    * ⚠️ Esta medida tiene como objetivo prevenir fraudes y evitar que se realicen transacciones en nombre de terceros o menores de edad.
  </Tab>

  <Tab title="Logotipos">
    * 📥 Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu *front-end*. Puedes [descargarlos aquí](https://prontopagalatam-my.sharepoint.com/:f:/g/personal/tahbet_reategui_prontopaga_com/EtPhXrMz3TxAtA11de5jVZEB3yowkpS1i2v6lm_eMKkB7g?e=BvEJpa\&download=1).
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
