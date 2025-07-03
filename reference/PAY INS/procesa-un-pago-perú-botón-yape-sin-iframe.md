---
title: Procesa un pago - Perú Botón Yape (sin iFrame)
api:
  file: prontopaga-api.json
  operationId: get_new-endpoint
deprecated: false
hidden: true
metadata:
  robots: index
---
Endpoint para procesar pagos con Botón Yape vía API (sin iFrame). Con este servicio, ProntoPaga no generará el front-end, por lo que tu comercio tendrá el manejo total de la apariencia del checkout durante un pago con Yape en Perú.

Para usar este servicio, necesitarás crear el pago usando el endpoint de [Crear un nuevo pago](https://docs.prontopaga.com/reference/create-payment), tomar el `uid` recibido en la respuesta y colocarlo en el path parameter de este endpoint.

<Callout icon="📘">
  Tipos de rechazo y datos de prueba

  Consulta los posibles tipos de rechazo para este método, su código y detalle en [esta página](https://docs.prontopaga.com/docs/payins-rejections#yape---primarios). Además, consulta los datos de prueba con diferentes escenarios [aquí.](https://docs.prontopaga.com/docs/test-data-cards-peru#bot%C3%B3n-yape)
</Callout>