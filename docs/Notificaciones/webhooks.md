---
title: Recibe notificaciones de tus transacciones
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    Set up a webhook to receive notifications about the status of your
    transactions by following a few steps. Add the URL of the endpoint in the
    `confirmationURL` parameter of the transaction body to link it.
  keywords:
    - webhook
    - ' webhooks'
    - ' notifications'
    - ' prontopaga webhooks'
    - ' prontopaga'
    - ' transaction status'
    - ' payment status'
    - ' guide'
    - ' instructions'
  robots: index
next:
  description: ''
---
Configurar un webhook para tus transacciones te ayudará a conocer el estado de tus pay ins y pay outs. Estos callbacks te notificarán cuando ocurra un cambio de estado en cierta transacción.

## Configura un webhook

Para iniciar la configuración de tu webhook, sigue estos pasos:

1. Crea un endpoint para recibirlo, es decir, crea una nueva ruta con la URL deseada.
2. Ajusta la llamada HTTP de tu endpoint a POST.
3. Agrega el body en formato JSON.

## Agrega la URL a tus transacciones

Para vincular tu webhook con la transacción deseada, agrega la URL del endpoint que creaste en el parámetro indicado del body de la transacción, que sería`urlConfirmation` en el caso de pay ins, o `confirmationURL` en pay outs.

Ejemplo:

```json
{
  "currency": "CLP",
  "country": "CL",
  "amount": 1000,
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "111111111",
  "clientDocument": "11111111",
  "paymentMethod": "mach_payment",
  "urlConfirmation": "Webhook (URL del endpoint que creaste)",
  "urlFinal": "url redirect",
  "urlRejected": "url reject",
  "order": "order id",
  "sing": "Firma de los parámetros"
}
```

> 📘 Estados de las transacciones
> 
> Conoce los posibles estados de los pay ins en [este enlace](https://docs.prontopaga.com/docs/payins-status). Los estados de los pay outs, los puedes encontrar en [este artículo](https://docs.prontopaga.com/docs/payouts-status).

## Estructura de la notificación

Estos son los posibles parámetros que se pueden entregar en el cuerpo del webhook:

| Parámetro             | Tipo   |
| :-------------------- | :----- |
| uid                   | string |
| status                | string |
| amount                | number |
| method                | string |
| reference             | string |
| clientEmail           | string |
| clientDocument        | string |
| order                 | string |
| currency              | string |
| country               | string |
| method_type           | string |
| method_detail         | string |
| hash                  | string |
| note                  | string |
| sign                  | string |
| data                  | string |
| type                  | string |
| statusCode            | string |
| startNotificationTime | string |
| endNotificationTime   | string |
| totalRequestTime      | string |

## Ejemplos

Estos son algunos ejemplos de webhooks que podrías recibir.

### Webhook de pay in exitoso - Perú Tarjeta

```json
{ 
  "uid":"01HZ7HFEJZ0GN2TYNDDXC456F", 
  "status":"success", 
  "amount":10, 
  "method":"PE Tarjeta", 
  "reference":"1687348107370523",
  "clientEmail" : "johndoe@example.com",
  "clientDocument" : "999999999",         
  "order":"30023", 
  "currency":"PEN", 
  "country":"PE", 
  "method_type":"TDD", 
  "method_detail":"6623 VD", 
  "hash":"25aGF34G33HG34H41111",
  "note":null, 
  "sign":"e6f27650e5e7703949b0f2be41dde1aeab84145595c4183271e0a42f1500aa"
} 
```

### Webhook de pay out exitoso - Perú Cuenta Interbancaria

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