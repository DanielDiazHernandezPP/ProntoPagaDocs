---
title: Códigos bancarios para PayIns con transferencias
excerpt: En este artículo se muestran las listas de códigos bancarios por país.
deprecated: false
hidden: false
metadata:
  title: Códigos bancarios para PayIns con transferencias | ProntoPaga Docs
  description: >-
    Cómo crear pagos por transferencia en Chile y Perú con Create Payment: envía
    el bankCode correcto y consulta aquí las listas de bancos y un ejemplo de
    payload.
  image: >-
    https://files.readme.io/6a73613a99c856ebb8da4030e21a37ee867a3deaeb5d8a02a0e7d2d1c1677b94-Captura_de_pantalla_2025-09-08_a_las_4.24.49_p._m..png
  keywords:
    - ProntoPaga
    - transferencias bancarias
    - bankCode
    - códigos bancarios
    - Chile
    - Perú
    - CLP
    - PEN
    - Create Payment
    - API de pagos
    - integración de pagos
    - payins
    - payouts
    - webhook
    - firma HMAC
    - ejemplo de payload
    - bancos peruanos
    - bancos chilenos
    - pagos con banco
    - pasarela de pagos
  robots: index
---
Para crear un nuevo pago por **transferencia bancaria en Chile y Perú**, es necesario utilizar el endpoint [Create Payment](https://docs.prontopaga.com/reference/create-payment#/), y **enviar el código bancario** en el campo `bankCode`. El valor de `bankCode` depende del país.

***

## Perú

Lista de códigos bancarios para Perú.

```json
[
    {
        "code": "PE_19",
        "name": "Banco de Crédito del Perú",
        "country": "PE",
        "logo": "https://prontopaga.com/img/gateways/bcp-1-1694533686.png"
    },
    {
        "code": "PE_20",
        "name": "Interbank",
        "country": "PE",
        "logo": "https://prontopaga.com/img/gateways/interbank-2-1694533661.png"
    },
    {
        "code": "PE_23",
        "name": "BBVA Continental",
        "country": "PE",
        "logo": "https://prontopaga.com/img/gateways/bbva-1-1694533357.png"
    },
    {
        "code": "PE_36",
        "name": "Caja Municipal de Ahorro y Crédito Arequipa",
        "country": "PE",
        "logo": "https://prontopaga.com/img/gateways/caja-arequipa-1730914923.svg"
    },
    {
        "code": "PE_39",
        "name": "Caja Municipal de Ahorro y Crédito Huancayo",
        "country": "PE",
        "logo": "https://prontopaga.com/img/gateways/image-2-1730915860.png"
    },
    {
        "code": "PE_961",
        "name": "Banco Pichincha",
        "country": "PE",
        "logo": "https://prontopaga.com/img/gateways/banco-pichincha-1730901988.svg"
    },
    {
        "code": "PE_962",
        "name": "Banco Alfin",
        "country": "PE",
        "logo": "https://prontopaga.com/img/gateways/alfin-1730916360.svg"
    },
    {
        "code": "PE_963",
        "name": "Banco Falabella",
        "country": "PE",
        "logo": "https://prontopaga.com/img/gateways/banks-6-1730916948.svg"
    }
]
```

***

## Chile

Lista de códigos bancarios para Chile.

```json
[
  {
    "code": "CL_487",
    "name": "Banco BICE",
    "country": "CL",
    "logo": "https://sandbox.insospa.com/img/gateways/type-bice-isotype-true-1712676182.svg"
  },
  {
    "code": "CL_488",
    "name": "Consorcio",
    "country": "CL",
    "logo": "https://sandbox.insospa.com/img/gateways/type-consorcio-1712676204.svg"
  },
  {
    "code": "CL_489",
    "name": "Banco de Chile",
    "country": "CL",
    "logo": "https://sandbox.insospa.com/img/gateways/type-banco-de-chile-isotype-true-1712676244.svg"
  },
  {
    "code": "CL_490",
    "name": "Banco del Estado",
    "country": "CL",
    "logo": "https://sandbox.insospa.com/img/gateways/banco-estado-iso-1712676299.svg"
  },
  {
    "code": "CL_491",
    "name": "Banco Falabella",
    "country": "CL",
    "logo": "https://sandbox.insospa.com/img/gateways/type-falabella-isotype-true-1712676321.svg"
  },
  {
    "code": "CL_493",
    "name": "Itaú",
    "country": "CL",
    "logo": "https://sandbox.insospa.com/img/gateways/type-itau-1712676384.svg"
  },
  {
    "code": "CL_494",
    "name": "Banco Ripley",
    "country": "CL",
    "logo": "https://sandbox.insospa.com/img/gateways/type-ripley-isotype-true-1712679477.svg"
  },
  {
    "code": "CL_495",
    "name": "Banco Santander",
    "country": "CL",
    "logo": "https://sandbox.insospa.com/img/gateways/type-santader-isotype-true-1712676526.svg"
  },
  {
    "code": "CL_496",
    "name": "Banco Security",
    "country": "CL",
    "logo": "https://sandbox.insospa.com/img/gateways/type-security-isotype-true-1712676685.svg"
  },
  {
    "code": "CL_497",
    "name": "BCI",
    "country": "CL",
    "logo": "https://sandbox.insospa.com/img/gateways/type-bci-isotype-true-1712676707.svg"
  },
  {
    "code": "CL_503",
    "name": "Scotiabank",
    "country": "CL",
    "logo": "https://sandbox.insospa.com/img/gateways/type-scotiabank-isotype-true-1712676743.svg"
  }
]
```

***

### Parámetros

Este ejemplo muestra los parámetros con los datos de Perú.

```json
{
"currency": "PEN",
  "country": "PE",
  "amount": 100,
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "12345678912",
  "paymentMethod": "PagaConTuBanco",
  "bankCode": "PE_490",
  "urlConfirmation": "Webhook",
  "urlFinal": "example.com/successful",
  "urlRejected": "example.com/declined",
  "order": "1234",
 "sign": "Signature of the parameters"
}
```

<br />

<br />