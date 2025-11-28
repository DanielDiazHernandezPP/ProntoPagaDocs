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

### Ejemplo 1

La siguiente tabla muestra una recopilación de datos de prueba para validar pagos con tarjeta.

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

### Ejemplo 2

<Callout icon="❗️" theme="error">
  **Ten en cuenta que**

  Los siguientes datos de prueba se pueden utilizar para probar el procesamiento de tarjetas de crédito en _Gateway_, pero no son compatibles automáticamente con todos los simuladores de _host_ de autorización.
</Callout>

A continuación encontrarás más ejemplos de datos de prueba necesarios para validar tu integración.

<HTMLBlock>{`
<div style="overflow-x: auto; width: 100%;">
<table style="border-collapse: collapse; width: 100%; min-width: 800px;">
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Número de tarjeta</b></th>
      <th><b>PIN</b></th>
      <th><b>CVV</b></th>
      <th><b>Mes de expiración</b></th>
      <th><b>Año de expiración</b></th>
      <th><b>Marca</b></th>
      <th><b>Tipo</b></th>
      <th><b>Descripción</b></th>
    </tr>
  </thead>
  <tbody>

    <tr>
      <td>4761739001010010</td>
      <td>1234</td>
      <td>002</td>
      <td>10</td>
      <td>30</td>
      <td>Visa</td>
      <td>Prepago</td>
      <td>Transacción exitosa</td>
    </tr>

    <tr>
      <td>4005520000000129</td>
      <td>1234</td>
      <td>002</td>
      <td>10</td>
      <td>30</td>
      <td>Visa</td>
      <td>Crédito</td>
      <td>Transacción exitosa</td>
    </tr>

    <tr>
      <td>5413330089010640</td>
      <td>4315</td>
      <td>002</td>
      <td>10</td>
      <td>30</td>
      <td>Mastercard</td>
      <td>Crédito</td>
      <td>Transacción exitosa</td>
    </tr>

    <tr>
      <td>5413330089600119</td>
      <td>4315</td>
      <td>002</td>
      <td>10</td>
      <td>30</td>
      <td>Mastercard</td>
      <td>Crédito</td>
      <td>Transacción exitosa</td>
    </tr>

    <tr>
      <td>374245001721009</td>
      <td>1234</td>
      <td>002</td>
      <td>10</td>
      <td>30</td>
      <td>Amex</td>
      <td>Crédito</td>
      <td>Transacción exitosa</td>
    </tr>

    <tr>
      <td>4035874000424977</td>
      <td>-</td>
      <td>977</td>
      <td>12</td>
      <td>30</td>
      <td>Visa</td>
      <td>Crédito</td>
      <td>Transacción exitosa</td>
    </tr>

    <tr>
      <td>5413330089010640</td>
      <td>-</td>
      <td>Cualquiera</td>
      <td>12</td>
      <td>30</td>
      <td>Mastercard</td>
      <td>Crédito</td>
      <td>Transacción exitosa</td>
    </tr>

  </tbody>
</table>
</div>
`}</HTMLBlock>

***

<br />

## Datos de prueba de autenticación/3-D Secure

<Callout icon="❗️" theme="error">
  **Escenarios soportados**

  Ten en cuenta que las tarjetas de prueba 3DS están configuradas únicamente para soportar los escenarios de autenticación listados a continuación y no están diseñadas para realizar pruebas de extremo a extremo que incluyan el procesamiento de la autorización.
</Callout>

<Callout icon="👍" theme="okay">
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

A continuación encontrarás datos de prueba de flujos sin fricción con el método 3DS

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

***

### Flujo de challenge

