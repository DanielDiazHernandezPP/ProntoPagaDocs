---
title: Environments
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Environments | ProntoPaga Docs
  description: >-
    The ProntoPaga API has two environments: sandbox and production; the sandbox
    uses simulated data and has a certain URL, while the production environment
    requires certification and uses a different URL.
  image: >-
    https://files.readme.io/ca34da4fc3a6b679e3463e4e855c9aed48d9e08b346520555505c6a5b4621369-Prontopaga_Logotipo.JPG
  keywords:
    - environment
    - sandbox
    - production
    - prontopaga
    - api
    - ambientes
    - producción
  robots: index
next:
  description: ''
---
La API de ProntoPaga cuenta con dos environments:

* El environment de pruebas (sandbox)
* El environment de producción

***

## Pruebas (sandbox)

Como primer paso, nosotros crearemos y te proporcionaremos tu Bearer Token y secretKey en el environment de pruebas, para que puedas hacer tu integración y realizar las pruebas que desees en sandbox. Realizar pruebas en este environment no afectará los datos reales de tu comercio, ya que se utilizan datos simulados.

La URL base de este environment es:

```
https://sandbox.prontopaga.com/api
```

<br />

Las IPs del environment de sandbox son:

```
54.236.195.158
44.195.64.16
```

***

## Producción

Una vez que tu comercio esté listo para pasar a producción con los datos reales y en vivo, la administración de ProntoPaga deberá certificarte. Después de formalizar la certificación, se te proporcionarán un Bearer Token y secretKey distintos a los que usaste en sandbox.

La URL base de este environment es:

```
https://prontopaga.com/api
```

<br />

Las IPs del environment de producción son:

```
54.207.141.85
44.219.63.240
52.206.25.128
104.18.21.166
```