---
title: Lista de afiliaciones
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: affiliations-list
deprecated: false
hidden: false
metadata:
  title: Lista de afiliaciones | ProntoPaga Docs
  description: >-
    This endpoint is used in Peru to obtain a list of your business's
    affiliations. 
  image: >-
    https://files.readme.io/1e6bed02cf0740d2d985a718b49722a7475026008d29a6d6027295b00092c709-Prontopaga_logotipo.png
  keywords:
    - endpoint yape
    - yape prontopaga
    - Yape on File
    - One Click Payment
    - recurrencia Yape
    - list of affiliations Yape
    - lista de afiliados Yape
  robots: index
next:
  description: ''
---
Prueba este endpoint directamente en Postman haciendo clic en el siguiente botón:

<HTMLBlock>{`
<!DOCTYPE html>
<html>
<body>

<p><a href="https://www.postman.com/prontopaga-api/workspace/prontopaga-docs/request/34607190-db936049-f3cb-4641-990f-04231a9adea9?action=share&source=copy-link&creator=45976681" target="_blank">
  <img src="https://run.pstmn.io/button.svg" alt="Run in Postman" style="width: 160px;">
</a></p>

</body>
</html>
`}</HTMLBlock>

***

Endpoint para obtener una lista con las afiliaciones (ya sea de tipo One Click Payment o de Recurrencias) activas para cierto cliente, según su número de documento.

Toma en cuenta que este endpoint solo devolverá como respuesta las afiliaciones con estado `ACCEPTED`, ya que son las que están activas y con las cuales el cliente puede pagar.

> 🚧 Número de documento
>
> Para que la consulta sea exitosa, debe enviarse el mismo número de documento que el cliente utilizó para realizar la afiliación.
