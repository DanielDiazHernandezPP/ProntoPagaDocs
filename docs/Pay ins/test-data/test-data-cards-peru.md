---
title: Datos de prueba Perú
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Test data for Peru
  description: >-
    The document provides test card numbers for successful and denied payment
    scenarios using various card types (Visa, MasterCard, American Express,
    Diners Club, Yape, and Union Pay) in Peru, detailing specific conditions and
    action codes for each case.
  image: >-
    https://files.readme.io/39f25b416f21c2d73d73ca3b8a6ccccc5c77fa2947cf1e9e32a36deddb63281f-Prontopaga_logotipo.png
  keywords:
    - testing
    - Prontopaga Peru
    - datos de prueba Peru
    - tarjetas de prueba Peru
    - test data Peru
    - pagos de prueba
    - Peru test credit cards
    - simulate payments Peru
    - boton Yape test
  robots: index
next:
  description: ''
---
## Tarjetas

Datos para realizar pagos en modo prueba con el servicio de pagos con tarjeta en Perú.

### Casos Exitosos

#### Visa

| Escenario                        | Número           | Mes / año | CVV | Código de acción |
| :------------------------------- | :--------------- | :-------- | :-- | :--------------- |
| Venta exitosa – con cuotas       | 4551708161768059 | 03/2028   | 111 | 000              |
| Venta exitosa – sin cuotas       | 4474118355632240 | 03/2028   | 111 | 000              |
| Venta exitosa – foránea          | 4485412049751046 | 03/2028   | 111 | 000              |
| Venta exitosa – afiliación a REC | 4474104525811674 | 03/2028   | 111 | 000              |

#### Master Card

| Escenario                        | Número           | Mes / año | CVV | Código de acción |
| :------------------------------- | :--------------- | :-------- | :-- | :--------------- |
| Venta exitosa – con cuotas       | 5160030000000317 | 03/2028   | 111 | 000              |
| Venta exitosa – sin cuotas       | 5455460920094260 | 03/2028   | 111 | 000              |
| Venta exitosa – afiliación a REC | 5443599980000447 | 03/2028   | 111 | 000              |

### Casos denegados

#### Visa

| Escenario                                | Número           | Mes / año | CVV | Código de acción |
| :--------------------------------------- | :--------------- | :-------- | :-- | :--------------- |
| Tarjeta vencida                          | 4024007126919058 | 03/2019   | 111 | 101              |
| Operación no permitida para esta tarjeta | 4916122919724598 | 03/2028   | 111 | 102              |
| Monto no permitido                       | 4242424242424242 | 03/2028   | 111 | 113              |
| Fondos insuficientes                     | 4041650444437904 | 03/2028   | 111 | 116              |
| Tarjeta inválida                         | 4111111111111111 | 03/2028   | 111 | 118              |
| Tarjeta no operativa                     | 4534410925317008 | 03/2028   | 111 | 129              |
| Tarjeta inválida                         | 4716883481987333 | 03/2028   | 111 | 180              |
| Tarjeta perdida                          | 4557885040264791 | 03/2028   | 111 | 208              |
| Tarjeta robada                           | 4557883870910971 | 03/2028   | 111 | 209              |
| Problemas de comunicación                | 4285975261967724 | 03/2028   | 111 | 666              |
| Transacción denegada por posible fraude  | 4551707477308329 | 03/2028   | 111 | 670              |
| Error en autenticación                   | 4732453453776393 | 03/2028   | 111 | 678              |
| Comercio no válido                       | 4539674409144668 | 03/2028   | 111 | 754              |
| Contactar emisor                         | 4539676788512233 | 03/2028   | 111 | 191              |
| Afiliación a REC no exitosa              | 4474103791846547 | 03/2028   | 111 | 0                |

#### Master card

| Escenario                                | Número           | Mes / año | CVV | Código de acción |
| :--------------------------------------- | :--------------- | :-------- | :-- | :--------------- |
| Tarjeta vencida                          | 5455450920104193 | 04/2019   | 111 | 101              |
| Monto no permitido                       | 5101641510088022 | 04/2023   | 111 | 113              |
| Fondos insuficientes                     | 5115422225052734 | 04/2023   | 111 | 116              |
| Tarjeta no registrada                    | 5109616945811695 | 04/2023   | 111 | 118              |
| Tarjeta no registrada (error de cvv)     | 5111053459429167 | 04/2023   | 111 | 129              |
| Tarjeta inválida                         | 5243798112895755 | 04/2023   | 111 | 180              |
| Tarjeta perdida                          | 5102851705613406 | 04/2023   | 111 | 207              |
| Tarjeta robada                           | 5105291169837406 | 04/2023   | 111 | 209              |
| Problemas de comunicación                | 5110556146550527 | 04/2023   | 111 | 666              |
| Problemas de comunicación con antifraude | 5103216920074983 | 04/2023   | 111 | 668              |
| Transacción denegada por posible fraude  | 5106248239975235 | 04/2023   | 111 | 670              |
| Error en autenticación                   | 5110109669996279 | 04/2023   | 111 | 678              |
| Comercio no válido                       | 5111886224425808 | 04/2023   | 111 | 754              |
| Contactar emisor                         | 5100538637530152 | 04/2023   | 111 | 191              |

## Paga con tu banco

Datos para pruebas en el servicio Paga con tu banco de Perú.

| Banco     | DNI      | Clave | Número de tarjeta | Clave digital | Token  |
| :-------- | :------- | :---- | :---------------- | :------------ | :----- |
| Banco BCP | 11111111 | 1234  | 1111222233334444  | 123456        | 123456 |

## Botón Yape

Datos para pruebas en el servicio de Botón Yape de Perú.

> 🚧 Motivos de rechazo para integración sin iFrame
>
> Puedes revisar los posibles motivos de rechazo, así como el mensaje que tu comercio debe mostrar al cliente en su front-end en integraciones sin iFrame en [esta página](https://docs.prontopaga.com/docs/payins-rejections#yape---primarios).

| Número de celular | OTP    | Detalle del escenario                                                                                                                                    |
| :---------------- | :----- | :------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 969929157         | 557454 | Yapero autenticado y habilitado                                                                                                                          |
| 999999999         | 284563 | Cuenta inactiva                                                                                                                                          |
| 993355231         | 784592 | Cuenta en blacklist                                                                                                                                      |
| 969929157         | 285743 | Límite diario excedido (> 500.00). **⚠️Nota:** En la integración sin iFrame, el pago es rechazado como resultado final y no es posible colocar otro OTP. |
| 991055199         | 378458 | Cuenta bloqueada por OTP. **⚠️Nota:** En la integración sin iFrame, el pago es rechazado como resultado final y no es posible colocar otro OTP.          |
| 995555126         | 678452 | Ausencia en F\&F                                                                                                                                         |
| 969929158         | 528475 | 1er intento de OTP incorrecto                                                                                                                            |
| 969929158         | 074854 | 2do intento de OTP incorreto                                                                                                                             |
| 969929158         | 875612 | 3er intento de OTP incorrecto. **⚠️Nota:** En la integración sin iFrame, el pago es rechazado como resultado final y no es posible colocar otro OTP.     |
| 969929157         | 000000 | OTP no generado                                                                                                                                          |