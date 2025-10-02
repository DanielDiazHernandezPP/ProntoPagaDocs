---
title: Procesa un pago - Perú Botón Yape (sin iFrame)
api:
  file: prontopaga-api.json
  operationId: get_new-endpoint
deprecated: false
hidden: true
metadata:
  title: Procesa un pago - Perú Botón Yape (sin iFrame) | ProntoPaga Docs
  description: >-
    API endpoint for integrating Yape payment button without using an iFrame,
    allowing merchants in Peru to fully control the checkout appearance. It
    provides a link to view possible rejection types and their details.
  image: >-
    https://files.readme.io/ac3f5c079029bfd04bca071bc0c334dde52d4efca5e1b7c567187a6b5bf53331-Prontopaga_logotipo.png
  keywords:
    - 'Keywords: api Yape'
    - boton Yape api
    - Yape api Prontopaga
    - yap Yape e Prontopaga
    - Prontopaga api
    - integra Yape
    - integrate Yape
    - endpoint Yape
  robots: index
---
Prueba este endpoint directamente en Postman haciendo clic en el siguiente botón:

<HTMLBlock>{`
<!DOCTYPE html>
<html>
<body>

<p><a href="https://www.postman.com/prontopaga-api/workspace/prontopaga-docs/request/34607190-b0667c18-1fc8-44a1-8afe-c05d24bd112f?action=share&source=copy-link&creator=45976681" target="_blank">
  <img src="https://run.pstmn.io/button.svg" alt="Run in Postman" style="width: 160px;">
</a></p>

</body>
</html>
`}</HTMLBlock>

***

Endpoint para procesar pagos con Botón Yape vía API (sin iFrame). Con este servicio, ProntoPaga no generará el front-end, por lo que tu comercio tendrá el manejo total de la apariencia del checkout durante un pago con Yape en Perú.

Para usar este servicio, necesitarás crear el pago usando el endpoint de [Crear un nuevo pago](https://docs.prontopaga.com/reference/create-payment), tomar el `uid` recibido en la respuesta y colocarlo en el path parameter de este endpoint.

> 📘 Tipos de rechazo y datos de prueba
>
> Consulta los posibles tipos de rechazo para este método, su código y detalle en [esta página](https://docs.prontopaga.com/docs/payins-rejections#yape---primarios). Además, consulta los datos de prueba con diferentes escenarios [aquí.](https://docs.prontopaga.com/docs/test-data-cards-peru#bot%C3%B3n-yape)

***