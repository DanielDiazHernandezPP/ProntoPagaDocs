---
title: Webhooks
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Webhooks | ProntoPaga Docs
  description: >-
    Set up a webhook to receive notifications about the status of your
    transactions. Add the URL of the endpoint in the `confirmation URL`
    parameter of the transaction body to link to it.
  image: >-
    https://files.readme.io/a53e3070e1e0455e0dfb1d091d073103e28b2d3d8b919b63ad13600aca1ebd4b-Prontopaga_logotipo.png
  keywords:
    - Prontopaga notifications
    - prontopaga webhooks
    - prontopaga
    - transaction status
    - payment status
    - estado de transacciones
    - recibir notificaciones de transacciones
  robots: index
next:
  description: ''
---
**Configurar un webhook para tus transacciones** te ayudará a conocer el estado de tus PayIns y PayOuts. Estos callbacks te notificarán cuando ocurra un cambio de estado en cierta transacción.

***

## Configura un webhook

Para iniciar la configuración de tu webhook, sigue estos pasos:

1. Crea un endpoint para recibirlo, es decir, crea una nueva ruta con la URL deseada.
2. Ajusta la llamada HTTP de tu endpoint a POST.
3. Agrega el body en formato JSON.

***

## Agrega la URL a tus transacciones

Para vincular tu webhook con la transacción deseada, **agrega la URL del endpoint que creaste en el parámetro indicado del body de la transacción**, que sería`urlConfirmation` en el caso de PayIns, o `confirmationURL` en PayOuts.

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
  "sign": "Firma de los parámetros"
}
```

> 📘 Estados de las transacciones
>
> Conoce los posibles estados de los PayIns en [este enlace](https://docs.prontopaga.com/docs/payins-status). Los estados de los PayOuts, los puedes encontrar en [este artículo](https://docs.prontopaga.com/docs/payouts-status).

***

## Estructura del webhook

Estos son los posibles parámetros que se pueden entregar en el cuerpo del webhook:

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Parámetro</b></th>
      <th><b>Tipo</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>uid</td><td>string</td></tr>
    <tr><td>status</td><td>string</td></tr>
    <tr><td>amount</td><td>number</td></tr>
    <tr><td>reference</td><td>string</td></tr>
    <tr><td>clientEmail</td><td>string</td></tr>
    <tr><td>clientDocument</td><td>string</td></tr>
    <tr><td>order</td><td>string</td></tr>
    <tr><td>currency</td><td>string</td></tr>
    <tr><td>country</td><td>string</td></tr>
    <tr><td>method_type</td><td>string</td></tr>
    <tr><td>method_detail</td><td>string</td></tr>
    <tr><td>hash</td><td>string</td></tr>
    <tr><td>note</td><td>string</td></tr>
    <tr><td>sign</td><td>string</td></tr>
    <tr><td>data</td><td>string</td></tr>
    <tr><td>type</td><td>string</td></tr>
    <tr><td>statusCode</td><td>string</td></tr>
    <tr><td>startNotificationTime</td><td>string</td></tr>
    <tr><td>endNotificationTime</td><td>string</td></tr>
    <tr><td>totalRequestTime</td><td>string</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

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

***

## Ejemplos

Estos son algunos ejemplos de webhooks que podrías recibir.

### Webhook de PayIn exitoso

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

> 📘 Campos del webhook
>
> Los campos `method`, `method_type` y `method_detail` serán distintos, dependiendo del método de pago usado.

### Webhook de PayOut exitoso

```json
{      
  "uid": "01J568DSG6CP9412EFPN3QC6WD",
  "status": "success",
  "data": "3325492",
  "sign": "e198c7a2c33d697c551c445b37659e06bf7c1e92db8bae04c7a1f5411b1e8a00"
}   
```
