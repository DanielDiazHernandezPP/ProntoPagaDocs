---
title: Transferencia (Paga con Tu Banco)
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Transferencia (Paga con Tu Banco) | ProntoPaga Docs
  description: >-
    Learn how to create secure bank transfer payments in Ecuador using the
    Prontopaga API. Includes payment flow, required parameters, webhooks, test
    data, and certification steps. 
  image: >-
    https://files.readme.io/08fc906b454e67bd107f208b454cdbdc55a7a97d30e7fa6c68fa7fc845050889-Prontopaga_logotipo.png
  keywords:
    - Wire transfer
    - bank transfer payments Ecuador
    - payment flow Ecuador
    - Prontopaga
    - pagos por transferencia bancaria Ecuador
  robots: index
next:
  description: ''
---
Crear un pago en Ecuador por medio de transferencia bancaria consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un Bearer Token y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.

Además, todas tus transacciones cuentan con la herramienta automatizada Decision Manager (DM) del motor de gestión de riesgos y prevención de fraude de **Cybersource (A Visa Solution)**.

***

<br />

## ¿Cómo funciona?

Paga con Tu Banco (Transferencia) es un método de pago utilizado en Ecuador que permite realizar transferencias electrónicas de fondos entre cuentas bancarias. Para completar una transacción utilizando este método de pago, el cliente debe seleccionar la opción "Paga con Tu Banco", elegir la cuenta desde la cual desea realizar la transferencia y aprobar la transacción desde la plataforma de su entidad bancaria.

El proceso de pago con transferencia en Ecuador consta de cuatro etapas principales:

<Image align="center" border={false} src="https://files.readme.io/1928bc5ac79a084a9b25b4050ef0d51c71bd6f063ed7cd89e36bac84b509a3a0-Ecuador_-_02.jpg" />

<br />

1. **Selección de método.** El cliente elige pagar con transferencia en tu sitio web o aplicación.
2. **Selección de banco.** Se le muestra un listado de bancos al cliente, en donde podrá seleccionar el suyo
3. **Redirección.** El cliente es redirigido al portal de su banco, en donde deberá iniciar sesión y seguir las instrucciones en pantalla para hacer la transferencia. El dinero se mueve desde el banco del cliente hacia la cuenta de tu comercio.
4. **Confirmación.** El cliente es redirigido a tu sitio y se muestra el resultado de la transacción. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

***

<br />

## Crea un nuevo pago

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `PagaConTuBanco` como método de pago en el body de la solicitud.

<NotaFirma />

La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros.

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
  "paymentMethod": "PagaConTuBanco",
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

### Pago en el banco

El cliente podrá continuar el proceso siguiendo las instrucciones en pantalla. Se redireccionará al cliente al sitio web de la institución bancaria que haya seleccionado para pagar, en donde podrá iniciar sesión y hacer la transferencia.

<br />

### Confirmación de un pago

Una vez que el usuario haya completado el proceso de pago en su banco, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

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
