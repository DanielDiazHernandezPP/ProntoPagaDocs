---
title: Ambientes
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    The ProntoPaga API has two environments: sandbox and production; the sandbox
    uses simulated data and has a certain URL, while the production environment
    requires certification and uses a different URL.
  keywords:
    - environment
    - ' sandbox'
    - ' production'
    - ' prontopaga'
    - ' api'
  robots: index
next:
  description: ''
---
La API de ProntoPaga cuenta con dos ambientes:

* El ambiente de pruebas (sandbox)
* El ambiente de producción

## Pruebas (sandbox)

Como primer paso, nosotros te crearemos un TokenApi y un SecretKey para que puedas hacer tu integración y realizar las pruebas que desees con el ambiente de sandbox. Realizar pruebas en este ambiente no afectará los datos reales de tu comercio, ya que se utilizan datos simulados.

La URL base de este ambiente es:

```
https://sandbox.insospa.com/api/
```

## Producción

Una vez que tu comercio esté listo para pasar a producción con los datos reales y en vivo, la administración de ProntoPaga deberá certificarte. Después de formalizar la certificación, se te proporcionarán un TokenApi y SecretKey distintos a los que usaste en sandbox.

La URL base de este ambiente es:

```
https://prontopaga.com/api
```
