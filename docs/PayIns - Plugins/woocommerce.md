---
title: Configura el plugin de WooCommerce
excerpt: >-
  Conoce el paso a paso de cómo configurar el plugin de WooCommerce para tu
  comercio.
deprecated: false
hidden: false
metadata:
  title: Configura el plugin de WooCommerce | ProntoPaga Docs
  description: >-
    Learn how to install, configure, and test the ProntoPaga payment plugin for
    WooCommerce. This guide walks you through setup requirements, plugin
    installation, API credential configuration, supported currencies and payment
    methods, and how to troubleshoot common issues.   
  image: >-
    https://files.readme.io/e53ff0cbfc3b6619dae24c75c132751145d191cc3b4ed877c7fbae5621d0ee4f-Prontopaga_logotipo.png
  keywords:
    - plugin woocommerce prontopaga
    - plugin de pagos woocommerce
    - plugin de pagos wordpress
    - prontopaga plugins
    - install Prontopaga WooCommerce
    - WooCommerce Peru payments
    - WooCommerce ProntoPaga guide
  robots: index
next:
  description: ''
---
En ProntoPaga desarrollamos este plugin de pagos específicamente para integrarse con WooCommerce en la plataforma WordPress, permitiendo a tu tienda en línea aceptar pagos de forma segura, rápida y eficiente.

Esta guía te llevará paso a paso a través del proceso de instalación, configuración y prueba del plugin de pagos ProntoPaga para WooCommerce.

***

<br />

## Requisitos

Antes de comenzar con la instalación, asegúrate de contar con lo siguiente:

