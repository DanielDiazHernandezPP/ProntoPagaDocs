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
Hacer un retiro en Perú a una wallet consiste en capturar los datos necesarios de la persona que recibirá el pago y hacer una solicitud a través de nuestra API con un bearer token y una firma secreta. De esta forma, las transacciones se autentican y se realizan de forma segura.

ProntoPaga te permite hacer retiros instantáneos en Perú. Para ello, cuentas con dos modalidades disponibles:

* [Retiros vía CCI](https://docs.prontopaga.com/docs/instant-withdrawals) (Cuenta bancaria / Cuenta interbancaria)
* Retiros vía wallet.

A continuación, puedes encontrar información detallada de cómo hacer retiros instantáneos desde el comercio a una wallet específica.

## ¿Cómo funciona?

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
  "confirmationURL": "Webhook",
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
  "reference": "8290",
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
      "sign": "e198c7a2c33d697c551c445b37659e06bf7c1e92db8bae00c7a1f5411b1e7a00",
      "statusCode": "200",
      "startNotificationTime": "2024-08-25 12:16:54",
      "endNotificationTime": "2024-08-25 12:16:54",
      "totalRequestTime": "0.791377"
}         
```

## Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, también puedes hacer pruebas con [nuestros demos](https://demo.insospa.com/transactions/deposit).
