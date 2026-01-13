---
title: Configura el plugin de VTEX
excerpt: Conoce el paso a paso de cómo configurar el plugin de VTEX para tu comercio.
deprecated: false
hidden: false
metadata:
  title: Configura el plugin de VTEX | ProntoPaga
  description: >-
    Learn how to install, configure, and test the ProntoPaga payment plugin for
    . VTEX. This guide walks you through setup requirements, plugin
    installation, API credential configuration, supported currencies and payment
    methods, and how to troubleshoot common issues.  
  image: >-
    https://files.readme.io/3e0e613b238d626c9e130c141eb56d50010ae179085d622f96c005aaac6fc000-Prontopaga_logotipo.png
  keywords:
    - ProntoPaga VTEX plugin
    - install ProntoPaga VTEX
    - VTEX Peru payments
    - VTEX ProntoPaga guide
  robots: index
next:
  description: ''
---
VTEX es una plataforma de comercio digital que permite a empresas crear y gestionar tiendas en línea de forma escalable y flexible. Un buen plugin de pagos puede optimizar la experiencia de compra, reduciendo fricción y mejorando la conversión. Esto, junto con garantizar transacciones seguras y rápidas, es el objetivo del plugin que desarrollamos en ProntoPaga.

Esta guía te llevará paso a paso a través del proceso de instalación, configuración y prueba del plugin de pagos ProntoPaga en la plataforma de VTEX.

***

<br />

## Requisitos

Antes de comenzar con la instalación, asegúrate de contar con lo siguiente:

* Acceso con permisos de administrador a la cuenta VTEX en la que instalarás el plugin.
* Tener configurado VTEX CLI en tu entorno local.
* Ser VTEX Partner con acceso al VTEX Admin.
* Tener configurado el entorno con Node.js y Yarn (opcional, pero recomendado).
* Tener instalado Git.

***

<br />

## Instalación

Para instalar el plugin de pagos ProntoPaga en VTEX, sigue estas instrucciones:

1. Abre la terminal e inicia sesión en VTEX CLI, ejecutando el comando: `vtex login nombre_de_cuenta`

<Image align="center" border={false} src="https://files.readme.io/fda43071aadb95b9238dc3ecf6edf454c9a5c8e76bf22730258736da09f5e4a6-1_vtex.png" />

2. El comando te redirigirá al _login_ de VTEX en el navegador. Inicia sesión con tus datos

<Image align="center" border={false} width="320px" src="https://files.readme.io/4eb449d06eff1282d1426f9614aa5bd980935b8116de2cc99a5a878bf76dcbdc-2vtex.png" />

3. Una vez iniciada la sesión en el navegador, la terminal se actualizará

<Image align="center" border={false} src="https://files.readme.io/b9cd29f262c0279d21aeb46e19128c170caeac5dc3020314d4a077e8f632a972-3vtex.png" />

4. Verifica el workspace, ejecutando el comando: `vtex workspace list`

<Image align="center" border={false} src="https://files.readme.io/7ad5e5637d8f6566d95229921a3be33ec23540f651cca9a4769ecab32b84703e-4vtex.png" />

5. Elige usar el workspace master ejecutando el comando: `vtex use master`

> 👍 Recomendación
>
> Te sugerimos primero hacer pruebas en un workspace de desarrollo (`vtex use dev`), y luego promocionar los cambios a master.

6. Instala ProntoPaga en tu cuenta VTEX, ejecutando el comando: `vtex install knownonline.prontopaga-paymentapp@1.3.0`

<Image align="center" border={false} src="https://files.readme.io/b0ed4bcc26c97cbb80e2304be9f73add3dda99c2a03b23548fa4996667db3e40-5vtex.png" />

> 🚧 Versión del plugin
>
> Verifica la versión más reciente del plugin en el [repositorio oficial ](https://ci.prontopaga.com/users/sign_in)o bien, en VTEX App Store, en la sección de: **Añadir nueva condición de pago para VTEX.**

7. ¡Listo! ProntoPaga habrá quedado instalado desde la terminal.

<Image align="center" border={false} width="400px" src="https://files.readme.io/f285ea53557966437a16198152986d56e63a7e05cba6608b758eee49efa7419e-6_vtex.png" />

***

<br />

## Verificación de la instalación y configuración

Una vez instalado el plugin desde la terminal, verifica la instalación en el Admin de VTEX y termina la configuración, siguiendo estos pasos:

1. Dirígete a **Pagos > Configuración de medios de pago**
2. Busca “ProntoPaga” en la lista de medios de pago
3. Revisa que esté activo, y añade tus credenciales API en esta sección:
   1. Token de autenticación (Bearer Token)
   2. Secret Key

***

<br />

## Prueba tu integración

Para asegurar el correcto funcionamiento de ProntoPaga en tu cuenta de VTEX, realiza una prueba de pago siguiendo estos pasos:

1. Agrega un producto al carrito

2. Haz clic en el botón **Finalizar compra**, para proceder al _checkout_

<Image align="center" border={false} width="420px" src="https://files.readme.io/7183f974b5492d342350e9c14c60710de8fe91556d1db998b69180c647ea47ab-7vtex.png" />

3. Completa los datos **Identificación** y **Envío**. En **Pago**, elige ProntoPaga

<Image align="center" border={false} width="420px" src="https://files.readme.io/14fafdf1339d6347f35c26e91cf4067b26b109298e89f7a43abe771d47fde016-8vtex.png" />

4. Haz clic en el botón **Comprar ahora**
5. Se abrirá la experiencia de ProntoPaga, en donde podrás elegir un método de pago y comprobar que el pago se realice correctamente

<Image align="center" border={false} width="370px" src="https://files.readme.io/827ddff4ab33e92dc048f358d4a899bd27b2a6572cf93fa546502e33fd93dfb1-9vtex.png" />

> 👍 Set de pruebas
>
> Te sugerimos hacer varias pruebas (exitosas y no exitosas) por cada método de pago, para confirmar el correcto funcionamiento de la pasarela.

6. Verifica que la redirección, validación y respuesta del pago funcionen adecuadamente

***

<br />

## Solución de problemas comunes

A continuación, se presenta una tabla con los problemas más comunes asociados a esta instalación, así como las soluciones sugeridas.

| Problema                                  | Solución sugerida                                                   |
| :---------------------------------------- | :------------------------------------------------------------------ |
| El plugin no aparece en el Admin          | Verifica si se instaló en el workspace correcto, y si fue publicado |
| Error de redirección al pagar             | Revisa las credenciales API configuradas                            |
| No aparece ProntoPaga como opción de pago | Asegúrate de que el plugin esté activo y configurado                |

<br />

### Ayuda con un pedido

En caso de requerir ayuda con un pedido específico, por favor comparte con nosotros el número de referencia del pedido.

***

<br />

## Recursos adicionales

Estos son algunos enlaces que podrían ser de utilidad durante este proceso:

* Documentación oficial de VTEX: [https://developers.vtex.com/](https://developers.vtex.com/)
* Repositorio de ProntoPaga: [https://ci.prontopaga.com/users/sign_in](https://ci.prontopaga.com/users/sign_in)
* Soporte de VTEX (en caso de errores persistentes en la plataforma):  [support@prontopaga.com](mailto:support@prontopaga.com)
* Soporte de ProntoPaga (en caso de errores persistentes con la pasarela): [support@prontopaga.com](mailto:support@prontopaga.com)

<br />