* Acceso de tipo administrador a la tienda de WooCommerce en donde instalarás el plugin.
* Descargar previamente el archivo .zip del plugin, [disponible aquí](https://drive.google.com/uc?export=download\&id=1GBeWHdoyFovihNltMqwZEQxFj8U2ho2X).

***

<br />

## Instalación

Para instalar el plugin de pagos ProntoPaga en WooCommerce, sigue estas instrucciones:

1. En el menú lateral de WooCommerce, dirígete a **Plugins > Añadir plugin**.
2. Haz clic en el botón superior **Subir plugin**, en donde deberás seleccionar el archivo .zip previamente descargado

<Image align="center" border={false} width="450px" src="https://files.readme.io/52ca502e35a0a7fa7dd938c2f81e73949970f236e0e5b8e212faaab01ebd5663-1wc.png" />

3. Cuando se haya cargado el archivo, haz clic en **Instalar ahora**
4. Al finalizar la instalación, haz clic en el botón azul de **Activar plugin**
5. Si el proceso fue exitoso, ahora verás el módulo de **ProntoPaga** en el menú lateral de WooCommerce

***

<br />

## Configuración

Una vez instalado el plugin de ProntoPaga, podrás proceder a configurarlo, seleccionar los métodos de pago y personalizar sus textos.

Para configurarlo y elegir los métodos de pago, sigue estos pasos:

1. En el menú lateral de WooCommerce, dirígete a **ProntoPaga**
2. Selecciona el enviroment que deseas usar: **Sandbox** o **Producción**
3. Según el enviroment seleccionado, agrega tus credenciales de autenticación:
   1. Token de autenticación (Bearer Token)
   2. Secret Key

<Image align="center" border={false} width="420px" src="https://files.readme.io/3203508386674b3a7b09984a9ded7bb7f51440217034dafd3e99f5dbe8929e92-Captura_de_pantalla_2025-05-04_a_las_11.09.56_p.m..png" />

> 📘 Credenciales
>
> En caso de aún no contar con tus credenciales de autenticación, tanto de Sandbox como de Producción, por favor solicítalas a nuestro equipo: [contacto@prontopaga.com](mailto:contacto@prontopaga.com)

4. Debajo de las credenciales que agregaste, haz clic en **Validar credenciales**, para que se puedan visualizar los métodos de pago asociados a tu comercio
5. Debajo, en **Métodos de pago**, selecciona los métodos de pago que deseas mostrar en tu tienda de WooCommerce

<Image align="center" border={false} width="450px" src="https://files.readme.io/140ba6d396f7ce95b0167090c233e67b6148a8e5535a6f2e4a7111e5b09e7100-Captura_de_pantalla_2025-05-04_a_las_11.12.04_p.m..png" />

6. Haz clic en el botón inferior de **Guardar Configuración**

<br />

### Personalización de textos

Nuestro plugin cuenta con la opción de personalizar el título del método de pago y agregar una descripción. Esta información se mostrará en el carrito de compras del cliente.

Para modificarlo:

1. En el menú lateral de WooCommerce, dirígete a **ProntoPaga**
2. Navega hasta la sección **Apariencia**
3. Agrega el **Título del método de pago** que desees
4. Añade una **Descripción**, si así lo requieres

<Image align="center" border={false} width="450px" src="https://files.readme.io/eb90c4eacc975cd57b4c830722296a993e1a7c99c5ea52cb563b21bdf0fcb12e-Captura_de_pantalla_2025-05-04_a_las_11.13.46_p.m..png" />

5. Haz clic en el botón inferior de **Guardar Configuración**

Este es un ejemplo de cómo se verían el título y la descripción durante el _checkout_:

<Image align="center" border={false} width="320px" src="https://files.readme.io/950e4513979756c17e0fe8c895c6a0fde66085682edd9a5a46c7a0c9a47c53d1-Captura_de_pantalla_2025-05-04_a_las_11.15.48_p.m..png" />

<br />

### Ajustes adicionales

Dependiendo de lo que requiera tu comercio, podrás configurar el estado final de las transacciones como "Procesando" o "Completada". Para hacerlo, sigue estos pasos:

1. En el menú lateral de WooCommerce, dirígete a **ProntoPaga**
2. Navega hasta la sección inferior de **Ajustes adicionales**
3. Selecciona el estado final de las transacciones que deseas utilizar
   1. **Procesando:** Utiliza este estado si necesitas completar el proceso manualmente, por ejemplo, si vas a facturar o enviar el producto.
   2. **Completada:**Utiliza este estado si con el pago el pedido queda completado y no debes hacer nada más, por ejemplo, en el caso de productos digitales.
4. Haz clic en el botón inferior de **Guardar Configuración**

> 📘 Estado de las transacciones
>
> El estado final que selecciones en esta sección será el estado que aparecerá en el listado de **WooCommerce > Pedidos**.

***

<br />

## Prueba tu integración

Para asegurar el correcto funcionamiento de ProntoPaga en tu tienda de WooCommerce, realiza una prueba de pago siguiendo estos pasos:

1. Agrega un producto al carrito

2. Haz clic en el botón **Finalizar compra**, para proceder al _checkout_

<Image align="center" border={false} width="400px" src="https://files.readme.io/0084fd098f3c09c2d5af19ec77805d5889d2a8d94b05fac56d5206e25b3e041d-Captura_de_pantalla_2025-05-04_a_las_3.08.56_p.m..png" />

3. En la página del _checkout_, realiza lo siguiente:
   1. Completa los datos de **Detalles de facturación**
   2. En el detalle de **Tu pedido**, elige ProntoPaga y selecciona el método de pago que probarás
   3. En caso de ser requerido para el método o país, ingresa un número de identificación

<Image align="center" border={false} width="420px" src="https://files.readme.io/71a4c95ec8e4104cc5e54ad9cca79ffd80556ba793935a088a8c09fa5f4dedb0-Captura_de_pantalla_2025-05-04_a_las_3.10.55_p.m..png" />

4. Haz clic en el botón **Realizar el pedido**
5. Se abrirá la experiencia de ProntoPaga, en donde podrás continuar el pago y comprobar que se realice correctamente

<Image align="center" border={false} width="420px" src="https://files.readme.io/9125cfb2a3144888366a1fa2ca6d9fca7e184179b8edb5afbd28d44e5baf2b85-woocomm_check.png" />

> 👍 Set de pruebas
>
> Te sugerimos hacer varias pruebas (exitosas y no exitosas) por cada método de pago, para confirmar el correcto funcionamiento de la pasarela.

6. Verifica que la redirección, validación y respuesta del pago funcionen adecuadamente

***

<br />

## Solución de problemas comunes

A continuación, se presenta una tabla con los problemas más comunes asociados a esta instalación, así como las soluciones sugeridas.

| Problema                                              | Solución sugerida                                                                 |
| :---------------------------------------------------- | :-------------------------------------------------------------------------------- |
| No aparece el módulo de ProntoPaga en el menú lateral | Verifica si el plugin está instalado y activo en **Plugins > Plugins instalados** |
| Error de redirección al pagar                         | Revisa las credenciales API configuradas                                          |
| No aparece ProntoPaga como opción de pago             | Asegúrate de que el plugin esté activo y configurado según esta guía              |

<br />

### Ayuda con un pedido

En caso de requerir ayuda con un pedido específico, por favor comparte con nosotros el número de referencia del pedido. Este lo podrás encontrar en **WooCommerce > Pedidos**, entrando al pedido indicado, en **Notas del pedido**, al lado izquierdo.

***

<br />

## Desinstalación

En caso de que desees desactivar el plugin momentáneamente, sigue estos pasos:

1. En el menú lateral, dirígete a **Plugins > Plugins instalados**
2. Busca el plugin **WooCommerce pagos con ProntoPaga**, y haz clic en la opción de **Desactivar**, debajo del nombre del plugin
3. Como confirmación, notarás que el módulo de ProntoPaga ya no aparece en el menú lateral izquierdo

Si deseas desinstalar el plugin, realiza lo siguiente:

1. En el menú lateral, dirígete a **Plugins > Plugins instalados**
2. Busca el plugin **WooCommerce pagos con ProntoPaga**, y haz clic en la opción de **Desactivar**, debajo del nombre del plugin
3. Ahora verás debajo del nombre del plugin otras opciones; haz clic en **Borrar**

> ❗️ Eliminación de datos
>
> Al borrar el plugin, también se eliminará la información relacionada, como la tabla de transacciones que se ingresó a la base de datos que hayas indicado.
