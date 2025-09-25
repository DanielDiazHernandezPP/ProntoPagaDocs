---
title: Retiros instantáneos con Wallet
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Retiros instantáneos con Wallet | ProntoPaga Docs
  description: >-
    To make instant payouts to a wallet in Peru with ProntoPaga, you must
    capture the beneficiary's data and make a request through the API with a
    bearer token and a secret signature; there are several wallets available. 
  image: >-
    https://files.readme.io/fed45f473bdde3a95f89e9e84fb1bead437b63381cb3ef38a60f2b5277978da3-Prontopaga_logotipo.png
  keywords:
    - instant payout to a wallet
    - wallet payout peru
    - prontopaga
    - guide
    - how to make a payout to a wallet
    - hacer un retiro a una wallet
  robots: index
next:
  description: ''
---
Hacer un retiro en Perú a una wallet consiste en capturar los datos necesarios de la persona que recibirá el pago y hacer una solicitud a través de nuestra API con un Bearer Token y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.

ProntoPaga te permite hacer retiros instantáneos en Perú. Para ello, cuentas con dos modalidades disponibles:

* [Retiros vía CCI](https://docs.prontopaga.com/docs/instant-withdrawals) (Cuenta bancaria / Cuenta interbancaria)
* Retiros vía wallet.

A continuación, puedes encontrar información detallada de cómo hacer retiros instantáneos desde el comercio a una wallet específica.

***

<br />

## ¿Cómo funciona?

Wallet (retiros instantáneos) es un método digital utilizado en Perú que permite retirar fondos desde una aplicación de billetera digital en el celular. Para utilizar este método, el cliente debe seleccionar la opción "Billetera digital", tener una cuenta activa en una billetera compatible, ingresar su número de teléfono, seleccionar la billetera y confirmar la operación. Para conocer el listado de billeteras disponibles, puedes consultarlo [aquí](https://docs.prontopaga.com/docs/instant-payout-wallet#wallets-disponibles).

El proceso de PayOut con wallet en Perú consta de cuatro etapas principales:

<Image align="center" border={false} src="https://files.readme.io/150951e1035b2d433aa2f6ee32afcbffa29cb598f966cb725da2ece36d368bfe-Peru-02.jpg" />

1. **Selección de método.** El cliente elige retirar dinero por medio de wallet en tu sitio web o aplicación.
2. **Ingreso de datos.** El cliente ingresa los datos necesarios para que el retiro sea realizado (como su número de teléfono y wallet) y confirma la transacción.
3. **Validación y Captura.** ProntoPaga valida la información del retiro, hace la solicitud de transferencia a la wallet y mueve el dinero desde la cuenta del comercio hacia la cuenta del cliente.
4. **Confirmación.** El cliente recibe una confirmación de retiro exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

***

<br />

## Wallets disponibles

Este es la lista completa de las wallets disponibles para hacer PayOuts con ProntoPaga en Perú:

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Marca</b></th>
      <th><b>Valor</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Banco Falabella</td><td>falabella</td></tr>
    <tr><td>Wayki Caja Cusco</td><td>cajaCusco</td></tr>
    <tr><td>Banco Nación</td><td>nacion</td></tr>
    <tr><td>Mibanco</td><td>mibanco</td></tr>
    <tr><td>Tarjeta oh</td><td>oh</td></tr>
    <tr><td>Banco GNB</td><td>gnb</td></tr>
    <tr><td>BanBif</td><td>banbif</td></tr>
    <tr><td>Caja Lima</td><td>cajaLima</td></tr>
    <tr><td>Compartamos Financiera</td><td>compartamos</td></tr>
    <tr><td>Caja Huancayo</td><td>cajaHuancayo</td></tr>
    <tr><td>Caja Piura</td><td>cajaPiura</td></tr>
    <tr><td>Dale</td><td>dale</td></tr>
    <tr><td>Financiera Confianza</td><td>confianza</td></tr>
    <tr><td>Bancom</td><td>comercio</td></tr>
    <tr><td>Ripley</td><td>ripley</td></tr>
    <tr><td>Santander</td><td>santander</td></tr>
    <tr><td>Banco Pichincha</td><td>pichincha</td></tr>
    <tr><td>Banco de Crédito del Perú (BCP)</td><td>bcp</td></tr>
    <tr><td>Financiera Efectiva</td><td>efectiva</td></tr>
    <tr><td>Caja Ica</td><td>cajaIca</td></tr>
    <tr><td>Caja Trujillo</td><td>cajaTrujillo</td></tr>
    <tr><td>Interbank</td><td>interbank</td></tr>
    <tr><td>Luqea</td><td>luqea</td></tr>
    <tr><td>Caja Sullana</td><td>cajaSullana</td></tr>
    <tr><td>Prexpe</td><td>prexpe</td></tr>
    <tr><td>Yape</td><td>yape</td></tr>
    <tr><td>Plin</td><td>plin</td></tr>
    <tr><td>Bim</td><td>bim</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

***

<br />

## Consulta de wallets por número telefónico (Opcional)

Si deseas conocer las wallets asociadas al número telefónico celular del beneficiario, primero deberás consultar el endpoint de [Lista de wallets](https://docs.prontopaga.com/reference/wallets-list) y agregar el teléfono en la URL de la petición.

<br />

### Respuesta

Si la transacción es exitosa, recibirás una respuesta similar a la siguiente:

```json
{"data": "Array",  
     { 
       "0": "yape”,  
       "1": "plin”, 
       "2": "bim”, 
       "3": "luqea”, 
       "4": "dale”,  
       "5": "prexpe”, 
       "6": "oh”, 
 } 
```

***

<br />

## Solicitud de retiro instantáneo vía wallet

Después de seleccionar una wallet del listado obtenido en el [endpoint anterior](https://docs.prontopaga.com/reference/wallets-list), deberás hacer una petición al endpoint de [Crear un nuevo retiro a wallet](https://docs.prontopaga.com/reference/instant-payout-peru-wallet) y enviar una solicitud con un body similar al siguiente.

<NotaFirma />

```json
{
  "amount": "150.90",
  "document_id": "12345678912",
  "beneficiaryName": "John",
  "beneficiaryLastName": "Doe",
  "beneficiaryEmail": "johndoe@example.com",
  "beneficiaryPhone": "999999999",
  "data": "XYZ789",
  "confirmationURL": "https://www.webhook.com",
  "currency": "PEN",
  "country": "PE",
  "wallet": "luqea",
  "sign": "Signature of the parameters"
}
```

<NotaWebhooks />

<br />

### Posibles respuestas

Como respuesta a una solicitud de pago exitosa, recibirás un identificador del retiro en el sistema, el estado del retiro y datos adicionales de la transacción.

Si la transacción es exitosa, recibirás la siguiente respuesta:

```json
{
  "uid": "01J4PG5MET5CV6BCCQB8HRFC2X",
  "status": "new",
  "data": "XYZ789",
  "reference": 8290,
  "plin": true
}
```

Si la transacción es rechazada, recibirás la siguiente respuesta:

```json
 {
    "beneficiaryPhone":  "(string) beneficiaryPhone, cannot be null."
 }
```

<br />

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

<br />

### Confirmación de un retiro

Una vez que hayas completado el proceso, ProntoPaga devolverá los datos de la transacción a la URL que especificaste en `confirmationURL`.

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un retiro en el siguiente enlace: [Estados de los PayOuts](https://docs.prontopaga.com/docs/payouts-status).

<br />

### Webhook

Al finalizar una transacción exitosa, recibirás un webhook similar al ejemplo mostrado a continuación.

```json
{      
      "uid": "01J8MWMSW7KCVG6YE6X1GZABCD",
      "status": "success",
      "data": "XYZ789",
      "statusCode": "200",
      "startNotificationTime": "2024-08-25 12:16:54",
      "endNotificationTime": "2024-08-25 12:16:54",
      "totalRequestTime": "0.791377",
      "sign": "e198c7a2c33d697c551c445b37659e06bf7c1e92db8bae00c7a1f5411b1e7a00"
}         
```

***

<br />

## Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, también puedes hacer pruebas con [nuestros demos](https://demo.insospa.com/transactions/deposit).

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
    * 📥 Agregar los logotipos de los diferentes métodos de retiro de ProntoPaga a tu *front-end*. Puedes [descargarlos aquí](https://drive.google.com/uc?export=download\&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr).
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
