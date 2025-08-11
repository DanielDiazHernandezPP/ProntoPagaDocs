---
title: Transferencia (Paga con Tu Banco)
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Transferencia (Paga con Tu Banco) | ProntoPaga Docs
  description: >-
    Learn how to create secure bank transfer payments in Chile using the
    Prontopaga API. Includes payment flow, required parameters, webhooks, test
    data, and certification steps.
  image: >-
    https://files.readme.io/ed53d7d42e750212c35b313110a1e79c89dc9b52d246a4aab1b4a66d2e9326a4-Prontopaga_logotipo.png
  keywords:
    - bank transfer
    - bank transfer payments Chile
    - Prontopaga Chile
    - Chile API integration Prontopaga
    - payment flow Chile Prontopaga
    - pagos por transferencia bancaria Chile
    - Paga con tu banco Chile
  robots: index
next:
  description: ''
---
Crear un pago en Chile por medio de transferencia bancaria consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un Bearer Token y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.

Además, todas tus transacciones cuentan con la herramienta automatizada Decision Manager (DM) del motor de gestión de riesgos y prevención de fraude de **Cybersource (A Visa Solution)**.

***

<br />

## ¿Cómo funciona?

Los pagos con transferencia son una forma común de realizar transacciones entre cuentas bancarias en Chile, ya sea dentro del mismo banco o entre distintos bancos, utilizando la banca en línea o plataformas electrónicas. Para completar una transacción utilizando este método de pago, el cliente debe seleccionar la opción "Paga con tu Banco", ingresar a su cuenta bancaria con su RUT y Clave, seleccionar la cuenta desde la cual realizará la transacción, elegir el método de autorización y autenticar la operación.

El proceso de pago con transferencia en Chile consta de cuatro etapas principales:

<Image align="center" src="https://files.readme.io/69fe50cdef55e7e15ea855157082a443a11feff735e1a6d32b6b769c1772bd2b-Chile-03.jpg" />

1. **Selección de método.** El cliente elige pagar con transferencia en tu sitio web o aplicación.
2. **Selección de banco.** Se le muestra un listado de bancos al cliente, en donde podrá seleccionar el suyo.
3. **Redirección y autorización** El cliente es redirigido al portal de su banco, en donde deberá iniciar sesión y seguir las instrucciones en pantalla para hacer la transferencia. Por única vez, **se solicitará al cliente el registro previo de la cuenta receptora** para acelerar futuras transacciones. Además:
   * Los bancos requieren autenticación de dos factores utilizando claves, tokens o autenticador dinámico para aprobar la transacción.
   * El dinero se mueve desde el banco del cliente hacia la cuenta de tu comercio.
4. **Confirmación.** El cliente es redirigido a tu sitio y se muestra el resultado de la transacción. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

***

## Límites transaccionales

Cada banco establece sus propios límites transaccionales, que dependen de factores como el método de autenticación y si la cuenta se ha registrado previamente.

Es importante conocer las políticas de cada banco sobre los montos de las transacciones, incluido el pago inicial, el periodo de espera antes de la segunda transacción y los límites de transacciones futuras. Estos límites pueden variar dependiendo del tipo de cuenta o del sistema de autenticación utilizado por el banco.

A continuación mostramos los límites por banco y sus consideraciones especiales.

\<Accordion title=\{\<span style=\{\{ fontSize: '20px', fontWeight: 'bold' }}>Banco de Chile\</span>}>
&#x20; En este banco, los límites de transacción se establecen en función del tipo de autenticación de segundo factor.

&#x20; \<div style=\{\{ textAlign: 'center' }}>
&#x20;   \<img
&#x20;     src=dd09a353-450d-42c2-9d80-a09ce54dc24d.png
&#x20;     alt="Brasil Coverage"
&#x20;     style=\{\{
&#x20;       width: '80%',
&#x20;       maxWidth: '1000px',
&#x20;       height: 'auto',
&#x20;       transition: 'all 0.4s ease'
&#x20;     }}
&#x20;     onMouseOver=\{(e) => (e.target.style.width = '100%')}
&#x20;     onMouseOut=\{(e) => (e.target.style.width = '90%')}
&#x20;   />
&#x20; \</div>
\</Accordion>

\<Accordion title=\{\<span style=\{\{ fontSize: '20px', fontWeight: 'bold' }}>🇨🇱 Chile\</span>}>
&#x20; A continuación, podrás ver listados los métodos con los que contamos en Chile, tanto para PayIns como para PayOuts.

