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

<Accordion title={<span style={{ fontSize: '20px', fontWeight: 'bold' }}>🏦 Banco de Chile</span>}>
  Información sobre límites transaccionales para Banco de Chile.

  <div style={{ textAlign: 'center' }}>
    <img
      src="https://files.readme.io/7081e9375e797442b64c3bcf37df382d073da3509c993870501faed084241df1-187CEA09-A566-4E42-AC87-EA11749CCBA5_copia.png"
      alt="Cobertura Banco de Chile"
      style={{
        width: '79%',
        maxWidth: '1000px',
        height: 'auto',
        transition: 'all 0.4s ease'
      }}
      onMouseOver={(e) => (e.target.style.width = '100%')}
      onMouseOut={(e) => (e.target.style.width = '90%')}
    />
  </div>
</Accordion>

<Accordion title={<span style={{ fontSize: '20px', fontWeight: 'bold' }}>🏦 Banco Itaú</span>}>
  Información sobre los límites transaccionales para Banco Itaú.

  <div style={{ textAlign: 'center' }}>
    <img
      src="https://files.readme.io/e79992427d75e596e3bfbf1f7ae36d3c512372fb4616796defc49e3362e525ae-Itau_1.png"
      alt="Cobertura Banco Itaú"
      style={{
        width: '80%',
        maxWidth: '1000px',
        height: 'auto',
        transition: 'all 0.4s ease'
      }}
      onMouseOver={(e) => (e.target.style.width = '100%')}
      onMouseOut={(e) => (e.target.style.width = '90%')}
    />
  </div>
</Accordion>

<Accordion title={<span style={{ fontSize: '20px', fontWeight: 'bold' }}>🏦 Banco Bci</span>}>
  Información sobre los límites transaccionales para Banco Bci.

  <div style={{ textAlign: 'center' }}>
    <img
      src="https://files.readme.io/3d536e070ecf2b8913d328ad4cf19d9e7905e141fff21e25e1978002212e64bf-BCI.png"
      alt="Cobertura Banco Bci"
      style={{
        width: '80%',
        maxWidth: '1000px',
        height: 'auto',
        transition: 'all 0.4s ease'
      }}
      onMouseOver={(e) => (e.target.style.width = '100%')}
      onMouseOut={(e) => (e.target.style.width = '90%')}
    />
  </div>
</Accordion>

<Accordion title={<span style={{ fontSize: '20px', fontWeight: 'bold' }}>🏦 Banco Estado</span>}>
  Información sobre los límites transaccionales para Banco Estado.

  <div style={{ textAlign: 'center' }}>
    <img
      src="https://files.readme.io/cedaf4840f4f3e5773295fe4787d814346cf244539b966af8469483c4f5ffb81-Banco_Estado.png"
      alt="Cobertura Banco Estado"
      style={{
        width: '80%',
        maxWidth: '1000px',
        height: 'auto',
        transition: 'all 0.4s ease'
      }}
      onMouseOver={(e) => (e.target.style.width = '100%')}
      onMouseOut={(e) => (e.target.style.width = '90%')}
    />
  </div>
</Accordion>

<Accordion title={<span style={{ fontSize: '20px', fontWeight: 'bold' }}>🏦 Banco Santander</span>}>
  Información sobre los límites transaccionales para Banco Santander.

  <div style={{ textAlign: 'center' }}>
    <img
      src="https://files.readme.io/a2ff3764f101db442dbae6cda3d877f0ffc0ee9e29970b0f1303ca4a529f86a9-Captura_de_pantalla_2025-08-11_a_las_1.50.21_p._m..png"
      alt="Cobertura Banco Santander"
      style={{
        width: '80%',
        maxWidth: '1000px',
        height: 'auto',
        transition: 'all 0.4s ease'
      }}
      onMouseOver={(e) => (e.target.style.width = '100%')}
      onMouseOut={(e) => (e.target.style.width = '90%')}
    />
  </div>
</Accordion>

<Accordion title={<span style={{ fontSize: '20px', fontWeight: 'bold' }}>🏦 Banco Falabella</span>}>
  Información sobre los límites transaccionales para Banco Falabella.

  <div style={{ textAlign: 'center' }}>
    <img
      src="https://files.readme.io/a343a5f4734f6ebabd83bae730fcb88be4f73b638e378406c1e8aed5280e2b0d-Banco_Falabella.png"
      alt="Cobertura Banco Falabella"
      style={{
        width: '80%',
        maxWidth: '1000px',
        height: 'auto',
        transition: 'all 0.4s ease'
      }}
      onMouseOver={(e) => (e.target.style.width = '100%')}
      onMouseOut={(e) => (e.target.style.width = '90%')}
    />
  </div>
</Accordion>

<Accordion title={<span style={{ fontSize: '20px', fontWeight: 'bold' }}>🏦 Banco Security</span>}>
  Información sobre los límites transaccionales para Banco Security.

  <div style={{ textAlign: 'center' }}>
    <img
      src="https://files.readme.io/83bc8e235187695d0c1ee510a0098404cdb744db1f6950a093f09e1c6076e068-Captura_de_pantalla_2025-08-11_a_las_2.33.48_p._m..png"
      alt="Cobertura Banco Security"
      style={{
        width: '80%',
        maxWidth: '1000px',
        height: 'auto',
        transition: 'all 0.4s ease'
      }}
      onMouseOver={(e) => (e.target.style.width = '100%')}
      onMouseOut={(e) => (e.target.style.width = '90%')}
    />
  </div>
</Accordion>

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