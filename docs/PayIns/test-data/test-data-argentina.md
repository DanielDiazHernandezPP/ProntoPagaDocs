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

## Datos de prueba de autenticación/3-D Secure

<Callout icon="❗️">
  **Escenarios soportados**

  Ten en cuenta que las tarjetas de prueba 3DS están configuradas únicamente para soportar los escenarios de autenticación listados a continuación y no están diseñadas para realizar pruebas de extremo a extremo que incluyan el procesamiento de la autorización.
</Callout>

<Callout icon="👍">
  **Datos de vencimiento y CVV**

  **Fecha de expiración:** cualquier fecha futura, por ejemplo 12/2028  
  **CVV:** cualquier número de 3 dígitos, por ejemplo, 123
</Callout>

### Flujo sin fricción

Conoce los datos para pruebas de flujos sin fricción. 

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

***

### Flujo sin fricción con el método 3DS

<HTMLBlock>{`
<table style="border-collapse: collapse; width: 100%;">
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Escenario</b></th>
      <th><b>Código de respuesta 3DS</b></th>
      <th><b>Estado de la transacción 3DS</b></th>
      <th><b>Número de tarjeta de prueba</b></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Sin fricciones - Totalmente autenticado</td>
      <td>1</td>
      <td>Y</td>
      <td>
        4012000000012011004<br>
        4761120010000492<br>
        4265880000000007<br>
        4265880000000049<br>
        4099000000001978<br>
        5204740000002711<br>
        5204247750001471
      </td>
    </tr>
    <tr>
      <td>Sin fricciones - No autenticado</td>
      <td>3</td>
      <td>N</td>
      <td>
        4012000000012011012<br>
        4265880000000015<br>
        4099000000001986<br>
        5204740000002729<br>
        5426064000425117<br>
        5426064000425190
      </td>
    </tr>
    <tr>
      <td>Sin fricciones - Intento de autenticación</td>
      <td>4</td>
      <td>A</td>
      <td>
        4149011500000519<br>
        4265880000000023<br>
        5426064000425208
      </td>
    </tr>
    <tr>
      <td>Sin fricciones - Autenticación rechazada</td>
      <td>3</td>
      <td>R</td>
      <td>
        4265880000000031<br>
        4012000000012011038<br>
        5204740000002778
      </td>
    </tr>
    <tr>
      <td>Sin fricciones - No se puede autenticar</td>
      <td>6</td>
      <td>U</td>
      <td>
        4012000000012011020<br>
        4012001037167778<br>
        4265880000000056<br>
        4265880000000072<br>
        4265880000000080<br>
        5204740000002786<br>
        5426064000425216
      </td>
    </tr>
  </tbody>
</table>
`}</HTMLBlock>