A continuación encontrarás los datos de prueba para flujos de challenge.

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
      <td>Flujo de challenge - Respuestas configurables</td>
      <td>1 o 4 o 6 o 3</td>
      <td>Y o A o U o N/R</td>
      <td>
        4147463011110059<br>
        5239290700000002
      </td>
    </tr>

    <tr>
      <td>Flujo de challenge - Totalmente autenticado</td>
      <td>1</td>
      <td>Y</td>
      <td>
        4147463011110109
      </td>
    </tr>

    <tr>
      <td>Flujo de challenge - Autenticación rechazada</td>
      <td>3</td>
      <td>R</td>
      <td>
        4147463011110034<br>
        5239290700000010
      </td>
    </tr>

  </tbody>
</table>
`}</HTMLBlock>

***

### Flujo de challenge con el método 3DS

A continuación encontrarás los datos de prueba necesarios para validar tu integración.

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
      <td>Flujo de challenge – Respuestas configurables</td>
      <td>1 o 4 o 6 o 3</td>
      <td>Y o A o U o N/R</td>
      <td>
        4099000000001960<br>
        4149011500000527<br>
        4265880000000064<br>
        5204740000002745<br>
        5544330000000235
      </td>
    </tr>

    <tr>
      <td>Flujo de challenge – Autenticación rechazada</td>
      <td>3</td>
      <td>R</td>
      <td>
        4149011500000535<br>
        5204740000002760
      </td>
    </tr>

  </tbody>
</table>
`}</HTMLBlock>

***

### Datos de prueba de autenticación 3D Secure

<Callout icon="📘" theme="info">
  **Antes de iniciar**

  Revisa los valores de los códigos de respuesta y estado de las transacciones 3DS. Puedes revisar todos los valores en la documentación externa de Fiserv.
</Callout>

#### ✅ Valores de estado de la transacción

<table>
  <thead>
    <tr>
      <th style={{ backgroundColor: "#ff1f55", color: "white", textAlign: "left" }}>
        <b>Valor</b>
      </th>
      <th style={{ backgroundColor: "#ff1f55", color: "white", textAlign: "left" }}>
        <b>Descripción</b>
      </th>
    </tr>
  </thead>

  <tbody>
    <tr><td>Y</td><td>Verificación de autenticación exitosa.</td></tr>
    <tr><td>N</td><td>No autenticado / cuenta no verificada. La transacción es denegada.</td></tr>
    <tr><td>U</td><td>No se pudo realizar la autenticación o verificación por un problema técnico u otro motivo, según lo indicado en Authentication Response (ARes) o Results Request (RReq).</td></tr>
    <tr><td>A</td><td>Se realizaron intentos de autenticación o verificación. No se autenticó, pero se proporciona una prueba del intento.</td></tr>
    <tr><td>D</td><td>Challenge requerido. Autenticación desacoplada confirmada.</td></tr>
    <tr><td>R</td><td>Autenticación o verificación de la cuenta rechazada por el emisor.</td></tr>
  </tbody>
</table>


#### ✅ Código de respuesta 3DS

<br />

<table>
  <thead>
    <tr>
      <th style={{ backgroundColor: "#ff1f55", color: "white", textAlign: "left" }}>
        <b>Valor</b>
      </th>

      <th style={{ backgroundColor: "#ff1f55", color: "white", textAlign: "left" }}>
        <b>Descripción</b>
      </th>
    </tr>
  </thead>

  <tbody>
    <tr><td>1</td><td>Autenticación exitosa (Visa ECI 05, Mastercard ECI 02).</td></tr>
    <tr><td>2</td><td>Autenticación exitosa sin AVV (Visa ECI 05, Mastercard ECI 02).</td></tr>
    <tr><td>3</td><td>Autenticación fallida o rechazada por el DS o el ACS (la transacción es rechazada por la pasarela).</td></tr>
    <tr><td>4</td><td>Intento de autenticación (Visa ECI 06, Mastercard ECI 01).</td></tr>
    <tr><td>5</td><td>No se pudo autenticar / el DS no responde (Visa ECI 07).</td></tr>
    <tr><td>6</td><td>No se pudo autenticar / el ACS o el DS no pueden autenticar al titular de la tarjeta (Visa ECI 07).</td></tr>
  </tbody>
</table>
