---
title: Lista de afiliaciones
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: affiliations-list
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Endpoint para obtener una lista con las afiliaciones (ya sea de tipo One Click Payment o de Recurrencias) activas para cierto cliente, según su número de documento.

Toma en cuenta que este endpoint solo devolverá como respuesta las afiliaciones con estado `ACCEPTED`, ya que son las que están activas y con las cuales el cliente puede pagar.

> 🚧 Número de documento
> 
> Para que la consulta sea exitosa, debe enviarse el mismo número de documento que el cliente utilizó para realizar la afiliación.