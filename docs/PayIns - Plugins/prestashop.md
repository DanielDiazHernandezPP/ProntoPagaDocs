---
title: Configura el plugin de PrestaShop
excerpt: >-
  Conoce el paso a paso de cómo configurar el plugin de PrestaShop para tu
  comercio.
deprecated: false
hidden: false
metadata:
  title: Configura el plugin de PrestaShop | ProntoPaga
  description: >-
    Learn how to install, configure, and test the ProntoPaga payment plugin for
    PrestaShop. This guide walks you through setup requirements, plugin
    installation, API credential configuration, supported currencies, payment
    methods, and how to troubleshoot common issues. 
  image: >-
    https://files.readme.io/4cfb0b23dd053db19b8dfa4c65a5f98b4b1b76c6cd21d9f37131bd9116602503-Prontopaga_logotipo.png
  keywords:
    - ProntoPaga PrestaShop plugin
    - install ProntoPaga PrestaShop
    - PrestaShop Peru payments
    - aceptar Yape y Plin en PrestaShop
    - PrestaShop ProntoPaga guide
  robots: index
next:
  description: ''
---
PrestaShop es una plataforma de comercio electrónico de código abierto que permite crear y gestionar tiendas online de forma flexible y personalizada. Contar con un sistema de pagos confiable y eficiente es esencial para ofrecer una experiencia de compra segura y fluida a tus clientes. Para esto, el plugin de ProntoPaga integra una solución de pagos robusta y sencilla de configurar, diseñada específicamente para optimizar el proceso de cobro en tiendas PrestaShop.

Esta guía te llevará paso a paso a través del proceso de instalación, configuración y prueba del plugin de pagos ProntoPaga para PrestaShop.

***

## Requisitos

Antes de comenzar con la instalación, asegúrate de contar con lo siguiente:

