---
title: Crear un nuevo retiro - Ecuador Red Activa/Western Union
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: payout-ecuador-redactiva
deprecated: false
hidden: false
metadata:
  title: Crear un nuevo retiro - Ecuador Red Activa/Western Union | ProntoPaga Docs
  description: >-
    This endpoint is used to create a new payout in Ecuador through Red
    Activa/Western Union using the ProntoPaga API. This guide covers required
    parameters, the use of bank code, and webhook confirmation.
  image: >-
    https://files.readme.io/c96314e80fc943d953ebf4adcf880cdb401a8445319d0f407187620f44eef195-Prontopaga_logotipo.png
  keywords:
    - create payout API Ecuador
    - ProntoPaga payout Ecuador
    - bank transfer Ecuador
    - crear retiro ProntoPaga
    - endpoint retiro Ecuador
    - Red Activa Ecuador integración
    - Western Union Ecuador Prontopaga
  robots: index
next:
  description: ''
---
Prueba este endpoint directamente en Postman haciendo clic en el siguiente botón:

<HTMLBlock>{`
<!DOCTYPE html>
<html>
<body>

<p><a href="https://www.postman.com/prontopaga-api/workspace/prontopaga-docs/request/34607190-26291c30-d7fb-4e1d-adda-166a8a14aca9?action=share&source=copy-link&creator=45976681" target="_blank">
  <img src="https://run.pstmn.io/button.svg" alt="Run in Postman" style="width: 160px;">
</a></p>

</body>
</html>
`}</HTMLBlock>

***

### Logos de los métodos de retiro

Antes de finalizar tu integración, recuerda agregar los logotipos de los diferentes métodos de ProntoPaga a tu front-end. Puedes [descargarlos aquí.](https://prontopagalatam-my.sharepoint.com/:u:/g/personal/tahbet_reategui_prontopaga_com/EWC1ijJHq5JKnjpIH9qH0ncBOMEiK2wrNPdxkTdVmyZ7Kg?e=SCuGY4\&download=1)

***

Endpoint para crear una nuevo retiro. Para crear una nueva solicitud de retiro, la solicitud debe construirse con los siguientes parámetros.

> 📘 Webhook
>
> Una vez que el usuario haya completado el proceso de retiro, ProntoPaga devolverá los datos a la URL que hayas especificado en la `confirmationURL`.

***

<NmeroDeCaracteres />

<br />
