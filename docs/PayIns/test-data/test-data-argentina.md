---
title: Datos de prueba Argentina
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: Datos de prueba Argentina | ProntoPaga Docs
  description: >-
    Simulate payments in Argentina using test cards with the Prontopaga API.
    Ensure your integration works with local methods before going live.
  image: >-
    https://files.readme.io/0216e2dda55fa49c0ff43b13ce1059d799990b9bb8349777307043ee4adc34bf-Prontopaga_logotipo.png
  keywords:
    - datos de prueba Argentina
    - tarjetas de prueba Argentina
    - data test Argentina
    - pagos de prueba
    - test credit cards Argentina
    - simulate payments Argentina
    - Prontopaga Argentina
  robots: index
next:
  description: ''
---
## Tarjetas

Tarjetas para realizar pagos en modo prueba con el servicio de pagos con tarjeta en Argentina.

<br />

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th>Tipo de tarjeta</th>
      <th>Número de tarjeta</th>
      <th>Fecha de vencimiento </th>
			<th>CVV</th>

    </tr>
  </thead>
  <tbody>
    <tr><td><b><em>Enable<em></b></td><td>Habilita o deshabilita el método de pago.</td></tr>
    <tr><td><b>Título</b></td><td>Nombre del método de pago que aparece en el pedido (administrador Magento).</td></tr>
    <tr><td><b><em>Merchant ID<em></b></td><td>Código de comercio en soles creado al momento de la afiliación.</td></tr>
    <tr><td><b><em>Merchant ID Dollar<em></b></td><td>Código de comercio en dólares creado al momento de la afiliación.</td></tr>
    <tr><td><b>Usuario</b></td><td>Usuario de acceso que permite invocar al API de seguridad y crear un token de acceso.</td></tr>
    <tr><td><b>Contraseña</b></td><td>Contraseña de acceso que permite invocar al API de Seguridad y crear un <em>token<em> de acceso.</td></tr>
    <tr><td><b><em>Debug<em></b></td><td>Activa o desactiva el modo producción.<br>• <em>YES<em> ⇒ Desarrollo<br>• NO ⇒ Producción</td></tr>
    <tr><td><b>Título del formulario</b></td><td>Nombre del método de pago que aparece en el <em>checkout<em>.</td></tr>
    <tr><td><b>Descripción en el formulario</b></td><td>Descripción del método de pago que aparece en el <em>checkout<em>.</td></tr>
    <tr><td><b>Subir logo</b></td><td>Subir imagen del logo que aparecerá en el formulario.<br>Tamaño sugerido: 187x40px.</td></tr>
    <tr><td><b>Color del botón</b></td><td>Define el color del botón “Pagar” en el formulario.<br>Valor por defecto: <span style="color:#FF0000; font-weight:bold;">#FF0000</span></td></tr>
    <tr><td><b>Mostrar cantidad</b></td><td>Muestra el importe a pagar en el formulario.</td></tr>
    <tr><td><b>Tamaño botón</b></td><td>Tamaño del botón de pago.<br>• <em>SMALL<em><br>• <em>MEDIUM<em><br>• <em>LARGE<em><br>• <em>DEFAULT<em></td></tr>
    <tr><td><b>Política de devolución URL</b></td><td>Dirección URL de las políticas de devolución.</td></tr>
    <tr><td><b><em>WebSite<em> Ip</b></td><td>Dirección IP del servidor.</td></tr>
    <tr><td><b>Términos y condiciones URL</b></td><td>Dirección URL de los términos y condiciones del comercio.</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

***

##

| Tipo de tarjeta | Número de tarjeta | Fecha de vencimiento | CVV |
| :-------------- | :---------------- | :------------------- | :-- |
| Visa            | 4147463011110059  | dic-29               | 123 |
| Mastercard      | 5165850000000008  | dic-29               | 123 |
| Mastercard      | 5200000000002490  | dic-28               | 123 |
