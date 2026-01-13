---
title: Códigos bancarios - Brasil
deprecated: false
hidden: true
metadata:
  robots: index
---
Esta guía recopila todas las instituciones financieras soportadas por ProntoPaga para pagos con Pix en Brasil.

Los valores son:

<br />

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Campo</b></th>
      <th><b>Descripción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>name</code></td>
      <td>Nombre del banco o institución financiera.</td>
    </tr>
    <tr>
      <td><code>code</code></td>
      <td>Código bancario, cuando corresponde.</td>
    </tr>
    <tr>
      <td><code>schema_skn</code></td>
      <td>Identificador que corresponde al <b>bankCode<b>/</td>
    </tr>
    <tr>
      <td><code>country</code></td>
      <td>Código del país (ISO 2).</td>
    </tr>
    <tr>
      <td><code>acronym</code></td>
      <td>Acrónimo o nombre corto del banco o institución.</td>
    </tr>
  </tbody>
</table>
`}</HTMLBlock>

<br />

Algunas entidades son:

El valor`schema_skn`corresponde al `bankCode`en el body de la solicitud.

Descarga la lista completa de [códigos de entidades financieras](https://drive.usercontent.google.com/u/0/uc?id=1ChVWHPMpM12qBWfrrBJmUSrE4XnXzozu\&export=download) que soportan transacciones con Pix en Brasil.

<br />
