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

<p><a href="https://www.postman.com/prontopaga-api/workspace/prontopaga-docs/request/34607190-0d6476c8-9ce4-4eb0-93ff-38b609e8e8a8?action=share&source=copy-link&creator=45976681" target="_blank">
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

| Marca                           | Valor        |
| :------------------------------ | :----------- |
| Banco Falabella                 | falabella    |
| Wayki Caja Cusco                | cajaCusco    |
| Banco Nación                    | nacion       |
| Mibanco                         | mibanco      |
| Tarjeta oh                      | oh           |
| Banco GNB                       | gnb          |
| BanBif                          | banbif       |
| Caja Lima                       | cajaLima     |
| Compartamos Financiera          | compartamos  |
| Caja Huancayo                   | cajaHuancayo |
| Caja Piura                      | cajaPiura    |
| Dale                            | dale         |
| Financiera Confianza            | confianza    |
| Bancom                          | comercio     |
| Ripley                          | ripley       |
| Santander                       | santander    |
| Banco Pichincha                 | pichincha    |
| Banco de Crédito del Perú (BCP) | bcp          |
| Financiera Efectiva             | efectiva     |
| Caja Ica                        | cajaIca      |
| Caja Trujillo                   | cajaTrujillo |
| Interbank                       | interbank    |
| Luqea                           | luqea        |
| Caja Sullana                    | cajaSullana  |
| Prexpe                          | prexpe       |
| Yape                            | yape         |
| Plin                            | plin         |
| Bim                             | bim          |

***

<NmeroDeCaracteres />

***
