---
title: Datos de prueba Brasil (PayOuts)
excerpt: Conoce los datos de prueba para retiros instantáneos en Brasil.
deprecated: false
hidden: true
metadata:
  robots: index
---
## Retiros instantáneos con Pix

Datos de pruebas para retiro con Pix en Brasil.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>CPF</b></th>
      <th><b>Número de cuenta</b></th>
      <th><b>Código de banco</b></th>
    </tr>
  </thead>
  <tbody>
    <!-- CPF con 1 cuenta -->
    <tr>
      <td>23456789</td>
      <td>123456789</td>
      <td>001</td>
    </tr>

    <!-- CPF con 2 cuentas -->
    <tr>
      <td rowspan="2">876543215</td>
      <td>996543215</td>
      <td>237</td>
    </tr>
    <tr>
      <td>234567890</td>
      <td>104</td>
    </tr>

    <!-- Otro CPF con 2 cuentas -->
    <tr>
      <td rowspan="2">081234567</td>
      <td>345678904</td>
      <td>341</td>
    </tr>
    <tr>
      <td>456789017</td>
      <td>033</td>
    </tr>

    <!-- CPF con 1 cuenta -->
    <tr>
      <td>148259361</td>
      <td>567890123</td>
      <td>077</td>
    </tr>

    <!-- CPF con 2 cuentas -->
    <tr>
      <td rowspan="2">675498256</td>
      <td>678901236</td>
      <td>260</td>
    </tr>
    <tr>
      <td>789012341</td>
      <td>422</td>
    </tr>
  </tbody>
</table>
`}</HTMLBlock>
