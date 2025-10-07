---
title: ¿Cómo usar nuestra documentación?
excerpt: Descubre cómo utilizar nuestra documentación y explora sus secciones.
deprecated: false
hidden: false
metadata:
  title: Cómo usar nuestra documentación | ProntoPaga Docs
  description: >-
    The ProntoPaga Quick Guide describes the structure of its technical
    documentation, which includes tabs for Integration Guides, Recipes, API
    Reference, and Changelog, providing details on how to use each section to
    facilitate integration and use of the API.
  image: >-
    https://files.readme.io/7de7c9c0d05036c8958655f509bfbcc9cc810b108f142d07da25acb93589f8bd-Prontopaga_logotipo.png
  keywords:
    - api use
    - quick guide Prontopaga
    - documentation Prontopaga
    - acceder a la documentación de Prontopaga
    - cómo usar la documentación de Prontopaga
  robots: index
next:
  description: ''
---
Esta es una **Guía Rápida** para conocer la plataforma y acomodo de la Documentación Técnica de ProntoPaga. Nuestra documentación cuenta con cuatro pestañas principales en el menú superior:

<Image align="center" width="500px" src="https://files.readme.io/5c7c84352166fdf0df87772560bb537f69eda81821f14c6b0b002d9df7ae66f2-Captura_de_pantalla_2025-03-04_a_las_8.47.39_p.m..png" />

A continuación, te mostramos qué puedes encontrar en cada una, así como consejos para sacar lo mejor de esta documentación.

## Guides

La pestaña de **Guides** contiene principalmente todas las Guías de integración, ordenadas por país y métodos. Además, también contiene información general que puede ser de utilidad para tu integración. En la siguiente imagen puedes observar sus características:

<Image align="center" src="https://files.readme.io/49a9a08bc7807a835a59d53ed5ada771565057e65069c9ba494912425ca2e6ab-03.png" />

Dentro de cada Guía de integración podrás encontrar información detallada, como:

* Introducción al método
* Notas o especificaciones importantes
* Ejemplos de body request para la solicitud
* Ejemplos de posibles respuestas
* Ejemplos de webhooks

## API Reference

La pestaña de **API Reference** es la más visitada de nuestro sitio. Aquí encontrarás todos los endpoints de ProntoPaga, ordenados por método. A continuación te mostramos los componentes generales:

<Image align="center" src="https://files.readme.io/cea86d1a25cb96889740a8bd06a1139c9efbe6771459c2deebbf1067a8f67834-01.png" />

Además, cada endpoint cuenta con ejemplos de body request y respuestas, así como un enviroment listo para realizar pruebas de la API en vivo:

<Image align="center" src="https://files.readme.io/e162b75d25a17ec8477a9c625f67292bdedc5f227551064367e727904448a12f-02.png" />

Recuerda que para hacer uso de la caja de pruebas en vivo, deberás contar con tu **Bearer Token y secretKey de Sandbox** (proporcionados por ProntoPaga), y seguir estos pasos:

1. Agregar tu Bearer Token en la sección **CREDENTIALS**.
2. Modificar los valores de los parámetros del body (en caso de ser necesario).
3. [Crear la firma de la transacción](https://docs.prontopaga.com/docs/sign-transactions) con tu secretKey y agregarla al body de la transacción (en caso de ser necesario).
4. Hacer clic en el botón **Try it!**. Verás la respuesta debajo, en la sección **RESPONSE**.

### Colección de Postman

Si prefieres realizar tus pruebas desde Postman, tenemos a tu disposición una colección que puedes copiar en tu espacio de trabajo. Esta colección cuenta con un script para automatizar la creación de la firma.

Conoce toda la información necesaria para utilizar nuestra colección de Postman en [esta página](https://docs.prontopaga.com/reference/postman).

### Environments

Para conocer más sobre los enviroments de ProntoPaga, así como las URL e IP de éstos, te sugerimos revisar [esta página](https://docs.prontopaga.com/docs/ambientes).

## Changelog

La pestaña de **Changelog** contiene el detalle del control de cambios de la API. Podrás ver los cambios realizados en cada nueva versión.