* Acceso de tipo administrador a la tienda de PrestaShop en donde instalarás el plugin.
* Descargar previamente el archivo .zip del plugin, [disponible aquí](https://prontopagalatam-my.sharepoint.com/:u:/g/personal/ana_escalante_prontopaga_com/EbQ-WUuMFhpCqKj_ss_kz_cBUsvQG6SrmqE3PZgNJ9_DDg?e=1XIxVE).

***

## Instalación

Para instalar el plugin de pagos ProntoPaga en PrestaShop, sigue estas instrucciones:

1. Ingresa a la cuenta de PrestaShop en la que deseas instalar el plugin de ProntoPaga
2. En el menú lateral izquierdo, dirígete a **Módulos > Administrador de módulos**
3. Haz clic en el botón superior derecho **Subir un módulo**, en donde deberás seleccionar el archivo .zip previamente descargado

<Image align="center" border={false} width="400px" src="https://files.readme.io/2e81297d755c1acf69b6d60ad61b1064eae25a2749e2deb81fefbcff0d0cfc1d-2pres.png" />

4. Espera a que termine la instalación. Al finalizar, verás un mensaje de éxito

***

## Configuración

Una vez instalado el plugin de ProntoPaga, podrás proceder a configurarlo. Para ello, sigue estos pasos:

1. En el menú lateral izquierdo, dirígete a **Pago > Métodos de pago**
2. Busca en la lista de **Módulos de pago activos** el módulo de ProntoPaga y haz clic en el botón **Configurar**, al lado del módulo
3. En **Settings**, usa el selector **Mode** para elegir el enviroment que deseas usar: **Sandbox** o **Producción**
4. Según el enviroment seleccionado, agrega tus credenciales de autenticación:
   1. Authentication Token (Bearer Token)
   2. Secret Key

<Image align="center" border={false} width="400px" src="https://files.readme.io/d10e974198fbb518eef249017ee62318da52b5ca91fcadf80106d7a5b480ad9a-Captura_de_pantalla_2025-05-04_a_las_11.40.21_p.m..png" />

5. Haz clic en **Save settings** para guardar el enviroment y tus credenciales

> 📘 Credenciales
>
> En caso de aún no contar con tus credenciales de autenticación, tanto de Sandbox como de Producción, por favor solicítalas a nuestro equipo: [contacto@prontopaga.com](mailto:contacto@prontopaga.com)

6. Luego, haz clic en **Sync Payment Methods**, para validar las credenciales de tu comercio
7. Una vez se haya realizado la validación de credenciales, podrás elegir la o las monedas que deseas utilizar en tu tienda, así como los métodos de pago asociados a cada moneda

> 🚧 Monedas y métodos de pago
>
> Para poder visualizar todas las monedas y métodos de pago asociados a tu comercio, recuerda que también deberán estar configuradas esas monedas en tu tienda de PrestaShop, en **Internacional > Localización > Monedas**.

### Métodos de pago

Una vez hayas validado tus credenciales y configurado la o las monedas que utilizarás en tu comercio, puedes proceder a elegir los métodos de pago que activarás. Para hacerlo, sigue estos pasos:

1. En el menú lateral izquierdo, dirígete a **Pago > Métodos de pago**
2. Busca en la lista de **Módulos de pago activos** el módulo de ProntoPaga y haz clic en el botón **Configurar**, al lado del módulo
3. Navega hasta el final de la página, en donde podrás visualizar todos los métodos de pago disponibles para tu comercio, divididos por moneda

<Image align="center" border={false} width="420px" src="https://files.readme.io/d3452fd89cd0bc51e2e24154e5d8c6e3872ae860e3fba8f794877a65c67a42cc-Captura_de_pantalla_2025-05-04_a_las_11.44.15_p.m..png" />

4. Para activar uno de los métodos de pago, haz clic sobre su mensaje de **Inactive**
5. Para desactivar uno de los métodos de pago, haz clic sobre su mensaje de **Active**

***

## Prueba tu integración

Para asegurar el correcto funcionamiento de ProntoPaga en tu tienda de PrestaShop, realiza una prueba de pago siguiendo estos pasos:

1. Agrega un producto al carrito

2. Una vez en la página del carrito, haz clic en **FINALIZAR COMPRA**

<Image align="center" border={false} width="400px" src="https://files.readme.io/cb61a1ad569e03233681a6af53eeadc7562e91ffdec24e362a0d526d155328c7-Captura_de_pantalla_2025-05-04_a_las_6.35.13_p.m..png" />

3. Ingresa la información solicitada en la secciones de **DATOS PERSONALES**, **DIRECCIONES** y **MÉTODO DE ENVÍO**
4. En **PAGO**, selecciona pagar con ProntoPaga, y elige el método de pago que deseas probar

<Image align="center" border={false} width="400px" src="https://files.readme.io/1ab8c2ea0e3d1f66b57e9af359c72e2421e5c80454f6d426c6dd1ff1f1834b2d-Captura_de_pantalla_2025-05-04_a_las_6.56.21_p.m..png" />

5. Se abrirá la experiencia de ProntoPaga, en donde podrás comprobar que el pago se realice correctamente

<Image align="center" border={false} width="400px" src="https://files.readme.io/575c390adda0ba637282daa182c77940e1ed878260a5ff477ad42cae03b50ec9-QRpresta.png" />

> 👍 Set de pruebas
>
> Te sugerimos hacer varias pruebas (exitosas y no exitosas) por cada método de pago, para confirmar el correcto funcionamiento de la pasarela.

6. Verifica que la redirección, validación y respuesta del pago funcionen adecuadamente

***

## Solución de problemas comunes

A continuación, se presenta una tabla con los problemas más comunes asociados a esta instalación, así como las soluciones sugeridas.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Problema</b></th>
      <th><b>Solución sugerida</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>No aparece el módulo de ProntoPaga en los Módulos de pago activos</td><td>a. Verifica si el plugin se subió correctamente. b. Intenta subirlo nuevamente. c. Verifica si el plugin está activo en <b>Módulos > Administrador de módulos</b>, en el selector de opciones (al lado del botón <b>Configurar</b> del plugin)</td></tr>
    <tr><td>Error de redirección al pagar</td><td>Revisa las credenciales API configuradas</td></tr>
    <tr><td>No aparece ProntoPaga como opción de pago en el <i>checkout</i></td><td>Asegúrate de que el plugin esté activo y configurado según esta guía</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

### Ayuda con un pedido

En caso de requerir ayuda con un pedido específico, por favor comparte con nosotros el número de referencia del pedido. Este lo podrás encontrar en **Pedidos > Pedidos**, en la segunda columna, llamada **Referencia**.

***

## Desinstalación

En caso de que desees desactivar el plugin momentáneamente, sigue estos pasos:

1. En el menú lateral izquierdo, dirígete a **Módulos > Administrador de módulos**
2. Busca en el listado o en la barra de búsqueda el módulo de ProntoPaga
3. Haz clic en el selector al lado del botón **Configurar**, para ver más opciones

<Image align="center" border={false} width="420px" src="https://files.readme.io/c3f63fa2fbfdadbc829fe4c114ab6ac047877e5c0285702bd9fb62c113c094d8-Captura_de_pantalla_2025-05-05_a_las_12.02.12_a.m..png" />

4. Selecciona la opción de **Desactivar**

Si deseas desinstalar el plugin, realiza lo siguiente:

1. En el menú lateral izquierdo, dirígete a **Módulos > Administrador de módulos**
2. Busca en el listado o en la barra de búsqueda el módulo de ProntoPaga
3. Haz clic en el selector al lado del botón **Configurar**, para ver más opciones

<Image align="center" border={false} width="420px" src="https://files.readme.io/c3f63fa2fbfdadbc829fe4c114ab6ac047877e5c0285702bd9fb62c113c094d8-Captura_de_pantalla_2025-05-05_a_las_12.02.12_a.m..png" />

4. Selecciona la opción de **Desinstalar**

> ❗️ Eliminación de datos
>
> Al borrar el plugin, también se eliminará la información relacionada, como la tabla de transacciones que se ingresó a la base de datos que hayas indicado.