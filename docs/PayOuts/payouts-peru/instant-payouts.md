---
title: Retiros instantáneos por Transferencia
excerpt: >-
  Conoce el paso a paso de cómo hacer un retiro instantáneo con transferencia en
  Perú.
deprecated: false
hidden: false
metadata:
  title: Retiros instantáneos por Transferencia | ProntoPaga Docs
  description: >-
    To make an instant payout in Peru through ProntoPaga, capture the
    beneficiary's data and send a request to the API with a bearer token and
    secret signature; transactions are authenticated and secure.
  image: >-
    https://files.readme.io/76579863a9262262c8b2bfffa02a66896b6e4b0d2fc377ed43e5c2aeb7e22d89-Prontopaga_logotipo.png
  keywords:
    - bank transfer Peru
    - Prontopaga Peru
    - CCI Peru withdrawal
    - make a payout Peru
    - transferencias interbancarias Perú
    - retiro bancario API Perú
    - how to make an instant payout
    - how to make an interbank payout
    - direct banks
  robots: index
next:
  description: ''
---
Hacer un retiro en Perú a una cuenta bancaria o interbancaria consiste en capturar los datos necesarios de la persona que recibirá el pago y hacer una solicitud a través de nuestra API con un Bearer Token y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.

ProntoPaga te permite hacer retiros instantáneos en Perú. Para ello, cuentas con dos modalidades disponibles:

