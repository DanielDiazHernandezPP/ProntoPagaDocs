---
title: Wallet (retiros instantáneos)
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    To make instant payouts to a wallet in Peru with ProntoPaga, you must
    capture the beneficiary's data and make a request through the API with a
    bearer token and a secret signature; there are several wallets available.
  keywords:
    - instant payout
    - ' instant payout to a wallet'
    - ' wallet payout'
    - ' peru'
    - ' prontopaga'
    - ' guide'
    - ' integration'
    - ' how to make a payout to a wallet'
  robots: index
next:
  description: ''
---
Hacer un retiro en Perú a una wallet consiste en capturar los datos necesarios de la persona que recibirá el pago y hacer una solicitud a través de nuestra API con un Bearer Token y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.

ProntoPaga te permite hacer retiros instantáneos en Perú. Para ello, cuentas con dos modalidades disponibles:

* [Retiros vía CCI](https://docs.prontopaga.com/docs/instant-withdrawals) (Cuenta bancaria / Cuenta interbancaria)
* Retiros vía wallet.

A continuación, puedes encontrar información detallada de cómo hacer retiros instantáneos desde el comercio a una wallet específica.

## ¿Cómo funciona?

Wallet (retiros instantáneos) es un método digital utilizado en Perú que permite retirar fondos desde una aplicación de billetera digital en el celular. Para utilizar este método, el cliente debe seleccionar la opción "Billetera digital", tener una cuenta activa en una billetera compatible, ingresar su número de teléfono, seleccionar la billetera y confirmar la operación. Para conocer el listado de billeteras disponibles, puedes consultarlo [aquí](https://docs.prontopaga.com/docs/instant-payout-wallet#wallets-disponibles).

El proceso de payout con wallet en Perú consta de cuatro etapas principales:

<Image align="center" src="https://files.readme.io/150951e1035b2d433aa2f6ee32afcbffa29cb598f966cb725da2ece36d368bfe-Peru-02.jpg" />

1. **Selección de método.** El cliente elige retirar dinero por medio de wallet en tu sitio web o aplicación.
2. **Ingreso de datos.** El cliente ingresa los datos necesarios para que el retiro sea realizado (como su número de teléfono y wallet) y confirma la transacción.
3. **Validación y Captura.** ProntoPaga valida la información del retiro, hace la solicitud de transferencia a la wallet y mueve el dinero desde la cuenta del comercio hacia la cuenta del cliente.
4. **Confirmación.** El cliente recibe una confirmación de retiro exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

## Wallets disponibles

Este es la lista completa de las wallets disponibles para hacer pay outs con ProntoPaga en Perú:

| Marca                           | Valor        |
| :------------------------------ | :----------- |
| Banco Falabella                 | falabella    |
| Wayki Caja Cusco                | cajaCusco    |
| Banco Nación                    | nacion       |
| Mibanco                         | mibanco      |
| Tarjeta oh                      | oh           |
| Banco GNB                       | gnb          |
| BanBif                          | banbif       |
| Caja Lima                       | cajaLima     |
| Compartamos Financiera          | compartamos  |
| Caja Huancayo                   | cajaHuancayo |
| Caja Piura                      | cajaPiura    |
| Dale                            | dale         |
| Financiera Confianza            | confianza    |
| Bancom                          | comercio     |
| Ripley                          | ripley       |
| Santander                       | santander    |
| Banco Pichincha                 | pichincha    |
| Banco de Crédito del Perú (BCP) | bcp          |
| Financiera Efectiva             | efectiva     |
| Caja Ica                        | cajaIca      |
| Caja Trujillo                   | cajaTrujillo |
| Interbank                       | interbank    |
| Luqea                           | luqea        |
| Caja Sullana                    | cajaSullana  |
| Prexpe                          | prexpe       |
| Yape                            | yape         |
| Plin                            | plin         |
| Bim                             | bim          |

## Consulta de wallets por número telefónico (Opcional)

Si deseas conocer las wallets asociadas al número telefónico celular del beneficiario, primero deberás consultar el endpoint de [Lista de wallets](https://docs.prontopaga.com/reference/wallets-list) y agregar el teléfono en la URL de la petición.

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

## Solicitud de retiro instantáneo vía wallet

Después de seleccionar una wallet del listado obtenido en el [endpoint anterior](https://docs.prontopaga.com/reference/wallets-list), deberás hacer una petición al endpoint de [Crear un nuevo retiro a wallet](https://docs.prontopaga.com/reference/instant-payout-peru-wallet) y enviar una solicitud con un body similar al siguiente.

<NotaFirma />

```json
{
  "amount": "2.00",
  "document_id": "12345678912",
  "beneficiaryName": "John",
  "beneficiaryLastName": "Doe",
  "beneficiaryEmail": "johndoe@example.com",
  "beneficiaryPhone": "999999999",
  "data": "1234",
  "confirmationURL": "https://www.webhook.com",
  "currency": "PEN",
  "country": "PE",
  "wallet": "luqea",
  "sign": "Signature of the parameters"
}
```

<NotaWebhooks />

### Posibles respuestas

Como respuesta a una solicitud de pago exitosa, recibirás un identificador del retiro en el sistema, el estado del retiro y datos adicionales de la transacción.

Si la transacción es exitosa, recibirás la siguiente respuesta:

```json
{
  "uid": "01J4PG5MET5CV6BCCQB8HRFC2X",
  "status": "new",
  "data": "1633611",
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

### Confirmación de un retiro

Una vez que hayas completado el proceso, ProntoPaga devolverá los datos de la transacción a la URL que especificaste en `confirmationURL`.

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un retiro en el siguiente enlace: [Estados de los pay outs](https://docs.prontopaga.com/docs/payouts-status).

### Webhook

Al finalizar una transacción exitosa, recibirás un webhook similar al ejemplo mostrado a continuación.

```json
{      
      "uid": "01J8MWMSW7KCVG6YE6X1GZABCD",
      "status": "success",
      "data": "332512",
      "statusCode": "200",
      "startNotificationTime": "2024-08-25 12:16:54",
      "endNotificationTime": "2024-08-25 12:16:54",
      "totalRequestTime": "0.791377",
      "sign": "e198c7a2c33d697c551c445b37659e06bf7c1e92db8bae00c7a1f5411b1e7a00"
}         
```

## Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, también puedes hacer pruebas con [nuestros demos](https://demo.insospa.com/transactions/deposit).

## Certifica tu integración

La certificación de la integración en *sandbox* es un paso obligatorio que todos los comercios deben realizar antes de recibir sus credenciales de producción. Su propósito es asegurar que la integración cumpla con los estándares técnicos, funcionales y de seguridad requeridos por ProntoPaga. Dentro de esta sección, se establecen los requisitos que deben cumplirse sin excepción para que la certificación sea aprobada.

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