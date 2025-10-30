---
title: Transferencia (Paga con Tu Banco)
excerpt: Conoce el paso a paso de cómo crear un pago con transferencia en Chile.
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

## ¿Cómo funciona?

Los pagos con transferencia son una forma común de realizar transacciones entre cuentas bancarias en Chile, ya sea dentro del mismo banco o entre distintos bancos, utilizando la banca en línea o plataformas electrónicas. Para completar una transacción utilizando este método de pago, el cliente debe seleccionar la opción "Paga con tu Banco", ingresar a su cuenta bancaria con su RUT y Clave, seleccionar la cuenta desde la cual realizará la transacción, elegir el método de autorización y autenticar la operación.

El proceso de pago con transferencia en Chile consta de cuatro etapas principales:

<Image align="center" border={false} src="https://files.readme.io/69fe50cdef55e7e15ea855157082a443a11feff735e1a6d32b6b769c1772bd2b-Chile-03.jpg" />

1. **Selección de método.** El cliente elige pagar con transferencia en tu sitio web o aplicación.
2. **Selección de banco.** Se le muestra un listado de bancos al cliente, en donde podrá seleccionar el suyo.
3. **Redirección y autorización** El cliente es redirigido al portal de su banco, en donde deberá iniciar sesión y seguir las instrucciones en pantalla para hacer la transferencia. Por única vez, **se solicitará al cliente el registro previo de la cuenta receptora** para acelerar futuras transacciones. Además:
   * Los bancos requieren autenticación de dos factores utilizando claves, tokens o autenticador dinámico para aprobar la transacción.
   * El dinero se mueve desde el banco del cliente hacia la cuenta de tu comercio.
4. **Confirmación.** El cliente es redirigido a tu sitio y se muestra el resultado de la transacción. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

<Callout icon="📘" theme="info">
  **Ten en cuenta que**

  El proceso de autorización y la forma de autenticación son diferentes según el banco.
</Callout>

***

## Límites transaccionales para transferencias

Cada banco **establece sus propios límites transaccionales**, que dependen de factores como el método de autenticación y si la cuenta se ha registrado previamente.

Es importante **conocer las políticas de cada banco sobre los montos de las transacciones**, incluido el pago inicial, el periodo de espera antes de la segunda transacción y los límites de transacciones futuras. Estos límites pueden variar dependiendo del tipo de cuenta o del sistema de autenticación utilizado por el banco.

⏳ A continuación mostramos **los límites por banco** y sus consideraciones especiales.

<Accordion title={<span style={{ fontSize: '18px', fontWeight: 'bold' }}>🏦 Banco de Chile</span>}>
  Información sobre límites transaccionales.

  <Table align={["left","left","left","left"]}>
    <thead>
      <tr>
        <th style={{ textAlign: "left" }}>
          Banco de Chile
        </th>

        <th style={{ textAlign: "left" }}>
          Límite de primera transacción
        </th>

        <th style={{ textAlign: "left" }}>
          Límites de transacciones en curso:
        </th>

        <th style={{ textAlign: "left" }}>
          Tiempo de espera para la segunda transacción:
        </th>
      </tr>
    </thead>

    <tbody>
      <tr>
        <td style={{ textAlign: "left" }}>
          En este banco, los límites transaccionales se establecen **según el tipo de autenticación de segundo factor**.
        </td>

        <td style={{ textAlign: "left" }}>
          CLP $350.000
        </td>

        <td style={{ textAlign: "left" }}>
          * **DigiPass y Mi Pass**: hasta $5.000.000 diarios (CLP)
          * **DigiCard**:
            hasta $2.000.000 diarios (CLP)
        </td>

        <td style={{ textAlign: "left" }}>
          12 horas
        </td>
      </tr>
    </tbody>
  </Table>
</Accordion>

