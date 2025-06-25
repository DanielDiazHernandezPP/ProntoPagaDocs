---
title: ¿Cómo usar nuestra documentación?
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    The ProntoPaga Quick Guide describes the structure of its Technical
    Documentation, which includes tabs for Integration Guides, Recipes, API
    Reference, and Changelog, providing details on how to use each section to
    facilitate integration and use of the API.
  keywords:
    - api use
    - ' quick guide'
    - ' prontopaga'
    - ' api'
    - ' api reference'
    - ' integration guides'
  robots: index
next:
  description: ''
---
Esta es una Guía Rápida para conocer la plataforma y acomodo de la Documentación Técnica de ProntoPaga. Nuestra documentación cuenta con cuatro pestañas principales en el menú superior:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2ae4c4886bd86180e59a47ea94417dd5e06ea32853ec7abc219cee0c3f18428a-Captura_de_pantalla_2024-11-15_a_las_11.15.36_a.m..png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "500px"
    }
  ]
}
[/block]


A continuación, te mostramos qué puedes encontrar en cada una, así como consejos para sacar lo mejor de esta documentación.

## Guides

La pestaña de **Guides** contiene principalmente todas las Guías de integración, ordenadas por país y métodos. Además, también contiene información general que puede ser de utilidad para tu integración. En la siguiente imagen puedes observar sus características: 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/49a9a08bc7807a835a59d53ed5ada771565057e65069c9ba494912425ca2e6ab-03.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


Dentro de cada Guía de integración podrás encontrar información detallada, como:

- Introducción al método 
- Notas o especificaciones importantes
- Ejemplos de body request para la solicitud
- Ejemplos de posibles respuestas
- Ejemplos de webhooks

## Recipes

En la pestaña de **Recipes** encontrarás tutoriales cortos para resolver preguntas comunes. Estas recetas están también mencionadas y linkeadas en el endpoint o guía correspondiente.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/522d1a344d52b001eb98fb89965f607ad6615a5e31e42c7fce2f4ac52bb5dd7b-04.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


## API Reference

La pestaña de **API Reference** es la más visitada de nuestro sitio. Aquí encontrarás todos los endpoints de ProntoPaga, ordenados por método. A continuación te mostramos los componentes generales:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cea86d1a25cb96889740a8bd06a1139c9efbe6771459c2deebbf1067a8f67834-01.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


Además, cada endpoint cuenta con ejemplos de body request y respuestas, así como un ambiente listo para realizar pruebas de la API en vivo:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e162b75d25a17ec8477a9c625f67292bdedc5f227551064367e727904448a12f-02.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


Recuerda que para hacer uso de la caja de pruebas en vivo, deberás contar con tu Bearer Token y SecretKey de sandbox (proporcionados por ProntoPaga), y seguir estos pasos:

1. Agregar tu Bearer Token en la sección **Credentials**
2. Modificar los valores de los parámetros del body (en caso de ser necesario)
3. [Crear la firma de la transacción](https://docs.prontopaga.com/docs/sign-transactions) con tu SecretKey y agregarla al body de la transacción (en caso de ser necesario)
4. Hacer clic en el botón **Try it!**

### Colección de Postman

Si prefieres realizar tus pruebas desde Postman, tenemos a tu disposición una colección que puedes copiar en tu espacio de trabajo. 

[Descarga la colección aquí](https://www.postman.com/prontopaga-docs/workspace/public-prontopaga/collection/34607190-ae5606cc-d470-4569-8860-fc54257e958c?action=share&creator=34607190).

## Changelog

La pestaña de **Changelog **contiene el detalle del control de cambios de la API. Podrás ver los cambios realizados en cada nueva versión.