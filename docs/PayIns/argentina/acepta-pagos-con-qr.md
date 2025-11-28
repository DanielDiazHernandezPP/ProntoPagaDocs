---
title: Acepta pagos con QR
excerpt: Conoce el paso a paso de cómo crear un pago con QR en Argentina.
deprecated: false
hidden: true
metadata:
  robots: index
---
Crear un pago con QR en Argentina consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un _Bearer Token_ y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.

Además, todas tus transacciones cuentan con la herramienta automatizada Decision Manager (DM) del motor de gestión de riesgos y prevención de fraude de Cybersource (A Visa Solution).

***

¿Cómo funciona?

<Image align="center" border={false} src="https://files.readme.io/7d966bb565600eafff1fcf1853cb066728a04ee3589007318fd1cb8944962887-Argentina_MODO.jpg" />

El proceso de pago con wallet en Argentina consta de cuatro etapas principales:

1. **Selección de método.** El cliente elige pagar con código QR en tu sitio web.

<Callout icon="📘" theme="info">
  **Versión mobile 📱**

  Si el dispositivo del cliente es mobile deberá elegir la opción de pago con wallet que abrirá la aplicación correspondiente para la confirmación del pago.
</Callout>

2. **Generación del QR.** ProntoPaga le entrega un QR único al cliente, el cual podrá escanear con la aplicación de la wallet con la que pagará.

Ten en cuenta que el flujo varía dependiendo de la versión utilizada:

<Cards columns={2}>
  <Card title="🌐 En web">
    Se genera un código QR para que el cliente lo escanee desde la apliación de su celular.
  </Card>

  <Card title="📱En mobile">
    La opción de pago con wallet abre la aplicación del cliente y se valida para confirmar el pago.
  </Card>
</Cards>

3. **Pago en aplicación.** El cliente abre la aplicación de su wallet, escanea el código QR y hace el pago. El dinero se mueve desde la wallet del cliente hacia la cuenta de tu comercio.
4. **Confirmación.** El cliente recibe una confirmación de pago exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación del pago a través de los webhooks que hayas configurado.

***

## Crea un nuevo pago

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y `colocar ar_qr_payment` o `ar_qr_2_payment` como método de pago en el _body_ de la solicitud.

La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros.

<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

<NotaWebhooks />

A continuación puedes ver dos ejemplos de _request_:

**Ejemplo 1**:

```json
{
    "currency": "ARS",
    "country": "AR",
    "amount": "110",
    "clientName": "Demo",
    "clientEmail": "luiggi@demo.cl",
    "clientPhone": "933020100",
    "clientDocument": "11111111",
    "paymentMethod": "ar_qr_payment",
    "urlConfirmation": "https://sandbox.prontopaga.com/test/logs",
    "urlFinal": "https://sandbox.prontopaga.com/test/logs",
    "urlRejected": "https://sandbox.prontopaga.com/test/logs",
    "order": randomData
}
```

**Ejemplo 2:**

```json
{
    "currency": "ARS",
    "country": "AR",
    "amount": "110",
    "clientName": "Demo",
    "clientEmail": "luiggi@demo.cl",
    "clientPhone": "933020100",
    "clientDocument": "11111111",
    "paymentMethod": "ar_qr_2_payment",
    "urlConfirmation": "https://sandbox.prontopaga.com/test/logs",
    "urlFinal": "https://sandbox.prontopaga.com/test/logs",
    "urlRejected": "https://sandbox.prontopaga.com/test/logs",
    "order": randomData
}
```

<br />

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

#### Ejemplo de respuesta de pago rechazado:

```json
{ 
   "uid": "ID in our services",
   "status": "rejected",
   "reference": "Reason for rejection" 
}
```

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

<br />