<Accordion title={<span style={{ fontSize: '18px', fontWeight: 'bold' }}>🏦 Banco Itaú</span>}>
  Información sobre límites transaccionales.

  <Table align={["left","left","left","left"]}>
    <thead>
      <tr>
        <th style={{ textAlign: "left" }}>
          Banco Itaú
        </th>

        <th style={{ textAlign: "left" }}>
          Límite de primera transacción
        </th>

        <th style={{ textAlign: "left" }}>
          Límites de transacciones en curso:
        </th>

        <th style={{ textAlign: "left" }}>
          Tiempo de espera para la segunda transacción:
        </th>
      </tr>
    </thead>

    <tbody>
      <tr>
        <td style={{ textAlign: "left" }}>
          En este banco, los limites se establecen para la transacción inicial **según el tipo de cuenta del usuario**.
        </td>

        <td style={{ textAlign: "left" }}>
          * Cuenta Corriente:
            **hasta $300.000** diarios (CLP)
          * Cuenta Vista/Ahorro/RUT:
            **hasta $200.000** diarios (CLP)
        </td>

        <td style={{ textAlign: "left" }}>
          Hasta $**5.000.000** diarios (CLP)
        </td>

        <td style={{ textAlign: "left" }}>
          24 horas
        </td>
      </tr>
    </tbody>
  </Table>
</Accordion>

<Accordion title={<span style={{ fontSize: '18px', fontWeight: 'bold' }}>🏦 Banco BCI</span>}>
  Información sobre límites transaccionales.

  <Table align={["left","left","left","left"]}>
    <thead>
      <tr>
        <th style={{ textAlign: "left" }}>
          Banco BCI
        </th>

        <th style={{ textAlign: "left" }}>
          BCI PASS: (App)
        </th>

        <th style={{ textAlign: "left" }}>
          Multipass (dispositivo físico):
        </th>

        <th style={{ textAlign: "left" }}>
          Tiempo de espera para la segunda transacción:
        </th>
      </tr>
    </thead>

    <tbody>
      <tr>
        <td style={{ textAlign: "left" }}>
          En Banco BCI, los límites dependen del sistema de autenticación.
        </td>

        <td style={{ textAlign: "left" }}>
          * Límite de primera transacción:
            **CLP $600.000**
          * Límites de transacciones en curso:
            hasta **$7.000.000 diarios (CLP)**
        </td>

        <td style={{ textAlign: "left" }}>
          * Límite de primera transacción:\
            **CLP $250.000**
          * Límites de transacciones en curso:\
            hasta **$5.000.000 diarios (CLP)**
        </td>

        <td style={{ textAlign: "left" }}>
          24 horas
        </td>
      </tr>
    </tbody>
  </Table>
</Accordion>

<Accordion title={<span style={{ fontSize: '18px', fontWeight: 'bold' }}>🏦 Banco Estado</span>}>
  Información sobre límites transaccionales.

  <Table align={["left","left","left","left"]}>
    <thead>
      <tr>
        <th style={{ textAlign: "left" }}>
          Banco Estado
        </th>

        <th style={{ textAlign: "left" }}>
          Cuenta RUT:
        </th>

        <th style={{ textAlign: "left" }}>
          Cuenta corriente y chequera electrónica:
        </th>

        <th style={{ textAlign: "left" }}>
          Tiempo de espera para la segunda transacción:
        </th>
      </tr>
    </thead>

    <tbody>
      <tr>
        <td style={{ textAlign: "left" }}>
          Los límites diarios de Banco Estado varían según el tipo de cuenta.
        </td>

        <td style={{ textAlign: "left" }}>
          * Límite de primera transacción:
            **CLP $100.000**
          * Límites de transacciones en curso:
            Hasta **$1.000.000 diarios (CLP)**
        </td>

        <td style={{ textAlign: "left" }}>
          * Límite de primera transacción:\
            **CLP $250.000**
          * Límites de transacciones en curso:\
            hasta **$5.000.000 diarios (CLP)**
        </td>

        <td style={{ textAlign: "left" }}>
          24 horas
        </td>
      </tr>
    </tbody>
  </Table>
</Accordion>

<Accordion title={<span style={{ fontSize: '18px', fontWeight: 'bold' }}>🏦 Banco Santander</span>}>
  Información sobre límites transaccionales.

  | Banco Santander                           | Límite de primera transacción: | Limites de transacciones en curso: | Tiempo de espera para la segunda transacción: |
  | :---------------------------------------- | :----------------------------- | :--------------------------------- | :-------------------------------------------- |
  | En este banco, los limites son generales. | **CLP $250.000**               | Hasta **$5.000.000 diarios (CLP)** | 24 horas                                      |
</Accordion>

