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
      <th><b>Mes/año</b></th>
      <th><b>CVV</b></th>
      <th><b>Código de acción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Venta exitosa – con cuotas</td><td>4551708161768059</td><td>03/2028</td><td>111</td><td>000</td></tr>
    <tr><td>Venta exitosa – sin cuotas</td><td>4474118355632240</td><td>03/2028</td><td>111</td><td>000</td></tr>
    <tr><td>Venta exitosa – foránea</td><td>4485412049751046</td><td>03/2028</td><td>111</td><td>000</td></tr>
    <tr><td>Venta exitosa – afiliación a REC</td><td>4474104525811674</td><td>03/2028</td><td>111</td><td>000</td></tr>    
  </tbody>
</table>
`}</HTMLBlock>

#### MasterCard

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Escenario</b></th>
      <th><b>Número</b></th>
      <th><b>Mes/año</b></th>
      <th><b>CVV</b></th>
      <th><b>Código de acción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Venta exitosa – con cuotas</td><td>5160030000000317</td><td>03/2028</td><td>111</td><td>000</td></tr>
    <tr><td>Venta exitosa – sin cuotas</td><td>5455460920094260</td><td>03/2028</td><td>111</td><td>000</td></tr>
    <tr><td>Venta exitosa – afiliación a REC</td><td>5443599980000447</td><td>03/2028</td><td>111</td><td>000</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

### Casos denegados

#### Visa

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Escenario</b></th>
      <th><b>Número</b></th>
      <th><b>Mes/año</b></th>
      <th><b>CVV</b></th>
      <th><b>Código de acción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Afiliación a REC no exitosa</td><td>4474103791846547</td><td>03/2028</td><td>111</td><td>0</td></tr>
		<tr><td>Tarjeta vencida</td><td>4024007126919058</td><td>03/2019</td><td>111</td><td>101</td></tr>
    <tr><td>Operación no permitida para esta tarjeta</td><td>4916122919724598</td><td>03/2028</td><td>111</td><td>102</td></tr>
    <tr><td>Monto no permitido</td><td>4242424242424242</td><td>03/2028</td><td>111</td><td>113</td></tr>
    <tr><td>Fondos insuficientes</td><td>4041650444437904</td><td>03/2028</td><td>111</td><td>116</td></tr>  
    <tr><td>Tarjeta inválida</td><td>4111111111111111</td><td>03/2028</td><td>111</td><td>118</td></tr>
    <tr><td>Tarjeta no operativa</td><td>4534410925317008</td><td>03/2028</td><td>111</td><td>129</td></tr>
    <tr><td>Tarjeta inválida</td><td>4716883481987333</td><td>03/2028</td><td>111</td><td>180</td></tr>
    <tr><td>Contactar emisor</td><td>4539676788512233</td><td>03/2028</td><td>111</td><td>191</td></tr>
    <tr><td>Tarjeta perdida</td><td>4557885040264791</td><td>03/2028</td><td>111</td><td>208</td></tr>   
    <tr><td>Tarjeta robada</td><td>4557883870910971</td><td>03/2028</td><td>111</td><td>209</td></tr>
    <tr><td>Problemas de comunicación</td><td>4285975261967724</td><td>03/2028</td><td>111</td><td>666</td></tr>
    <tr><td>Transacción denegada por posible fraude</td><td>4551707477308329</td><td>03/2028</td><td>111</td><td>670</td></tr>
    <tr><td>Error en autenticación</td><td>4732453453776393</td><td>03/2028</td><td>111</td><td>678</td></tr>   
    <tr><td>Comercio no válido</td><td>4539674409144668</td><td>03/2028</td><td>111</td><td>754</td></tr>    
  </tbody>
</table>
`}</HTMLBlock>

