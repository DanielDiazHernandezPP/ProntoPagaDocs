---
title: Crear un nuevo retiro a wallet - Perú
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: instant-payout-peru-wallet
deprecated: false
hidden: false
metadata:
  title: Crear un nuevo retiro a wallet - Perú | ProntoPaga Docs
  description: >-
    Use this endpoint to make an instant payout from your business to a wallet
    in Peru. This guide explains the required parameters, how to use the
    bankCode, and how to confirm transactions through webhooks.
  image: >-
    https://files.readme.io/5ea4fd45a9e5560657cd9c0ece637024d525806f30b3f98e408a52063678c20a-Prontopaga_logotipo.png
  keywords:
    - Peru wallet payout
    - ProntoPaga payout Peru
    - send money to wallet Peru
    - instant withdrawal Peru
    - payout API ProntoPaga
    - crear un retiro a wallet
    - wallet transfer Peru
    - transferir a billetera Perú
  robots: index
next:
  description: ''
---
Prueba este endpoint directamente en Postman haciendo clic en el siguiente botón:

<HTMLBlock>{`
<!DOCTYPE html>
<html>
<body>

<p><a href="https://www.postman.com/prontopaga-api/workspace/prontopaga-docs/request/34607190-1927be3f-6bfc-4588-b934-51fd81cffeec?action=share&source=copy-link&creator=45976681" target="_blank">
  <img src="https://run.pstmn.io/button.svg" alt="Run in Postman" style="width: 160px;">
</a></p>

</body>
</html>
`}</HTMLBlock>

***

Con este endpoint podrás hacer un retiro instantáneo desde el comercio a una wallet.

> 📘 Lista de wallets
>
> Para conocer la lista de wallets disponibles para el número de teléfono celular del beneficiario, consulta primero [este endpoint](https://docs.prontopaga.com/reference/wallets-list).

***

## Lista completa de wallets

Estas son las wallets disponibles en Perú para hacer payouts con ProntoPaga.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Marca</b></th>
      <th><b>Valor</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Banco Falabella</td><td>falabella</td></tr>
    <tr><td>Wayki Caja Cusco</td><td>cajaCusco</td></tr>
    <tr><td>Banco Nación</td><td>nacion</td></tr>
    <tr><td>Mibanco</td><td>mibanco</td></tr>
    <tr><td>Tarjeta oh</td><td>oh</td></tr>
    <tr><td>Banco GNB</td><td>gnb</td></tr>
    <tr><td>BanBif</td><td>banbif</td></tr>
    <tr><td>Caja Lima</td><td>cajaLima</td></tr>
    <tr><td>Compartamos Financiera</td><td>compartamos</td></tr>
    <tr><td>Caja Huancayo</td><td>cajaHuancayo</td></tr>
    <tr><td>Caja Piura</td><td>cajaPiura</td></tr>
    <tr><td>Dale</td><td>dale</td></tr>
    <tr><td>Financiera Confianza</td><td>confianza</td></tr>
    <tr><td>Bancom</td><td>comercio</td></tr>
    <tr><td>Ripley</td><td>ripley</td></tr>
    <tr><td>Santander</td><td>santander</td></tr>
    <tr><td>Banco Pichincha</td><td>pichincha</td></tr>
    <tr><td>Banco de Crédito del Perú (BCP)</td><td>bcp</td></tr>
    <tr><td>Financiera Efectiva</td><td>efectiva</td></tr>
    <tr><td>Caja Ica</td><td>cajaIca</td></tr>
    <tr><td>Caja Trujillo</td><td>cajaTrujillo</td></tr>
    <tr><td>Interbank</td><td>interbank</td></tr>
    <tr><td>Luqea</td><td>luqea</td></tr>
    <tr><td>Caja Sullana</td><td>cajaSullana</td></tr>
    <tr><td>Prexpe</td><td>prexpe</td></tr>
    <tr><td>Yape</td><td>yape</td></tr>
    <tr><td>Plin</td><td>plin</td></tr>
    <tr><td>Bim</td><td>bim</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

***

<NmeroDeCaracteres />

***
