---
title: Crear un nuevo retiro - Ecuador Ponle más
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: payout-ecuador-ponle-mas
deprecated: false
hidden: false
metadata:
  title: Crear un nuevo retiro - Ecuador Ponle más | ProntoPaga Docs
  description: >-
    This endpoint is used to create a new payout in Ecuador through Ponle más
    using the ProntoPaga API. This guide covers required parameters, the use of
    bank code, and webhook confirmation.
  image: >-
    https://files.readme.io/50d1ddb3ff59698104655999512ab620e7ff726f3d3ff8e75d8e0d665dcce82f-Prontopaga_logotipo.png
  keywords:
    - create payout API Ecuador
    - ProntoPaga payout Ecuador
    - bank transfer Ecuador
    - crear retiro ProntoPaga
    - endpoint retiro Ecuador
    - Ponle más Ecuador integración
  robots: index
next:
  description: ''
---
Prueba este endpoint directamente en Postman haciendo clic en el siguiente botón:

<HTMLBlock>{`
<!DOCTYPE html>
<html>
<body>

<p><a href="https://www.postman.com/prontopaga-api/workspace/prontopaga-docs/request/34607190-f5d9fb13-09aa-40ab-9c19-8a9b4158411a?action=share&source=copy-link&creator=45976681" target="_blank">
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

### Logos de los métodos de retiro

Antes de finalizar tu integración, recuerda agregar los logotipos de los diferentes métodos de ProntoPaga a tu front-end. Puedes [descargarlos aquí.](https://prontopagalatam-my.sharepoint.com/:f:/g/personal/tahbet_reategui_prontopaga_com/EtPhXrMz3TxAtA11de5jVZEB3yowkpS1i2v6lm_eMKkB7g?e=KXcZX5)

***

<NmeroDeCaracteres />

***
