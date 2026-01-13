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

En la tabla a continuación, podrás consultar las entidades aptas para transacciones vía CCI, así como aquellas que requieren o no requieren validación de pagos a terceros.

| Entidad                   | Apta para CCI (con validación de terceros) | Apta para CCI (sin validación de terceros) |
| :------------------------ | :----------------------------------------- | :----------------------------------------- |
| BANCO DE CREDITO DEL PERU | ✅ YES                                      | ✅ YES                                      |
| INTERBANK                 | ✅ YES                                      | ✅ YES                                      |
| SCOTIABANK                | ❌ NO                                       | ✅ YES                                      |
| BBVA                      | ✅ YES                                      | ✅ YES                                      |
| BANCO NACION              | ❌ NO                                       | ✅ YES                                      |
| BANCOM                    | ❌ NO                                       | ✅ YES                                      |
| BANCO PICHINCHA           | ✅ YES                                      | ✅ YES                                      |
| BANBIF                    | ❌ NO                                       | ✅ YES                                      |
| CREDISCOTIA               | ❌ NO                                       | ✅ YES                                      |
| MI BANCO                  | ❌ NO                                       | ✅ YES                                      |
| BANCO GNB                 | ✅ YES                                      | ✅ YES                                      |
| BANCO FALABELLA           | ❌ NO                                       | ✅ YES                                      |
| BANCO RIPLEY              | ✅ YES                                      | ✅ YES                                      |
| BANCO ALFIN               | ✅ YES                                      | ✅ YES                                      |
| COMPARTAMOS FINANCIERA    | ✅ YES                                      | ✅ YES                                      |
| TARJETA OH                | ✅ YES                                      | ✅ YES                                      |
| FINANCIERA EFECTIVA       | ✅ YES                                      | ✅ YES                                      |
| FINANCIERA CONFIANZA      | ✅ YES                                      | ✅ YES                                      |
| PREXPE                    | ✅ YES                                      | ✅ YES                                      |
| CAJA LIMA                 | ✅ YES                                      | ✅ YES                                      |
| CAJA PIURA                | ✅ YES                                      | ✅ YES                                      |
| CAJA TRUJILLO             | ✅ YES                                      | ✅ YES                                      |
| CMAC AREQUIPA             | ❌ NO                                       | ✅ YES                                      |
| WAYKI CAJA CUSCO          | ✅ YES                                      | ✅ YES                                      |
| CAJA HUANCAYO             | ❌ NO                                       | ✅ YES                                      |
| CAJA ICA                  | ✅ YES                                      | ✅ YES                                      |
| CAJA LOS ANDES            | ✅ YES                                      | ✅ YES                                      |
| COOPERATIVA ABACO         | ✅ YES                                      | ✅ YES                                      |
| LIGO                      | ✅ YES                                      | ✅ YES                                      |
| DALE                      | ✅ YES                                      | ✅ YES                                      |

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

| Código | Mensaje                                                     |
| :----- | :---------------------------------------------------------- |
| AC01   | Número de cuenta incorrecta                                 |
| AC03   | Número de cuenta a acreditar incorrecta                     |
| AC06   | Cuenta bloqueada                                            |
| AC07   | Cuenta a acreditar cerrada                                  |
| AC11   | Moneda de la cuenta a acreditar invalida                    |
| AC14   | Tipo de cuenta a acreditar invalida                         |
| AG01   | Transacción prohibida                                       |
| AG03   | Operación no soportada                                      |
| AM01   | Monto Cero                                                  |
| AM02   | Monto no permitido                                          |
| AM03   | Error interno en moneda de la transacción                   |
| AM04   | Saldo de garantía insuficiente                              |
| AM05   | Duplicado                                                   |
| AM09   | Monto equivocado                                            |
| AM11   | Error interno en moneda de la transacción                   |
| AM13   | Monto excede límite de operación                            |
| BE08   | Nombre de cliente originante faltante                       |
| BE15   | Id de referencia requerido                                  |
| BE16   | Código de identificación de originante invalido             |
| BE22   | Nombre de beneficiario faltante                             |
| CH11   | Identificador de cliente receptor incorrecto                |
| CH21   | Falta de elementos obligatorios                             |
| DNOR   | Entidad originante no registrada                            |
| DS0A   | Forma de datos requerida                                    |
| DS0B   | Formato de firma desconocido                                |
| DS0D   | Certificado de firma invalido                               |
| DS0H   | Entidad indirecta no autorizada                             |
| DT04   | Fecha de creación no soportada                              |
| FF02   | Error de formato                                            |
| RC01   | Estructura de identificador de entidad incorrecta           |
| RC02   | Entidad originante no autorizado                            |
| RC03   | Identificador de entidad originante invalido                |
| RC04   | Identificador de entidad receptora invalido                 |
| RR04   | Motivo regulatorio (políticas de AML/CFT)                   |
| RR10   | Set de caracteres invalido                                  |
| 9910   | Entidad receptora en sign off                               |
| 9912   | Entidad receptora no disponible                             |
| 9920   | Tipo de transacción, canal o código de transacción invalido |
| 9921   | Criterio de aplicación invalido                             |
| 9922   | Tipo de persona invalido                                    |
| 9923   | Concepto de cobro no es numérico                            |
| 9924   | Indicador de activo invalido (320)                          |
| 9934   | Entidad originante en sign off                              |
| 9946   | Entidad originante suspendida                               |
| 9947   | Entidad receptora suspendida                                |
| 9948   | Servicio IPS suspendido                                     |
| 9964   | Identificador de entidad invalido                           |

<br />

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
    * 📥 Agregar los logotipos de los diferentes métodos de retiro de ProntoPaga a tu *front-end*. Puedes [descargarlos aquí](https://drive.google.com/uc?export=download\&id=1MmsVaugP7ztzRXA_dK9wNrwKJOfHSL59).
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
