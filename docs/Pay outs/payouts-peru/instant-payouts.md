---
title: Transferencia (retiros instantáneos)
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    To make an instant payout in Peru through ProntoPaga, capture the
    beneficiary's data and send a request to the API with a bearer token and
    secret signature; transactions are authenticated and secure.
  keywords:
    - instant payouts
    - ' instant payout'
    - ' bank transfer'
    - ' cci'
    - ' interbank'
    - ' guide'
    - ' installation'
    - ' peru'
    - ' prontopaga'
    - ' how to make an instant payout'
    - ' how to make an interbank payout'
    - ' direct banks'
  robots: index
next:
  description: ''
---
Hacer un retiro en Perú a una cuenta bancaria o interbancaria consiste en capturar los datos necesarios de la persona que recibirá el pago y hacer una solicitud a través de nuestra API con un bearer token y una firma secreta. De esta forma, las transacciones se autentican y se realizan de forma segura.

ProntoPaga te permite hacer retiros instantáneos en Perú. Para ello, cuentas con dos modalidades disponibles:

- Retiros vía CCI (Cuenta bancaria / Cuenta interbancaria), los cuales se cubren en esta página.
- [Retiros vía wallet.](https://docs.prontopaga.com/docs/instant-withdrawal-wallet)

A continuación, puedes encontrar información detallada de cómo hacer retiros vía CCI.

## ¿Cómo funciona?

El proceso de payout con transferencia (retiros instantáneos) en Perú consta de cuatro etapas principales:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/149a54f4d90599dd421fbd4e89786257bb12ae426173ca0bf8852615248dfa92-Peru-01.jpg",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


1. **Selección de método.** El cliente elige retirar dinero por medio de transferencia en tu sitio web o aplicación. 
2. **Ingreso de datos.** El cliente ingresa los datos necesarios para que el retiro sea realizado (como banco, número de cuenta bancaria e interbancaria y tipo de cuenta) y confirma la transacción. 
3. **Validación y Captura. **ProntoPaga valida la información del retiro, hace la solicitud de transferencia al banco y mueve el dinero desde la cuenta del comercio hacia la cuenta del cliente.  
4. **Confirmación.** El cliente recibe una confirmación de retiro exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

## Lista de bancos

La lista de códigos bancarios para pay outs de tipo transferencia la puedes encontrar en [este artículo](https://docs.prontopaga.com/docs/bank-codes-transfer), dividida por países. El código bancario debe enviarse en el campo `bankCode` del endpoint de creación de un retiro.

## Crear un nuevo retiro

Consulta el endpoint de [Crear un nuevo retiro](https://docs.prontopaga.com/reference/payout) y envía una solicitud con un body similar a la siguiente.

`accountNumber` es el número de cuenta bancaria al que se depositará.

`accountInterbank` es el número de cuenta interbancaria al que se depositará.

<NotaFirma />

```json
{
  "amount": "10.00",
  "document_id": "12345678912",
  "beneficiaryName": "John",
  "beneficiaryLastName": "Doe",
  "beneficiaryEmail": "johndoe@example.com",
  "beneficiaryPhone": "999999999",
  "accountNumber": "10070010030000",
  "accountType": "C",
  "bankCode": "011",
  "data": "1234",
  "confirmationURL": "Webhook",
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

### Confirmación de un retiro

Una vez que hayas completado el proceso, ProntoPaga devolverá los datos de la transacción a la URL que especificaste en `confirmationURL`. 

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un retiro en el siguiente enlace: [Estados de los pay outs](https://docs.prontopaga.com/docs/payouts-status).

### Webhook

Al finalizar una transacción exitosa, recibirás un webhook similar al ejemplo mostrado a continuación.

```json
{      
      "uid": "01J568DSG6CP9412EFPN3QC6WD",
      "status": "success",
      "data": "3325492",
      "type": "bank",
      "sign": "e198c7a2c33d697c551c445b37659e06bf7c1e92db8bae04c7a1f5411b1e8a00",
      "statusCode": "200",
      "startNotificationTime": "2024-08-13 12:16:54",
      "endNotificationTime": "2024-08-13 12:16:54",
      "totalRequestTime": "0.393352"
}         
```

## Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, también puedes hacer pruebas con [nuestros demos](https://demo.insospa.com/transactions/deposit).