---
title: Datos de prueba Argentina
excerpt: Conoce los datos de prueba disponibles para Argentina
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

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Tipo de tarjeta</b></th>
      <th><b>Número de tarjeta</b></th>
      <th><b>Fecha de vencimiento</b></th>
			<th><b>CVV</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Visa</td><td>4147463011110059</td><td>dic-29</td><td>123</td></tr>
    <tr><td>Mastercard</td><td>5165850000000008</td><td>dic-29</td><td>123</td></tr>
    <tr><td>Mastercard</td><td>5200000000002490</td><td>dic-28</td><td>123</td></tr></tr>
  </tbody>
</table>
`}</HTMLBlock>

***

### Flujo sin fricción

Conoce los

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Escenario</b></th>
      <th><b>Código de respuesta 3DS</b></th>
      <th><b>Estado de la transacción 3DS</b></th>
			<th><b>Número de tarjeta de prueba</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Sin fricciones - Totalmente autenticado</td><td>1</td><td>Y</td><td>4147463011110083<br>
        5239290700000028</td></tr>
    <tr><td>Sin fricciones - No autenticado</td><td>3</td><td>N</td><td>4147463011110091<br>
        5239290700000036</td></tr>
    <tr><td>Sin fricciones - Intento de autenticación</td><td>4</td><td>A</td><td> 4147463011110117<br>
      5239290700000044</td></tr></tr>
    <tr><td>Sin fricciones - Autenticación rechazada</td><td>3</td><td>R</td><td> 4147463011110042<br>
      5239290700000051</td></tr></tr>
    <tr><td>Sin fricciones - No se puede autenticar</td><td>6</td><td>U</td><td> 4147463011110067<br>
        4147463011110125<br>
        5239290700000069</td></tr></tr>
  </tbody>
</table>
`}</HTMLBlock>

<br />

<HTMLBlock>{`
<table style="border-collapse: collapse; width: 100%;">
  <thead>
    <tr style="background-color: #ff1f55; color: white; text-align: left;">
      <th>Scenario</th>
      <th>3DS Response Code</th>
      <th>3DS Transaction Status</th>
      <th>Test card number</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>Frictionless - Fully Authenticated</td>
      <td>1</td>
      <td>Y</td>
      <td>
        4147463011110083<br>
        5239290700000028
      </td>
    </tr>

    <tr>
      <td>Frictionless - Not Authenticated</td>
      <td>3</td>
      <td>N</td>
      <td>
        4147463011110091<br>
        5239290700000036
      </td>
    </tr>

    <tr>
      <td>Frictionless - Attempted Authentication</td>
      <td>4</td>
      <td>A</td>
      <td>
        4147463011110117<br>
        5239290700000044
      </td>
    </tr>

    <tr>
      <td>Frictionless - Rejected Authentication</td>
      <td>3</td>
      <td>R</td>
      <td>
        4147463011110042<br>
        5239290700000051
      </td>
    </tr>

    <tr>
      <td>Frictionless - Unable to Authenticate</td>
      <td>6</td>
      <td>U</td>
      <td>
        4147463011110067<br>
        4147463011110125<br>
        5239290700000069
      </td>
    </tr>
  </tbody>
</table>
`}</HTMLBlock>
