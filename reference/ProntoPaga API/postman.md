---
title: Colección de Postman
excerpt: >-
  Descubre cómo utilizar nuestra colección de Postman para facilitar tus
  pruebas.
deprecated: false
hidden: false
metadata:
  title: Colección de Postman | ProntoPaga Docs
  description: >-
    Access and test all ProntoPaga API endpoints easily using our Postman
    collection. This guide explains how to authenticate requests with generic or
    personal sandbox credentials, generate secure signatures with pre-request
    scripts, and configure webhooks. 
  image: >-
    https://files.readme.io/60017209c9dc3f3c289e33fcf7c4cbb62f13e0eef91288e5b7ba07819cfcb854-Prontopaga_logotipo.png
  keywords:
    - endpoints postman prontopaga
    - Postman Prontopaga
    - Prontopaga API testing
    - sandbox API credentials
    - bearer token Prontopaga
    - secret key Prontopaga
    - Prontopaga webhook
    - test Prontopaga API Prontopaga
  robots: index
next:
  description: ''
---
Si prefieres realizar tus pruebas desde Postman, tenemos a tu disposición una colección con todos nuestros endpoints.

➡️ <a href="https://www.postman.com/prontopaga-api/prontopaga-docs/collection/24iz2pb/prontopaga-api?action=share&creator=34607190" target="_blank">Accede a la colección aquí</a>

## ¿Cómo utilizar la colección?

A continuación se detallan los pasos para utilizar la colección de Postman, ya sea que cuentes o no con tus propias credenciales de prueba.

### Con credenciales de prueba genéricas

Si no cuentas con un Bearer Token y secretKey de sandbox, sigue estos pasos para probar nuestra API en Postman:

1. Busca el endpoint del servicio que quieres probar.
2. Añade este Bearer Token en la pestaña **Autorización**: `caff446438560a48438e0b49e5a6a0870ac5624b9f9ce1577858595d1a8ba1ec`
3. En los endpoints que requieren una firma, usa el script precargado en la ruta **Scripts > Pre-request**, el cual creará automáticamente la firma. Además, ya incluye la secretKey de prueba (que en este caso, es `01JNH2SBC5Z2CM1PWQXM2C1XK9`)
4. Envía la petición.

### Con tus propias credenciales de prueba

Si ya has recibido tu Bearer Token y secretKey de sandbox, sigue estos pasos para probar nuestra API en Postman:

1. Busca el endpoint del servicio que quieres probar.
2. Añade tu Bearer Token en la pestaña **Authorization**.
3. En los endpoints que requieren una firma, usa el script precargado en la ruta **Scripts > Pre-request**, el cual creará automáticamente la firma. Cambia el valor de `let secretKey = '';` por tu secretKey de sandbox.
4. Envía la solicitud.

## Webhooks

Configurar un webhook para tus transacciones te ayudará a conocer el estado de los pagos y retiros. Estos callbacks te notificarán cuando se produzca un cambio de estado en una determinada transacción. Conoce cómo crear uno en [este artículo](https://docs.prontopaga.com/docs/webhooks).