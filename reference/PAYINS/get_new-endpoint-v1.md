---
title: Cancelar un pago con QR en Argentina
api:
  file: prontopaga-api.json
  operationId: get_new-endpoint-v1
hidden: true
---
Prueba este endpoint directamente en Postman haciendo clic en el siguiente botón

<HTMLBlock>{`
<!DOCTYPE html>
<html>
<body>

<p><a href="https://www.postman.com/prontopaga-api/workspace/prontopaga-docs/request/34607190-d2d5b910-f670-4750-9292-4bbad03fc7b4?action=share&source=copy-link&creator=45976681" target="_blank">
  <img src="https://run.pstmn.io/button.svg" alt="Run in Postman" style="width: 160px;">
</a></p>

</body>
</html>
`}</HTMLBlock>

***

<br />

Busca el pago por uid.
Si no existe → lanza 404.
Si el pago no está finalizado (SUCCESS/REJECTED):
Llama al servicio newPayService->cancelQRPayment().
Si el servicio falla, usa ['status' => 'canceled'].
Ejecuta validación validateTransaction.
Registra cualquier error en logs.
Redirige a la ruta payment_step_3.
Respuestas
RedirectResponse a payment_step_3.
Errores posibles
404 si no encuentra el pago.
Errores en cancelación → logueados.
Excepciones del servicio de validación.

<br />
