---
title: Crear un nuevo retiro - Ecuador Bemovil
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: payout-ecuador-bemovil
deprecated: false
hidden: false
metadata:
  title: Crear un nuevo retiro - Ecuador Bemovil | ProntoPaga Docs
  description: >-
    This endpoint is used to create a new payout in Ecuador through Bemovil
    using the ProntoPaga API. This guide covers required parameters, the use of
    bank code, and webhook confirmation.   
  image: >-
    https://files.readme.io/edb211052843808b0f51395a675a8f8542047687bac1131515f0ffa1f279e9e0-Prontopaga_logotipo.png
  keywords:
    - create payout API Ecuador
    - ProntoPaga payout Ecuador
    - bank transfer Ecuador
    - crear retiro ProntoPaga
    - endpoint retiro Ecuador
    - Bemovil Ecuador integración
  robots: index
next:
  description: ''
---
Prueba este endpoint directamente en Postman haciendo clic en el siguiente botón:

<HTMLBlock>{`
<!DOCTYPE html>
<html>
<body>

<p><a href="https://www.postman.com/prontopaga-api/workspace/prontopaga-docs/request/34607190-6ccfbb52-c510-49e6-8d49-b238afb6deaa?action=share&source=copy-link&creator=45976681" target="_blank">
  <img src="https://run.pstmn.io/button.svg" alt="Run in Postman" style="width: 160px;">
</a></p>

</body>
</html>
`}</HTMLBlock>

***

Endpoint para crear una nuevo retiro. Para crear una nueva solicitud de retiro, la solicitud debe construirse con los siguientes parámetros.

> 📘 Webhook
>
> Una vez que el usuario haya completado el proceso de retiro, ProntoPaga devolverá los datos a la URL que hayas especificado en la `confirmationURL`.

***

<br />

<NmeroDeCaracteres />

***

### Logos de los métodos de pago

Antes de finalizar tu integración, recuerda agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu front-end. Puedes [descargarlos aquí.](https://prontopagalatam-my.sharepoint.com/:u:/g/personal/tahbet_reategui_prontopaga_com/EWC1ijJHq5JKnjpIH9qH0ncBOMEiK2wrNPdxkTdVmyZ7Kg?e=SCuGY4\&download=1)