<Accordion title={<span style={{ fontSize: '18px', fontWeight: 'bold' }}>🏦 Banco Falabella</span>}>
  Información sobre límites transaccionales.

  | Banco Falabella                           | Límite de primera transacción: | Limites de transacciones en curso: | Tiempo de espera para la segunda transacción: |
  | :---------------------------------------- | :----------------------------- | :--------------------------------- | :-------------------------------------------- |
  | En este banco, los limites son generales. | **CLP $200.000**               | Hasta **$7.000.000 diarios (CLP)** | 24 horas                                      |
</Accordion>

<Accordion title={<span style={{ fontSize: '18px', fontWeight: 'bold' }}>🏦 Banco Ripley</span>}>
  Información sobre límites transaccionales.

  | Banco Ripley                                                        | Límite de primera transacción: | Limites de transacciones en curso: | Límites con clave de coordenadas: |
  | :------------------------------------------------------------------ | :----------------------------- | :--------------------------------- | :-------------------------------- |
  | Transferencias diarias de hasta **$7.000.000 CLP** con clave Rpass. | **CLP $250.000**               | Hasta **$7.000.000 diarios (CLP)** | Hasta **$2.000.000 (CLP)**        |
</Accordion>

<Accordion title={<span style={{ fontSize: '18px', fontWeight: 'bold' }}>🏦 Banco Scotiabank</span>}>
  Información sobre límites transaccionales.

  | Banco Scotiabank        | Límite de primera transacción: | Limites de transacciones diarias:  | Tiempo de espera para la segunda transacción: |
  | :---------------------- | :----------------------------- | :--------------------------------- | :-------------------------------------------- |
  | Hasta **5.000.000(CLP) diarios** | \*\* 300.000 (CLP)\*\*       | Hasta **$5.000.000 diarios (CLP)** | Hasta **24 horas**                            |
</Accordion>

<Accordion title={<span style={{ fontSize: '18px', fontWeight: 'bold' }}>🏦 Banco Security</span>}>
  Información sobre límites transaccionales

  <Table align={["left","left","left","left","left"]}>
    <thead>
      <tr>
        <th style={{ textAlign: "left" }}>
          Banco Security
        </th>

        <th style={{ textAlign: "left" }}>
          Límite de primera transacción:
        </th>

        <th style={{ textAlign: "left" }}>
          Tarjeta de coordenadas
        </th>

        <th style={{ textAlign: "left" }}>
          Dispositivo de clave dinámica o SMS
        </th>

        <th style={{ textAlign: "left" }}>
          Tiempo de espera para la segunda transacción:
        </th>
      </tr>
    </thead>

    <tbody>
      <tr>
        <td style={{ textAlign: "left" }}>
          En este banco, los límites **dependen del sistema de autenticación**.
        </td>

        <td style={{ textAlign: "left" }}>
          **CLP $350.000**
        </td>

        <td style={{ textAlign: "left" }}>
          Límites transaccionales en curso: hasta **$2.000.000 diarios (CLP)**
        </td>

        <td style={{ textAlign: "left" }}>
          Límites transaccionales en curso:
          hasta **$5.000.000 diarios (CLP)**
        </td>

        <td style={{ textAlign: "left" }}>
          48 horas
        </td>
      </tr>
    </tbody>
  </Table>
</Accordion>

***

### Tabla de límites transaccionales

📊 Esta tabla muestra el **resumen de los datos clave** y permite comparar valores de manera rápida y visual.

