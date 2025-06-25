---
title: Datos de prueba Perú
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    The document provides test card numbers for successful and denied payment
    scenarios using various card types (Visa, MasterCard, American Express,
    Diners Club, and Union Pay) in Peru, detailing specific conditions and
    action codes for each case.
  keywords:
    - test data
    - ' test'
    - ' cards'
    - ' card numbers'
    - ' peru'
    - ' testing'
    - ' prontopaga'
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

#### American Express

| Escenario                  | Número          | Mes / año | CVV | Código de acción |
| :------------------------- | :-------------- | :-------- | :-- | :--------------- |
| Venta exitosa – con cuotas | 371064649323968 | 03/2028   | 111 | 000              |
| Venta exitosa – sin cuotas | 371204534881155 | 03/2028   | 111 | 000              |

#### Diners Club

| Escenario                  | Número         | Mes / año | CVV | Código de acción |
| :------------------------- | :------------- | :-------- | :-- | :--------------- |
| Venta exitosa – con cuotas | 36006616055724 | 04/2025   | 111 | 000              |
| Venta exitosa – sin cuotas | 36340477773855 | 04/2025   | 111 | 000              |

#### Union Pay

| Escenario                  | Número           | Mes / año | CVV | Código de acción |
| :------------------------- | :--------------- | :-------- | :-- | :--------------- |
| Venta exitosa – con cuotas | 6210945888010005 | 10/2030   | 123 | 000              |
| Venta exitosa – Foranea    | 6210945888021    | 10/2030   | 123 | 000              |

<br />

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

#### American Express

| Escenario                                   | Número          | Mes / año | CVV | Código de acción |
| :------------------------------------------ | :-------------- | :-------- | :-- | :--------------- |
| Tarjeta vencida                             | 371160951393498 | 01/2019   | 111 | 101              |
| Fondos insuficientes                        | 371327381068590 | 01/2024   | 111 | 116              |
| Tarjeta no registrada                       | 370374318198760 | 01/2024   | 111 | 118              |
| Tarjeta no registrada (error de cvv)        | 371045592151431 | 01/2024   | 111 | 129              |
| Tarjeta inválida                            | 311111111111111 | 01/2024   | 111 | 180              |
| Transacción inválida                        | 371448663683011 | 01/2024   | 111 | 190              |
| Tarjeta perdida                             | 371540506350103 | 01/2024   | 111 | 207              |
| Tarjeta robada                              | 371631798378041 | 01/2024   | 111 | 207              |
| Tienda inhabilitada                         | 371032217060171 | 01/2024   | 111 | 401              |
| La operación ya se encuentra en un depósito | 371950721798434 | 01/2024   | 111 | 476              |
| Código de comercio no existe o es inválido  | 371143974183930 | 01/2024   | 111 | 479              |
| Problemas de comunicación                   | 349999481735341 | 01/2024   | 111 | 666              |
| Problemas de comunicación con antifraude    | 371912610030071 | 01/2024   | 111 | 668              |
| Transacción denegada por posible fraude     | 340010734769274 | 01/2024   | 111 | 670              |
| Error en autenticación                      | 371461600047737 | 01/2024   | 111 | 678              |

#### Diners Club

| Escenario                                   | Número         | Mes / año | CVV | Código de acción |
| :------------------------------------------ | :------------- | :-------- | :-- | :--------------- |
| Tarjeta vencida                             | 36953865709495 | 04/2019   | 111 | 101              |
| Fondos insuficientes                        | 36344311372031 | 05/2024   | 111 | 116              |
| Tarjeta no registrada                       | 36165277401757 | 05/2024   | 111 | 118              |
| Tarjeta no registrada (error de cvv)        | 36161915044570 | 05/2024   | 111 | 129              |
| Tarjeta inválida                            | 30042507084040 | 05/2024   | 111 | 180              |
| Transacción inválida                        | 36552045187919 | 05/2024   | 111 | 190              |
| Tarjeta perdida                             | 36174837286856 | 05/2024   | 111 | 207              |
| Tarjeta robada                              | 36482193207873 | 05/2024   | 111 | 207              |
| Tienda inhabilitada                         | 36445590978511 | 05/2024   | 111 | 401              |
| La operación ya se encuentra en un depósito | 36346782517671 | 05/2024   | 111 | 476              |
| Código de comercio no existe o es inválido  | 36344465159135 | 05/2024   | 111 | 479              |
| Problemas de comunicación                   | 36484318063264 | 05/2024   | 111 | 666              |
| Problemas de comunicación con antifraude    | 36124375262074 | 05/2024   | 111 | 668              |
| Transacción denegada por posible fraude     | 36165181797514 | 05/2024   | 111 | 670              |
| Error en autenticación                      | 36006973925121 | 05/2024   | 111 | 678              |

#### Union Pay

| Escenario                                   | Número              | Mes / año | CVV | Código de acción |
| :------------------------------------------ | :------------------ | :-------- | :-- | :--------------- |
| Tarjeta vencida                             | 6210945888040000007 | 09/2020   | 123 | 101              |
| Operación no permitida para esta tarjeta    | 6210946888053       | 10/2030   | 123 | 102              |
| Monto no permitido                          | 6210946888060008    | 10/2030   | 123 | 113              |
| Fondos insuficientes                        | 6210946888070000009 | 10/2030   | 123 | 116              |
| Tarjeta inválida                            | 62111111111111100   | 10/2030   | 123 | 118              |
| Tarjeta no operativa                        | 6210946888080006    | 10/2030   | 123 | 129              |
| Tarjeta inválida                            | 6210946888090005    | 10/2030   | 123 | 180              |
| Tarjeta perdida                             | 6210945888100004    | 10/2030   | 123 | 207              |
| Tarjeta robada                              | 6210946888110001    | 10/2030   | 123 | 209              |
| Problemas de comunicación                   | 6210945888120002    | 10/2030   | 123 | 666              |
| La operación ya se encuentra en un depósito | 6210945888130001    | 10/2030   | 123 | 476              |
| Comercio no válido                          | 6210946888140008    | 10/2030   | 123 | 754              |
| Contactar emisor                            | 6210946888150007    | 10/2030   | 123 | 191              |
| Transacción denegada por posible fraude     | 6210946888160006    | 10/2030   | 123 | 670              |
| Tienda inhabilitada                         | 6210946888170005    | 10/2030   | 123 | 401              |
| Código de comercio no existe o es inválido  | 6210946888180004    | 10/2030   | 123 | 479              |
| Problemas de comunicación con antifraude    | 8171999900000000021 | 10/2030   | 123 | 668              |
| Error en autenticación                      | 8163999900010       | 10/2030   | 123 | 678              |

## Paga con tu banco

Datos para pruebas en el servicio Paga con tu banco de Perú.

| Banco     | DNI      | Clave | Número de tarjeta | Clave digital | Token  |
| :-------- | :------- | :---- | :---------------- | :------------ | :----- |
| Banco BCP | 11111111 | 1234  | 1111222233334444  | 123456        | 123456 |

## Botón Yape

Datos para pruebas en el servicio de Botón Yape de Perú.

| Número de celular | Código de aprobación |
| :---------------- | :------------------- |
| 969929157         | 557454               |