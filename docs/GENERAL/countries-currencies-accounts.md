---
title: Países, monedas y cuentas
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Países, monedas y cuentas | ProntoPaga Docs
  description: >-
    It details the country and currency codes for Brazil, Chile, Ecuador and
    Peru, and describes the types of bank accounts available in each country,
    with additional specifications for Payphone accounts in Ecuador.
  image: >-
    https://files.readme.io/be36fa313f9f8077f025d1c7cde5dd8750254ccc721b0d9a406702c67dabf553-Prontopaga_logotipo.png
  keywords:
    - countries
    - currencies
    - accounts
    - api
    - prontopaga
    - moneda
    - cuentas bancarias
    - países
  robots: index
next:
  description: ''
---
## Países y monedas

Los códigos de país están en formato ISO 3166-1 alpha-2. Las monedas están en formato ISO 4217.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>País</b></th>
      <th><b>Código del país (ISO 3166-1 alpha-2)</b></th>
      <th><b>Código de moneda (ISO 4217)</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Argentina</td><td>AR</td><td>ARS</td></tr>
    <tr><td>Brasil</td><td>BR</td><td>BRL / USD</td></tr>
    <tr><td>Chile</td><td>CL</td><td>CLP</td></tr></tr>
    <tr><td>Ecuador</td><td>EC</td><td>USD</td></tr>
    <tr><td>Perú</td><td>PE</td><td>PEN / USD</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

***

## Tipos de cuentas

El tipo de cuenta se especifica con un solo caracter en la mayoría de los casos (a excepción de Ecuador), como se describe a continuación.

### Brasil

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Tipo de cuenta</b></th>
      <th><b>Descripción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>1</td><td>Corriente</td></tr>
    <tr><td>2</td><td>Salario</td></tr>
    <tr><td>3</td><td>Ahorro</td></tr>
    <tr><td>4</td><td>Transaccional</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

***

### Chile

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Tipo de cuenta</b></th>
      <th><b>Descripción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>C</td><td>Cuenta corriente</td></tr>
    <tr><td>S</td><td>Cuenta de ahorros</td></tr>
    <tr><td>V</td><td>Cuenta Rut / Visa</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

***

### Ecuador

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Tipo de cuenta</b></th>
      <th><b>Descripción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>AHO</td><td>Ahorros</td></tr>
    <tr><td>CTE</td><td>Corriente</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

#### Payphone

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Tipo de cuenta</b></th>
      <th><b>Descripción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>C</td><td>Cliente</td></tr>
    <tr><td>B</td><td>Comercio</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

***

### Perú

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Tipo de cuenta</b></th>
      <th><b>Descripción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>A</td><td>Ahorros</td></tr>
    <tr><td>C</td><td>Corriente</td></tr>
  </tbody>
</table>
`}</HTMLBlock>
