---
title: Crear una nueva biometría
api:
  file: prontopaga-api.json
  operationId: get_v2biometricnew
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  robots: index
---
Prueba este endpoint directamente en Postman haciendo clic en el siguiente botón:

<HTMLBlock>{`
<!DOCTYPE html>
<html>
<body>

<p><a href="https://www.postman.com/prontopaga-api/workspace/prontopaga-docs/request/34607190-a52ca4cf-0814-448e-8a2f-6a1bcf692f4e?action=share&creator=45976681&ctx=documentation" target="_blank">
  <img src="https://run.pstmn.io/button.svg" alt="Run in Postman" style="width: 160px;">
</a></p>

</body>
</html>
`}</HTMLBlock>

***

Con este endpoint podrás realizar una nueva solicitud de verificación biométrica. La respuesta de ProntoPaga a la solicitud de verificaición biométrica es el UID de la transacción y la URL a la que debe redirigir al usuario.