#### MasterCard

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Escenario</b></th>
      <th><b>Número</b></th>
      <th><b>Mes/año</b></th>
      <th><b>CVV</b></th>
      <th><b>Código de acción</b></th>
    </tr>
  </thead>
  <tbody>
		<tr><td>Tarjeta vencida</td><td>5455450920104193</td><td>04/2019</td><td>111</td><td>101</td></tr>
    <tr><td>Monto no permitido</td><td>5101641510088022</td><td>04/2023</td><td>111</td><td>113</td></tr>
    <tr><td>Fondos insuficientes</td><td>5115422225052734</td><td>04/2023	</td><td>111</td><td>116</td></tr>  
    <tr><td>Tarjeta no registrada</td><td>5109616945811695</td><td>04/2023</td><td>111</td><td>118</td></tr>
    <tr><td>Tarjeta no registrada (error de cvv)</td><td>5111053459429167</td><td>04/2023</td><td>111</td><td>129</td></tr>
    <tr><td>Tarjeta inválida</td><td>5243798112895755</td><td>04/2023</td><td>111</td><td>180</td></tr>
    <tr><td>Contactar emisor</td><td>5100538637530152</td><td>04/2023</td><td>111</td><td>191</td></tr>
    <tr><td>Tarjeta perdida</td><td>5102851705613406</td><td>04/2023</td><td>111</td><td>207</td></tr>   
    <tr><td>Tarjeta robada</td><td>5105291169837406</td><td>04/2023</td><td>111</td><td>209</td></tr>
    <tr><td>Problemas de comunicación</td><td>5110556146550527</td><td>04/2023</td><td>111</td><td>666</td></tr>
    <tr><td>Problemas de comunicación con antifraude</td><td>5103216920074983</td><td>04/2023</td><td>111</td><td>668</td></tr>
    <tr><td>Transacción denegada por posible fraude</td><td>5106248239975235</td><td>04/2023</td><td>111</td><td>670</td></tr>
    <tr><td>Error en autenticación</td><td>5110109669996279</td><td>04/2023</td><td>111</td><td>678</td></tr>   
    <tr><td>Comercio no válido</td><td>5111886224425808</td><td>04/2023</td><td>111</td><td>754</td></tr>    
  </tbody>
</table>
`}</HTMLBlock>

***

## Paga con tu banco

Datos para pruebas en el servicio Paga con tu banco de Perú.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Banco</b></th>
      <th><b>DNI</b></th>
      <th><b>Clave</b></th>
      <th><b>Número de tarjeta</b></th>
      <th><b>Clave digital</b></th>
      <th><b>Token</b></th>
    </tr>
  </thead>
  <tbody>
		<tr><td>Banco BCP</td><td>11111111</td><td>1234</td><td>1111222233334444</td><td>123456</td><td>123456</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

***

## Botón Yape

Datos para pruebas en el servicio de Botón Yape de Perú.

> 🚧 Motivos de rechazo para integración sin iFrame
>
> Puedes revisar los posibles motivos de rechazo, así como el mensaje que tu comercio debe mostrar al cliente en su front-end en integraciones sin iFrame en [esta página](https://docs.prontopaga.com/docs/payins-rejections#yape---primarios).

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Número de celular</b></th>
      <th><b>OTP</b></th>
      <th><b>Detalle del escenario</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>969929157</td><td>557454</td><td>Yapero autenticado y habilitado</td></tr>
		<tr><td>999999999</td><td>284563</td><td>Cuenta inactiva</td></tr>    
		<tr><td>993355231</td><td>784592</td><td>Cuenta en blacklist</td></tr>    
		<tr><td>969929157</td><td>285743</td><td>Límite diario excedido (> 500.00). ⚠️<b>Nota:</b> En la integración sin iFrame, el pago es rechazado como resultado final y no es posible colocar otro OTP</td></tr>    
 		<tr><td>991055199</td><td>378458</td><td>Cuenta bloqueada por OTP. ⚠️<b>Nota:</b> En la integración sin iFrame, el pago es rechazado como resultado final y no es posible colocar otro OTP</td></tr>   
		<tr><td>995555126</td><td>678452</td><td>Ausencia en F&F</td></tr>
		<tr><td>969929158</td><td>528475</td><td>1er intento de OTP incorrecto</td></tr>
		<tr><td>969929158</td><td>074854</td><td>2do intento de OTP incorreto</td></tr>
		<tr><td>969929158</td><td>875612</td><td>3er intento de OTP incorrecto. ⚠️<b>Nota:</b> En la integración sin iFrame, el pago es rechazado como resultado final y no es posible colocar otro OTP</td></tr>
		<tr><td>969929157</td><td>000000</td><td>OTP no generado</td></tr>
  </tbody>
</table>
`}</HTMLBlock>