* Retiros vía CCI (Cuenta bancaria / Cuenta interbancaria), los cuales se cubren en esta página.
* [Retiros vía wallet.](https://docs.prontopaga.com/docs/instant-withdrawal-wallet)

A continuación, puedes encontrar información detallada de cómo hacer retiros vía CCI.

***

## ¿Cómo funciona?

Transferencia (Retiros Instantáneos) es una forma de retirar fondos en Perú mediante transferencias entre cuentas bancarias e interbancarias. Para completar una transacción con este método, el cliente debe seleccionar la opción "Transferencia bancaria", ingresar su número de cuenta bancaria, CCI, el tipo de cuenta, seleccionar el banco, y confirmar la operación.

El proceso de PayOut con transferencia (retiros instantáneos) en Perú consta de cuatro etapas principales:

<Image align="center" border={false} src="https://files.readme.io/149a54f4d90599dd421fbd4e89786257bb12ae426173ca0bf8852615248dfa92-Peru-01.jpg" />

1. **Selección de método.** El cliente elige retirar dinero por medio de transferencia en tu sitio web o aplicación.
2. **Ingreso de datos.** El cliente ingresa los datos necesarios para que el retiro sea realizado (como banco, número de cuenta bancaria e interbancaria y tipo de cuenta) y confirma la transacción.
3. **Validación y Captura.** ProntoPaga valida la información del retiro, hace la solicitud de transferencia al banco y mueve el dinero desde la cuenta del comercio hacia la cuenta del cliente.
4. **Confirmación.** El cliente recibe una confirmación de retiro exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

***

## Lista de bancos

La lista de códigos bancarios para PayOuts de tipo transferencia la puedes encontrar en [este artículo](https://docs.prontopaga.com/docs/bank-codes-transfer), dividida por países. El código bancario debe enviarse en el campo `bankCode` del endpoint de creación de un retiro.

***

## Entidades

En la tabla a continuación, podrás consultar las entidades aptas para transacciones vía CCI, así como aquellas que envían el DNI.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Entidad</b></th>
      <th><b>Envía DNI</b></th>
      <th><b>Apta para CCI</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>BANCO DE CREDITO DEL PERU</td><td>✅ YES</td><td>✅ YES</td></tr>
    <tr><td>INTERBANK</td><td>✅ YES</td><td>✅ YES</td></tr>
    <tr><td>BBVA</td><td>✅ YES</td><td>✅ YES</td></tr>
    <tr><td>BANCO NACION</td><td>❌ NOT</td><td>✅ YES</td></tr>
    <tr><td>BANCOM</td><td>❌ NOT</td><td>✅ YES</td></tr>
    <tr><td>BANCO GNB</td><td>✅ YES</td><td>✅ YES</td></tr>
    <tr><td>BANCO FALABELLA</td><td>❌ NOT</td><td>✅ YES</td></tr>
    <tr><td>COMPARTAMOS FINANCIERA</td><td>✅ YES</td><td>✅ YES</td></tr>
    <tr><td>FINANCIERA EFECTIVA</td><td>✅ YES</td><td>✅ YES</td></tr>
    <tr><td>FINANCIERA CONFIANZA</td><td>✅ YES</td><td>✅ YES</td></tr>
    <tr><td>PREXPE</td><td>✅ YES</td><td>✅ YES</td></tr>
    <tr><td>WAYKI CAJA CUSCO</td><td>✅ YES</td><td>✅ YES</td></tr>
    <tr><td>CAJA ICA</td><td>✅ YES</td><td>✅ YES</td></tr>
    <tr><td>YAPE</td><td>✅ YES</td><td>✅ YES</td></tr>
    <tr><td>PLIN</td><td>✅ YES</td><td>✅ YES</td></tr>
    <tr><td>COOPERATIVA ABACO</td><td>✅ YES</td><td>✅ YES</td></tr>
    <tr><td>LIGO</td><td>✅ YES</td><td>✅ YES</td></tr>
    <tr><td>CITIBANK</td><td>❌ NOT</td><td>❌ NOT</td></tr>
    <tr><td>SCOTIABANK</td><td>❌ NOT</td><td>✅ YES</td></tr>
    <tr><td>BANCO PICHINCHA</td><td>❌ NOT</td><td>✅ YES</td></tr>
    <tr><td>BANBIF</td><td>❌ NOT</td><td>✅ YES</td></tr>
    <tr><td>CREDISCOTIA</td><td>❌ NOT</td><td>✅ YES</td></tr>
    <tr><td>MI BANCO</td><td>❌ NOT</td><td>✅ YES</td></tr>
    <tr><td>BANCO RIPLEY</td><td>✅ YES</td><td>✅ YES</td></tr>
    <tr><td>SANTANDER</td><td>❌ NOT</td><td>❌ NOT</td></tr>
    <tr><td>CREDINKA</td><td>❌ NOT</td><td>❌ NOT</td></tr>
    <tr><td>LUQEA</td><td>❌ NOT</td><td>❌ NOT</td></tr>
    <tr><td>GLOBAL66</td><td>❌ NOT</td><td>❌ NOT</td></tr>
    <tr><td>CAJA LIMA</td><td>✅ YES</td><td>✅ YES</td></tr>
    <tr><td>CAJA PIURA</td><td>✅ YES</td><td>✅ YES</td></tr>
    <tr><td>CAJA TRUJILLO</td><td>✅ YES</td><td>✅ YES</td></tr>
    <tr><td>CMAC AREQUIPA</td><td>❌ NOT</td><td>✅ YES</td></tr>
    <tr><td>CAJA SULLANA</td><td>❌ NOT</td><td>❌ NOT</td></tr>
    <tr><td>CAJA HUANCAYO</td><td>✅ YES</td><td>✅ YES</td></tr>
    <tr><td>CAJA LOS ANDES</td><td>✅ YES</td><td>✅ YES</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

***

## Crear un nuevo retiro

Consulta el endpoint de [Crear un nuevo retiro](https://docs.prontopaga.com/reference/payout) y envía una solicitud con un body similar a la siguiente.

`accountNumber` es el número de cuenta bancaria al que se depositará.

`accountInterbank` es el número de cuenta interbancaria al que se depositará.

<NotaFirma />

```json
{
  "amount": "150.90",
  "document_id": "12345678912",
  "beneficiaryName": "John",
  "beneficiaryLastName": "Doe",
  "beneficiaryEmail": "johndoe@example.com",
  "beneficiaryPhone": "999999999",
  "accountNumber": "10070010030000",
  "accountType": "C",
  "bankCode": "011",
  "data": "XYZ789",
  "confirmationURL": "https://www.webhook.com",
  "currency": "PEN",
  "country": "PE",
  "accountInterbank": "01150004004006000900",
  "sign": "Signature of the parameters"
}
```

<NotaWebhooks />

### Posibles respuestas

Como respuesta a una solicitud de pago exitosa, recibirás un identificador del retiro en el sistema, el estado del retiro y datos adicionales de la transacción.

Si la transacción es exitosa, recibirás la siguiente respuesta:

```json
{
    "uid": "01J59EC1DMW5HV8F93GSAWD24G",
    "status": "new",
    "data": "2010906",
    "reference": 9898
}
```

Si la transacción es rechazada, recibirás esta respuesta similar a esta:

```json
{
  "accountInterbank": "string accountInterbank, cannot be null"
}
```

### Motivos de rechazo

A continuación se muestran varios posibles casos de rechazo de un retiro, junto con su respectivo código.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Código</b></th>
      <th><b>Mensaje</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>AC01</td><td>Número de cuenta incorrecta</td></tr>
    <tr><td>AC03</td><td>Número de cuenta a acreditar incorrecta</td></tr>
    <tr><td>AC06</td><td>Cuenta bloqueada</td></tr>
    <tr><td>AC07</td><td>Cuenta a acreditar cerrada</td></tr>
    <tr><td>AC11</td><td>Moneda de la cuenta a acreditar invalida</td></tr>
    <tr><td>AC14</td><td>Tipo de cuenta a acreditar invalida</td></tr>
    <tr><td>AG01</td><td>Transacción prohibida</td></tr>
    <tr><td>AG03</td><td>Operación no soportada</td></tr>
    <tr><td>AM01</td><td>Monto Cero</td></tr>
    <tr><td>AM02</td><td>Monto no permitido</td></tr>
    <tr><td>AM03</td><td>Error interno en moneda de la transacción</td></tr>
    <tr><td>AM04</td><td>Saldo de garantía insuficiente</td></tr>
    <tr><td>AM05</td><td>Duplicado</td></tr>
    <tr><td>AM09</td><td>Monto equivocado</td></tr>
    <tr><td>AM11</td><td>Error interno en moneda de la transacción</td></tr>
    <tr><td>AM13</td><td>Monto excede límite de operación</td></tr>
    <tr><td>BE08</td><td>Nombre de cliente originante faltante</td></tr>
    <tr><td>BE15</td><td>Id de referencia requerido</td></tr>
    <tr><td>BE16</td><td>Código de identificación de originante invalido</td></tr>
    <tr><td>BE22</td><td>Nombre de beneficiario faltante</td></tr>
    <tr><td>CH11</td><td>Identificador de cliente receptor incorrecto</td></tr>
    <tr><td>CH21</td><td>Falta de elementos obligatorios</td></tr>
    <tr><td>DNOR</td><td>Entidad originante no registrada</td></tr>
    <tr><td>DS0A</td><td>Forma de datos requerida</td></tr>
    <tr><td>DS0B</td><td>Formato de firma desconocido</td></tr>
    <tr><td>DS0D</td><td>Certificado de firma invalido</td></tr>
    <tr><td>DS0H</td><td>Entidad indirecta no autorizada</td></tr>
    <tr><td>DT04</td><td>Fecha de creación no soportada</td></tr>
    <tr><td>FF02</td><td>Error de formato</td></tr>
    <tr><td>RC01</td><td>Estructura de identificador de entidad incorrecta</td></tr>
    <tr><td>RC02</td><td>Entidad originante no autorizado</td></tr>
    <tr><td>RC03</td><td>Identificador de entidad originante invalido</td></tr>
    <tr><td>RC04</td><td>Identificador de entidad receptora invalido</td></tr>
    <tr><td>RR04</td><td>Motivo regulatorio (políticas de AML/CFT)</td></tr>
    <tr><td>RR10</td><td>Set de caracteres invalido</td></tr>
    <tr><td>9910</td><td>Entidad receptora en sign off</td></tr>
    <tr><td>9912</td><td>Entidad receptora no disponible</td></tr>
    <tr><td>9920</td><td>	Tipo de transacción, canal o código de transacción invalido</td></tr>
    <tr><td>9921</td><td>Criterio de aplicación invalido</td></tr>
    <tr><td>9922</td><td>Tipo de persona invalido</td></tr>
    <tr><td>9923</td><td>Concepto de cobro no es numérico</td></tr>
    <tr><td>9924</td><td>Indicador de activo invalido (320)</td></tr>
    <tr><td>9934</td><td>Entidad originante en sign off</td></tr>
    <tr><td>9946</td><td>Entidad originante suspendida</td></tr>
    <tr><td>9947</td><td>Entidad receptora suspendida</td></tr>
    <tr><td>9948</td><td>Servicio IPS suspendido</td></tr>
    <tr><td>9964</td><td>Identificador de entidad invalido</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

### Confirmación de un retiro

Una vez que hayas completado el proceso, ProntoPaga devolverá los datos de la transacción a la URL que especificaste en `confirmationURL`.

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un retiro en el siguiente enlace: [Estados de los PayOuts](https://docs.prontopaga.com/docs/payouts-status).

### Webhook

Al finalizar una transacción exitosa, recibirás un webhook similar al ejemplo mostrado a continuación.

```json
{      
      "uid": "01J568DSG6CP9412EFPN3QC6WD",
      "status": "success",
      "data": "XYZ789",
      "type": "bank",
      "statusCode": "200",
      "startNotificationTime": "2024-08-13 12:16:54",
      "endNotificationTime": "2024-08-13 12:16:54",
      "totalRequestTime": "0.393352",
      "sign": "e198c7a2c33d697c551c445b37659e06bf7c1e92db8bae04c7a1f5411b1e8a00"
}         
```

***

## Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, también puedes hacer pruebas con [nuestros demos](https://demo.insospa.com/transactions/deposit).

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
    * 📥 Agregar los logotipos de los diferentes métodos de retiro de ProntoPaga a tu *front-end*. Puedes [descargarlos aquí](https://prontopagalatam-my.sharepoint.com/:f:/g/personal/tahbet_reategui_prontopaga_com/EtPhXrMz3TxAtA11de5jVZEB3yowkpS1i2v6lm_eMKkB7g?e=KXcZX5).
    * 🔎 Todos los nombres y logos de los métodos de retiro habilitados deben mostrarse de forma clara, sin modificaciones visuales o estilísticas que puedan generar confusión o inducir a errores.
    * ✅ Se recomienda ordenarlos según su popularidad o frecuencia de uso, para mejorar la experiencia del usuario y optimizar la conversión.
  </Tab>

  <Tab title="Mensajes al usuario">
    * ✅ El *checkout* debe incluir mensajes claros y visibles que orienten al usuario durante todo el proceso.

    ❗ Es obligatorio mostrar:

    * ℹ️ Montos mínimos y máximos permitidos para cada método de retiro.
    * ℹ️ Estados transaccionales con claridad: por ejemplo, **Transacción aprobada** o **Transacción rechazada**, junto con una sugerencia de los pasos a seguir en caso de que corresponda.
  </Tab>

  <Tab title="Consideraciones importantes">
    * ❌ No almacenar datos sensibles del cliente en tu base de datos.
    * ✅ La certificación se otorga únicamente si estos requisitos se cumplen en su totalidad en el entorno de *sandbox*.
    * 💻 Una vez validada la integración, se habilitarán las credenciales para el entorno productivo.
    * ⚠️ El incumplimiento de estos requisitos podrá resultar en la denegación de la certificación.
  </Tab>
</Tabs>
