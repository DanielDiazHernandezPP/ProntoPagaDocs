---
title: Crear un nuevo retiro en efectivo - Ecuador
excerpt: ''
api:
  file: prontopaga-api.json
  operationId: cash-payout
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    Endpoint to create a new cash payout request. To create a payout, the
    request must be constructed with the following parameters.
  keywords:
    - cash payout
    - ' payout with cash'
    - ' prontopaga'
    - ' api'
    - ' endpoint'
    - ' payouts'
    - ' request'
    - ' body params'
    - ' examples'
    - ' response'
  robots: index
next:
  description: ''
---
Endpoint para crear una nueva solicitud de retiro en efectivo. 

> 📘 Webhook
>
> Una vez que el usuario haya completado el proceso de retiro, ProntoPaga devolverá los datos a la URL que hayas especificado en la `confirmationURL`.

## Plataformas

| Parámetro platform | Marca                    |
| :----------------- | :----------------------- |
| broadnet           | Ponle más                |
| bemovil            | Bemovil                  |
| redactiva          | Red Activa/Western Union |