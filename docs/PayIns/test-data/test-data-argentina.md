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
<Table align={["left","left","left","left"]}>
  <thead>
    <tr style={{ backgroundColor: "#ff1f55", color: "white", textAlign: "left" }}>
      <th>Escenario</th>
      <th>Código de respuesta 3DS</th>
      <th>Estado de la transacción de 3DS</th>
      <th>Número de tarjeta de prueba</th>
    </tr>
  </thead>
  <tbody>
    {/* filas aquí */}
  </tbody>
</Table>
`}</HTMLBlock>

<br />

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Escenario
      </th>

      <th style={{ textAlign: "left" }}>
        Código de respuesta 3DS
      </th>

      <th style={{ textAlign: "left" }}>
        Estado de la transacción de 3DS
      </th>

      <th style={{ textAlign: "left" }}>
        Número de tarjeta de prueba
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        Sin fricciones - Totalmente autenticado
      </td>

      <td style={{ textAlign: "left" }}>
        1
      </td>

      <td style={{ textAlign: "left" }}>
        Y
      </td>

      <td style={{ textAlign: "left" }}>
        4147463011110083
        5239290700000028
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Sin fricción - No autenticado
      </td>

      <td style={{ textAlign: "left" }}>
        3
      </td>

      <td style={{ textAlign: "left" }}>
        N
      </td>

      <td style={{ textAlign: "left" }}>
        4147463011110091
        5239290700000036
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Sin fricción - Intento de autenticación
      </td>

      <td style={{ textAlign: "left" }}>
        4
      </td>

      <td style={{ textAlign: "left" }}>
        A
      </td>

      <td style={{ textAlign: "left" }}>
        4147463011110117
        5239290700000044
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Sin fricción - Autenticación rechazada
      </td>

      <td style={{ textAlign: "left" }}>
        3
      </td>

      <td style={{ textAlign: "left" }}>
        R
      </td>

      <td style={{ textAlign: "left" }}>
        4147463011110042
        5239290700000051
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Sin fricción: no se puede autenticar
      </td>

      <td style={{ textAlign: "left" }}>
        6
      </td>

      <td style={{ textAlign: "left" }}>
        U
      </td>

      <td style={{ textAlign: "left" }}>
        4147463011110067
        4147463011110125
        5239290700000069
      </td>
    </tr>
  </tbody>
</Table>
  </tbody>
</table>
`}</HTMLBlock>
