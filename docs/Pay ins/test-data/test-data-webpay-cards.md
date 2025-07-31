---
title: Datos de prueba Chile
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Datos de prueba Chile | ProntoPaga Docs
  description: >-
    This document provides a list of test cards for the Webpay service in Chile,
    indicating the card type, details and whether transactions are approved or
    declined.
  keywords:
    - webpay card numbers
    - Prontopaga chile
    - datos de prueba Chile
    - tarjetas de prueba Chile
    - data test Chile
    - pagos de prueba
    - test credit cards Chile
    - simulate payments Chile
  robots: index
next:
  description: ''
---
> 🚧 Webhook
>
> Para recibir el webhook de la transacción durante las pruebas, contacta a soporte técnico por medio de correo electrónico y proporciona el **uid** y **referencia** de la transacción.

## Tarjetas

Tarjetas para realizar pagos en modo prueba con el servicio de Webpay en Chile.

| Tipo de tarjeta     | Detalle                                                      | Resultado                                                                          |
| :------------------ | :----------------------------------------------------------- | :--------------------------------------------------------------------------------- |
| VISA (crédito)      | 4051 8856 0044 6623 **CVV** 123 Cualquier fecha de caducidad | Genera transacciones aprobadas.                                                    |
| AMEX                | 3700 0000 0002 032 **CVV** 1234 Cualquier fecha de caducidad | Genera transacciones aprobadas.                                                    |
| MasterCard          | 5186 0595 5959 0568 **CVV** 123 Cualquier fecha de caducidad | Genera transacciones rechazadas.                                                   |
| Red compra (débito) | 4051 8842 3993 7763                                          | Genera transacciones aprobadas (para operaciones que permiten débito Red compra).  |
| Red compra          | 4511 3466 6003 7060                                          | Genera transacciones aprobadas (para operaciones que permiten débito Red compra).  |
| Red compra          | 5186 0085 4123 3829                                          | Genera transacciones rechazadas (para operaciones que permiten débito Red compra). |
| Prepago VISA        | 4051 8860 0005 6590 **CVV** 123 msg\_testCard4               | Genera transacciones aprobadas.                                                    |
| Prepago MasterCard  | 5186 1741 1062 9480 **CVV** 123 Cualquier fecha de caducidad | Genera transacciones rechazadas.                                                   |

Además, puedes usar los siguientes datos para tus pruebas con Webpay:

| RUT / RUT Usuario | Clave / Clave de transferencia |
| :---------------- | :----------------------------- |
| 11.111.111-1      | 123                            |

## Paga con tu banco

Datos para pruebas en el servicio Paga con tu banco de Chile.

| Banco           | RUT        | Clave   | Cuenta     | Coordenadas | Verificación                |
| :-------------- | :--------- | :------ | :--------- | :---------- | :-------------------------- |
| Banco Estado    | 11111111-1 | 1234    | Primera    | NA          | Método: bepass. Clave: 1234 |
| Banco Santander | 415792638  | jonsnow | Cualquiera | 00 00 00    | NA                          |
| Banco de Test   | 11111111-1 | 111111  | Primera    | 11 11 11    | 11 11 11                    |