<HTMLBlock>{`
<table style="border-collapse: collapse; width: 100%; text-align: left; font-family: Arial, sans-serif;">
  <thead>
    <tr style="background-color: #FC2B5F; color: white;">
      <th style="padding: 12px;">Banco</th>
      <th style="padding: 12px;">Primera transacción</th>
      <th style="padding: 12px;">Tiempo de espera</th>
      <th style="padding: 12px;">Transacción en curso</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="padding: 12px;"><img src="https://files.readme.io/b93f49c82927cb2af650266f65cb7b98b103bd866bad86e68d9ded22ce121c9f-Captura_de_pantalla_2025-08-11_a_las_2.50.26_p._m..png" alt="Banco de Chile" height="30"> Banco de Chile</td>
      <td>$350.000</td>
      <td>12 horas</td>
      <td>$2.000.000 / $5.000.000</td>
    </tr>
    <tr>
      <td style="padding: 12px;"><img src="https://files.readme.io/78a50dbf947abcc2763916ad40c6575ed46012d94bdee2e8810e1888eb23416f-descarga.png" alt="Banco Itaú" height="30"> Banco Itaú</td>
      <td>$200.000 / $300.000</td>
      <td>24 horas</td>
      <td>$5.000.000</td>
    </tr>
    <tr>
      <td style="padding: 12px;"><img src="https://files.readme.io/8df8568b17affdeba21d3ee6be41717630245b6336daa493b5eb862585435d70-bci-banco-credito-logo-png_seeklogo-311385.png" alt="Banco BCI" height="30"> Banco BCI</td>
      <td>$250.000 / $600.000</td>
      <td>24 horas</td>
      <td>$5.000.000 / $7.000.000</td>
    </tr>
    <tr>
      <td style="padding: 12px;"><img src="https://files.readme.io/7a13f4a615d27e1f3f638235406ef265f590911efe1d7c52b0fc1941ac8326cd-740ea7d2f0c8131a98ac574312bc7c45.jpg" alt="Banco Estado" height="30"> Banco Estado</td>
      <td>$100.000 / $250.000</td>
      <td>24 horas</td>
      <td>$1.000.000 / $5.000.000</td>
    </tr>
    <tr>
      <td style="padding: 12px;"><img src="https://files.readme.io/4a05e25bd70c57cf44a21f5531483b2a8cc3c6299b6baf8606f35fb44ac8f996-descarga_1.png" alt="Banco Santander" height="30"> Banco Santander</td>
      <td>$250.000</td>
      <td>24 horas</td>
      <td>$5.000.000</td>
    </tr>
    <tr>
      <td style="padding: 12px;"><img src="https://files.readme.io/c71f20243b30b466401940e3d0424d64763cc55b7a9215094a555d43ff91f69f-descarga_2.png" alt="Banco Falabella" height="30"> Banco Falabella</td>
      <td>$200.000</td>
      <td>24 horas</td>
      <td>$7.000.000</td>
    </tr>
    <tr>
      <td style="padding: 12px;"><img src="https://files.readme.io/88c8d0732d449f32986a24cbac1768a36ba2ba93a7a3a993f5780c05be60c374-descarga.jpeg" height="30"> Banco Security</td>
      <td>$350.000</td>
      <td>48 horas</td>
      <td>$2.000.000 / $5.000.000</td>
    </tr>
  </tbody>
</table>
`}</HTMLBlock>

<br />

### Plazos para usuarios nuevos

<Callout icon="❗️" theme="error">
  **Recuerda que**

  Para los nuevos usuarios, el tiempo de espera para la segunda transacción **oscila entre 12 y 48 horas**.
</Callout>

Para garantizar una buena experiencia de pago, te recomendamos realizar un **seguimiento de este plazo y de la actividad del cliente**. Si un usuario necesita hacer un depósito antes de que finalice este período, se puede usar un proveedor alternativo temporalmente y evitar transacciones rechazadas.

Una vez finalizado el período de espera, recomendamos **enrutar todas las transacciones a través de ProntoPaga**. Una vez que el usuario ya ha registrado su cuenta, el proceso de pago se vuelve más rápido.

## Crea un nuevo pago

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `PagaConTuBanco` como método de pago en el body de la solicitud.

<NotaFirma />

La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros.

<NotaWebhooks />

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

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un enlace para procesar el pago, así como un identificador de pago del sistema.

### Pago en el banco

El cliente podrá continuar el proceso siguiendo las instrucciones en pantalla. Se redireccionará al cliente al sitio web de la institución bancaria que haya seleccionado para pagar, en donde podrá iniciar sesión y hacer la transferencia.

### Confirmación de un pago

Una vez que el usuario haya completado el proceso de pago en su banco, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`.

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los PayIns](https://docs.prontopaga.com/docs/payins-status).

***

## Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, puedes hacer pruebas con nuestros demos:

<Embed url="https://experience.prontopaga.com/" href="https://experience.prontopaga.com/" typeOfEmbed="iframe" height="1000px" width="100%" iframe="true" html="false" />

***

<br />

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
    * 📥 Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu *front-end*. Puedes [descargarlos aquí](https://prontopagalatam-my.sharepoint.com/:f:/g/personal/tahbet_reategui_prontopaga_com/EtPhXrMz3TxAtA11de5jVZEB3yowkpS1i2v6lm_eMKkB7g?e=KXcZX5).
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
