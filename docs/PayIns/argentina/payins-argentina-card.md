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
Crear un pago con tarjeta en Argentina consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un _Bearer Token_ y una _secretKey_. De esta forma, las transacciones se autentican y se realizan de forma segura.

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

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `latam_chk_card_payment` o `ar_chk_card_payment `como método de pago en el body de la solicitud.

La solicitud se envía con tu _Bearer Token_, así como con tu _secretKey_. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros.

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

**Ejemplo 2:**

```json
{ 
  "currency": "ARS", 
  "country": "AR", 
  "amount": "34000.90",
  "clientName" : "John Doe", 
  "clientEmail" : "johndoe@example.com", 
  "clientPhone" : "999999999", 
  "clientDocument" : "12345678912", 
  "paymentMethod" : "ar_chk_card_payment", 
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

***

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

***

### Personalizar el formulario de pago

Puedes ajustar la apariencia de tu formulario con el parámetro opcional theme, cambiando el color de fondo o creando versiones en modo claro y modo oscuro con este <Anchor label="endpoint" target="_blank" href="https://docs.prontopaga.com/reference/create-payment#/">endpoint</Anchor>. A continuación, se muestra un ejemplo del body request:

```json
{
  "currency": "ARS",
  "country": "AR",
  "amount": "34000.90",
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "12345678912",
  "paymentMethod": "ar_chk_card_payment",
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

**Más motivos de rechazo**

<HTMLBlock>{`
<div style="overflow-x:auto;">
<table style="border-collapse: collapse; width: 100%;">
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Código</b></th>
      <th><b>Mensaje de rechazo</b></th>
    </tr>
  </thead>
  <tbody>

    <tr><td>USU0001</td><td>Cancelado por usuario</td></tr>
    <tr><td>FRA0004</td><td>Cuenta bloqueada, contacta a tu banco</td></tr>
    <tr><td>FOR0003</td><td>Datos inválidos, verifica e inténtalo nuevamente</td></tr>
    <tr><td>SIS0006</td><td>Error del sistema de conexión, intenta más tarde</td></tr>
    <tr><td>FOR0002</td><td>Error del sistema, verifica tus permisos</td></tr>
    <tr><td>RES0001</td><td>Excede monto máximo, contacta a tu banco</td></tr>
    <tr><td>FON0001</td><td>Fondo insuficiente, contacta a tu banco</td></tr>
    <tr><td>SIS0001</td><td>Merchant inválido</td></tr>
    <tr><td>RES0005</td><td>No cumple requisitos de edad, no insistir</td></tr>
    <tr><td>RES0002</td><td>Operación no permitida</td></tr>
    <tr><td>SIS0007</td><td>Pago rechazado</td></tr>
    <tr><td>AUT0002</td><td>Problema en la autenticación, vuelva a intentar</td></tr>
    <tr><td>SIS0003</td><td>Problema en la transacción, contacta a tu banco</td></tr>
    <tr><td>FRA0003</td><td>Riesgo de fraude - múltiples intentos</td></tr>
    <tr><td>FRA0002</td><td>Tarjeta bloqueada, contacta a tu banco</td></tr>
    <tr><td>SIS0008</td><td>Tarjeta inválida</td></tr>
    <tr><td>RES0004</td><td>Tarjeta vencida, no insistir</td></tr>
    <tr><td>TIM0001</td><td>Tiempo de espera agotado</td></tr>
    <tr><td>APR0005</td><td>Transacción completada exitosamente</td></tr>
    <tr><td>FRA0001</td><td>Transacción denegada, no insistir</td></tr>
    <tr><td>APR0001</td><td>Transacción exitosa</td></tr>
    <tr><td>TIM0002</td><td>Transacción expirada, inténtalo de nuevo</td></tr>
    <tr><td>TEC0001</td><td>Transacción inconsistente, no insistir</td></tr>
    <tr><td>TEC0002</td><td>Transacción no soportada, no insistir</td></tr>
    <tr><td>APR0002</td><td>Verificación de edad positiva</td></tr>
    <tr><td>APR0003</td><td>Verificaciones positivas</td></tr>

  </tbody>
</table>
</div>
`}</HTMLBlock>

***

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

<br />
