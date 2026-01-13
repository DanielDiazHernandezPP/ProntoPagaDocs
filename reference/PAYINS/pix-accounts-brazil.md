---
title: Consultar cuentas - Brasil
api:
  file: prontopaga-api.json
  operationId: get_paymentpix-paymentaccounts?taxId={taxId}
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  title: Consultar cuentas en Brasil | ProntoPaga Docs
  description: >-
    Retrieve registered Pix accounts in Brazil using the account holder’s tax
    identification number (CPF or CNPJ). This endpoint enables merchants to
    securely validate and list available Pix accounts.
  image: >-
    https://files.readme.io/ee167b820578160de99dc9ac03bd45c55280e1fa0bc6169e487c823685667ca2-Captura_de_pantalla_2025-09-08_a_las_4.24.49_p._m..png
  keywords:
    - pix accounts brazil
    - consult pix accounts
    - pix cpf cnpj
    - brazil pix api
    - prontopaga pix
    - taxid pix brazil
    - consultar cuentas pix brasil
  robots: index
---
Prueba este endpoint directamente en Postman haciendo clic en el siguiente botón

<HTMLBlock>{`
<!DOCTYPE html>
<html>
<body>

<p><a href="https://www.postman.com/prontopaga-api/workspace/prontopaga-docs/request/34607190-23977bd5-db16-473e-8bd4-e5a4800e28d9?action=share&source=copy-link&creator=45976681" target="_blank">
  <img src="https://run.pstmn.io/button.svg" alt="Run in Postman" style="width: 160px;">
</a></p>

</body>
</html>
`}</HTMLBlock>

***

_Endpoint_ que recupera las cuentas Pix asociadas al CPF proporcionado. Se debe enviar el identificador del `taxId` en la ruta.