&#x20; \<div style=\{\{ textAlign: 'center' }}>
&#x20;   \<img
&#x20;     src="https\://files.readme.io/d44a8c59af784f4496b9624b423dada1719ad7e2f83a3f382b1e99b3a240e3eb-Coverage\_in\_Chile.png"
&#x20;     alt="Chilean Coverage"
&#x20;     style=\{\{
&#x20;       width: '80%',
&#x20;       maxWidth: '1000px',
&#x20;       height: 'auto',
&#x20;       transition: 'all 0.4s ease'
&#x20;     }}
&#x20;     onMouseOver=\{(e) => (e.target.style.width = '100%')}
&#x20;     onMouseOut=\{(e) => (e.target.style.width = '90%')}
&#x20;   />
&#x20; \</div>
\</Accordion>

\<Accordion title=\{\<span style=\{\{ fontSize: '20px', fontWeight: 'bold' }}>🇪🇨 Ecuador\</span>}>
&#x20; A continuación, podrás ver listados los métodos con los que contamos en Ecuador, tanto para PayIns como para PayOuts.

&#x20; \<div style=\{\{ textAlign: 'center' }}>
&#x20;   \<img
&#x20;     src="https\://files.readme.io/f726f22a13bc8511c8ab07d77032139ccc8212ac4b0b10640a9cceccedd7d30d-Coverage\_in\_Ecuador.png"
&#x20;     alt="Ecuadorian Coverage"
&#x20;     style=\{\{
&#x20;       width: '80%',
&#x20;       maxWidth: '1000px',
&#x20;       height: 'auto',
&#x20;       transition: 'all 0.4s ease'
&#x20;     }}
&#x20;     onMouseOver=\{(e) => (e.target.style.width = '100%')}
&#x20;     onMouseOut=\{(e) => (e.target.style.width = '90%')}
&#x20;   />
&#x20; \</div>
\</Accordion>

\<Accordion title=\{\<span style=\{\{ fontSize: '20px', fontWeight: 'bold' }}>🇵🇪 Perú\</span>}>
&#x20; A continuación, podrás ver listados los métodos con los que contamos en Perú, tanto para PayIns como para PayOuts.

&#x20; \<div style=\{\{ textAlign: 'center' }}>
&#x20;   \<img
&#x20;     src="https\://files.readme.io/1b3ae4e6a2dbb194b9aac5a2e521d21609d420c2adb8388ad28e274f116a786d-Coverage\_in\_Peru.png"
&#x20;     alt="Peruvian Coverage"
&#x20;     style=\{\{
&#x20;       width: '80%',
&#x20;       maxWidth: '1000px',
&#x20;       height: 'auto',
&#x20;       transition: 'all 0.4s ease'
&#x20;     }}
&#x20;     onMouseOver=\{(e) => (e.target.style.width = '100%')}
&#x20;     onMouseOut=\{(e) => (e.target.style.width = '90%')}
&#x20;   />
&#x20; \</div>
\</Accordion>

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
  "currency": "CLP",
  "country": "CL",
  "amount": "25500",
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "11111111-1",
  "paymentMethod": "PagaConTuBanco",
  "urlConfirmation": "https://www.webhook.com",
  "urlFinal": "https://sandbox.prontopaga.com/successful",
  "urlRejected": "https://sandbox.prontopaga.com/declined",
  "order": "XYZ789",
  "sign": "Signature of the parameters"
}
```

> 👍 Solicitud a un banco específico (Direct Banks - Chile y Perú)
>
> Para hacer una solicitud a un banco específico, primero debes consultar el endpoint de [Lista de códigos bancarios](https://docs.prontopaga.com/reference/bank-codes), tomar el valor del campo `code` y colocarlo en el parámetro `bankCode` de [este endpoint](https://docs.prontopaga.com/reference/create-payment).

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

La certificación de la integración en *sandbox* es un paso obligatorio que todos los comercios deben realizar antes de recibir sus credenciales de producción. Su propósito es asegurar que la integración cumpla con los estándares técnicos, funcionales y de seguridad requeridos por ProntoPaga. Dentro de esta sección, se establecen los requisitos que deben cumplirse sin excepción para que la certificación sea aprobada.

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
    * 📥 Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu *front-end*. Puedes [descargarlos aquí](https://drive.google.com/uc?export=download\&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr).
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