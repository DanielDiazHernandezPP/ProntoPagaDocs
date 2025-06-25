---
title: Lista de wallets - Perú
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: wallets-list
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    Endpoint to obtain the available wallets. You can get the total list or the
    wallets associated to a certain phone number.
  keywords:
    - wallets list
    - ' list of wallets'
    - ' peru wallets'
    - ' wallets prontopaga'
    - ' available wallets'
    - ' wallets per phone'
    - ' wallets per phone number'
    - ' wallets per number'
    - ' prontopaga'
    - ' api'
    - ' endpoint'
  robots: index
next:
  description: ''
---
Endpoint para obtener las wallets disponibles.

> 🚧 Número telefónico
> 
> El envío del `{teléfono}` en la URL es opcional. Si se manda, recibirás como respuesta las wallets asociadas a ese número telefónico. Si no se manda, recibirás una lista de todas las wallets disponibles.