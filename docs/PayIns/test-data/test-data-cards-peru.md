---
title: Datos de prueba Perú (PayIns)
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Datos de prueba Perú (payins) | ProntoPaga Docs
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
> 🚧 Webhook de la transacción
>
> El webhook de la transacción se enviará automáticamente en el ambiente _Sandbox_ únicamente si se utilizan los datos de prueba especificados en nuestra documentación. Para los demás métodos de pago, será necesario contactar con el soporte técnico por correo electrónico, proporcionando el **uid** y la **referencia** de la transacción, para que podamos cambiar el estado a `success` y, de este modo, se reciba el webhook correspondiente.

***

## Tarjetas

Datos para realizar pagos en modo prueba con el servicio de pagos con tarjeta en Perú.

### Casos Exitosos

#### Visa

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Escenario</b></th>
      <th><b>Número</b></th>
      <th><b>Mes / año</b></th>
      <th><b>CVV</b></th>
      <th><b>Código de acción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Venta exitosa – con cuotas</td><td>4551708161768059</td><td>03 / 2028</td><td>111</td><td>000</td></tr>
    <tr><td>Venta exitosa – sin cuotas</td><td>4474118355632240</td><td>03 / 2028</td><td>111</td><td>000</td></tr>
    <tr><td>Venta exitosa – foránea</td><td>4485412049751046</td><td>03 / 2028</td><td>111</td><td>000</td></tr>
    <tr><td>Venta exitosa – afiliación a REC</td><td>4474104525811674</td><td>03 / 2028</td><td>111</td><td>000</td></tr>    
  </tbody>
</table>
`}</HTMLBlock>

| Escenario                        | Número           | Mes / año | CVV | Código de acción |
| :------------------------------- | :--------------- | :-------- | :-- | :--------------- |
| Venta exitosa – con cuotas       | 4551708161768059 | 03/2028   | 111 | 000              |
| Venta exitosa – sin cuotas       | 4474118355632240 | 03/2028   | 111 | 000              |
| Venta exitosa – foránea          | 4485412049751046 | 03/2028   | 111 | 000              |
| Venta exitosa – afiliación a REC | 4474104525811674 | 03/2028   | 111 | 000              |

#### MasterCard

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Escenario</b></th>
      <th><b>Número</b></th>
      <th><b>Mes / año</b></th>
      <th><b>CVV</b></th>
      <th><b>Código de acción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Venta exitosa – con cuotas</td><td>5160030000000317</td><td>03 / 2028</td><td>111</td><td>000</td></tr>
    <tr><td>Venta exitosa – sin cuotas</td><td>5455460920094260</td><td>03 / 2028</td><td>111</td><td>000</td></tr>
    <tr><td>Venta exitosa – foránea</td><td>5443599980000447</td><td>03 / 2028</td><td>111</td><td>000</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

| Escenario                        | Número           | Mes / año | CVV | Código de acción |
| :------------------------------- | :--------------- | :-------- | :-- | :--------------- |
| Venta exitosa – con cuotas       | 5160030000000317 | 03/2028   | 111 | 000              |
| Venta exitosa – sin cuotas       | 5455460920094260 | 03/2028   | 111 | 000              |
| Venta exitosa – afiliación a REC | 5443599980000447 | 03/2028   | 111 | 000              |

### Casos denegados

#### Visa

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Escenario</b></th>
      <th><b>Número</b></th>
      <th><b>Mes / año</b></th>
      <th><b>CVV</b></th>
      <th><b>Código de acción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Afiliación a REC no exitosa</td><td>4474103791846547</td><td>03 / 2028</td><td>111</td><td>0</td></tr>
		<tr><td>Tarjeta vencida</td><td>4024007126919058</td><td>03 / 2019</td><td>111</td><td>101</td></tr>
    <tr><td>Operación no permitida para esta tarjeta</td><td>4916122919724598</td><td>03 / 2028</td><td>111</td><td>102</td></tr>
    <tr><td>Monto no permitido</td><td>4242424242424242</td><td>03 / 2028</td><td>111</td><td>113</td></tr>
    <tr><td>Fondos insuficientes</td><td>4041650444437904</td><td>03 / 2028</td><td>111</td><td>116</td></tr>  
    <tr><td>Tarjeta inválida</td><td>4111111111111111</td><td>03 / 2028</td><td>111</td><td>118</td></tr>
    <tr><td>Tarjeta no operativa</td><td>4534410925317008</td><td>03 / 2028</td><td>111</td><td>129</td></tr>
    <tr><td>Tarjeta inválida</td><td>4716883481987333</td><td>03 / 2028</td><td>111</td><td>180</td></tr>
    <tr><td>Contactar emisor</td><td>4539676788512233</td><td>03 / 2028</td><td>111</td><td>191</td></tr>
    <tr><td>Tarjeta perdida</td><td>4557885040264791</td><td>03 / 2028</td><td>111</td><td>208</td></tr>   
    <tr><td>Tarjeta robada</td><td>4557883870910971</td><td>03 / 2028</td><td>111</td><td>209</td></tr>
    <tr><td>Problemas de comunicación</td><td>4285975261967724</td><td>03 / 2028</td><td>111</td><td>666</td></tr>
    <tr><td>Transacción denegada por posible fraude</td><td>4551707477308329	</td><td>03 / 2028</td><td>111</td><td>670</td></tr>
    <tr><td>Error en autenticación</td><td>4732453453776393</td><td>03 / 2028</td><td>111</td><td>678</td></tr>   
    <tr><td>Comercio no válido</td><td>4539674409144668</td><td>03 / 2028</td><td>111</td><td>754</td></tr>    
  </tbody>
</table>
`}</HTMLBlock>

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

#### MasterCard

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

***

## Paga con tu banco

Datos para pruebas en el servicio Paga con tu banco de Perú.

| Banco     | DNI      | Clave | Número de tarjeta | Clave digital | Token  |
| :-------- | :------- | :---- | :---------------- | :------------ | :----- |
| Banco BCP | 11111111 | 1234  | 1111222233334444  | 123456        | 123456 |

***

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
| 995555126         | 678452 | Ausencia en F&F                                                                                                                                          |
| 969929158         | 528475 | 1er intento de OTP incorrecto                                                                                                                            |
| 969929158         | 074854 | 2do intento de OTP incorreto                                                                                                                             |
| 969929158         | 875612 | 3er intento de OTP incorrecto. **⚠️Nota:** En la integración sin iFrame, el pago es rechazado como resultado final y no es posible colocar otro OTP.     |
| 969929157         | 000000 | OTP no generado                                                                                                                                          |
