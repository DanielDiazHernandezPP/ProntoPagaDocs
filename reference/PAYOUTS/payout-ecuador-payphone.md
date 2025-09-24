---
title: Crear un nuevo retiro - Ecuador Payphone
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: payout-ecuador-payphone
deprecated: false
hidden: false
metadata:
  title: Crear un nuevo retiro - Ecuador Payphone | ProntoPaga Docs
  description: >-
    This endpoint is used to create a new payout in Ecuador through Payphone
    using the ProntoPaga API. This guide covers required parameters, the use of
    bank code, and webhook confirmation.   
  image: >-
    https://files.readme.io/7763cb4f35f503a463dfcd76844a1835e8970997fcdbe6211ca99a2b2d4d2797-Prontopaga_logotipo.png
  keywords:
    - create payout API Ecuador
    - ProntoPaga payout Ecuador
    - ProntoPaga Ecuador withdrawal
    - bank transfer Ecuador
    - crear retiro ProntoPaga
    - endpoint retiro Ecuador
    - Payphone Ecuador
  robots: index
next:
  description: ''
---
Prueba este endpoint directamente en Postman haciendo clic en el siguiente botón:

<HTMLBlock>{`
<!DOCTYPE html>
<html>
<body>

<p><a href="https://www.postman.com/prontopaga-api/workspace/prontopaga-docs/request/34607190-40b1560c-cb2a-45f3-a180-74954e1c75e3?action=share&source=copy-link&creator=45976681" target="_blank">
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

## Estados del retiro en Payphone

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Estado</b></th>
      <th><b>Descripción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Success</td><td>Solicitud aprobada</td></tr>
    <tr><td>Canceled</td><td>Solicitud rechazada. Conoce los <a href="https://docs.prontopaga.com/docs/payouts-rejections#/">tipos de retiros cancelados</a> </td></tr>
  </tbody>
</table>
`}</HTMLBlock>

> 📘 Estados
>
> Payphone solo utiliza el estado **success** y **canceled** ya que son pagos instantáneos.

***

<NmeroDeCaracteres />

***
