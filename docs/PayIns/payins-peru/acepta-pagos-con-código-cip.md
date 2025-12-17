---
title: Acepta pagos con código CIP
excerpt: 'Conoce el paso a paso de cómo crear un pago con código CIP en Perú. '
deprecated: false
hidden: true
metadata:
  robots: index
---
Crear un pago con esta modalidad consiste en hacer una solicitud para crear un **código CIP** a través de nuestra API. Esta solicitud podrá realizarse tanto para la versión web como para la versión _mobile_. Una vez realizada con éxito, el cliente podrá realizar sus pagos ingresando el código CIP en diferentes plataformas integradas del **BCP (Banco de Crédito del Perú)** sin necesidad de usar tarjeta bancaria.

<Callout icon="👍" theme="okay">
  **CIP**

  El **Código de Identificación de Pago único (CIP)** es generado por ProntoPaga y vincula una operación específica con el usuario.
</Callout>

***

## ¿Cómo funciona?

BCP es un banco que opera en Perú y permite realizar pagos de cargos, cuotas o consumos mediante código CIP en sus distintas plataformas digitales. Para completar un pago con cualquiera de estas plataformas, el usuario debe iniciar sesión en:

* Yape
* VíaBCP (banca por internet)
* Telecrédito web BCP (banca negocios)
* Banca Móvil BCP (_app_)

El proceso de pago con código CIP en Perú consta de cuatro etapas principales:

1. **Selección de método.** El cliente elige pagar vía banca por internet/móvil BCP en tu sitio web o aplicación.
2. **Solicitud.** ProntoPaga genera el **código CIP** y muestra al cliente los datos para realizar el pago.
3. **Cuenta**. El cliente inicia sesión en su plataforma elegida para realizar el pago. La siguiente parte del flujo varía según el canal que elija el cliente:

<Cards columns={4}>
  <Card title="📱 En Yape:">
    El usuario abre su app Yape y elige la opción Yapear servicios. En el buscador ingresa ProntoPaga y luego digita el código CIP para completar la transacción.
  </Card>

  <Card title="📱En App Banca móvil BCP:">
    El usuario inicia sesión en su app Banca móvil BCP y selecciona la opción Pagar servicios. En el buscador ingresa ProntoPaga y digita el número de código CIP para finalizar la transacción.
  </Card>

  <Card title="💻 En VíaBCP Banca por internet">
    El usuario ingresa a su banca por internet del BCP y selecciona la opción Pagar servicios. En el buscador ingresa ProntoPaga y digita el número de código CIP otorgado para continuar la transacción.
  </Card>

  <Card title="🌐 En Telecrédito web BCP">
    El usuario inicia sesión en Telecrédito web y selecciona la opción Pagar servicios. En el buscador ingresa ProntoPaga y luego digita el código CIP asignado para completar la transacción.
  </Card>
</Cards>

4. **Pago**. El monto se recaudará directamente de la cuenta BCP del cliente.
5. **Confirmación**. El cliente recibe una confirmación de pago exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación del pago a través de los _webhooks_ que hayas configurado.

***

<br />

## Crea un nuevo pago

Tu _front-end_ será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu _back-end_ estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar este _endpoint_ y colocar `_pe_service_payment_` como método de pago en el _body_ de la solicitud.

La solicitud se envía con tu _Bearer Token_, así como con tu _secretKey_. Además, debes incluir los datos necesarios del cliente para hacer el pago, como nombre, correo electrónico, teléfono, país, moneda, monto, entre otros.

<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

<NotaWebhooks />

<br />

### Body de la solicitud

A continuación puedes ver un ejemplo del _body_ que se envía en la solicitud:

```json
{
  "currency": "PEN",
  "country": "PE",
  "amount": 100.90,
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "12345678912",
  "paymentMethod": "pe_service_payment",
  "urlConfirmation": "https://www.webhook.com",
  "urlFinal": "https://sandbox.prontopaga.com/successful",
  "urlRejected": "https://sandbox.prontopaga.com/declined",
  "order": "XYZ789",
  "sign": "Signature of the parameters"
}
```

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un enlace para procesar el pago, así como un identificador de pago del sistema y un código CIP.

```json
{
    "urlPay": "https://prontopaga.com/payment/rest/0A853DD8",
    "uid": "01JRGVFWM2N1H8Y817R9KWZPD9",
    "reference": "123456789",
    "cip": "0A853BD9"
}
```

### Confirmación de un pago

Una vez que el usuario haya completado el proceso de pago, ProntoPaga le notificará el resultado de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los PayIns](https://docs.prontopaga.com/docs/payins-status).

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
