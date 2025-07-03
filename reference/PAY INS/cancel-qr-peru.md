---
title: Cancelar un pago con QR - Perú
api:
  file: prontopaga-api.json
  operationId: post_peqrcancel{uid}
deprecated: false
hidden: false
metadata:
  description: >-
    This page describes an endpoint that allows to cancel a QR payment in Peru
    if it was not made immediately, preventing a customer from using the QR
    image to try to pay later.
  keywords:
    - cancel a qr
    - cancel a payment
    - qr peru
    - prontopaga
    - api
  robots: index
---
Con este endpoint podrás cancelar un pago con QR en Perú (cuando no se realizó al momento). De este modo, se evitará que un cliente guarde la imagen del QR e intente pagar tiempo después.