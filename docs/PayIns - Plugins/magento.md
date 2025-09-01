---
title: Adobe Commerce (Magento)
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  keywords:
    - plugin magento
    - ' magento plugin'
    - ' plugin magento prontopaga'
    - ' prontopaga magento'
    - ' acepta pagos con magento'
    - ' plugin de pagos magento'
    - ' prontpaga'
  robots: index
next:
  description: ''
---
En ProntoPaga desarrollamos este **_plugin_ de pagos para integrarse específicamente con Adobe Commerce (antes Magento)**, permitiendote aceptar pagos de forma segura, rápida y eficiente. Adobe Commerce es una plataforma de código abierto para personalizar, administrar y optimizar una tienda de comercio electrónico.

Esta guía te llevará paso a paso a través del proceso de instalación, configuración y prueba del _plugin_ de pagos ProntoPaga para Adobe Commerce.

## Requisitos

Antes de comenzar con la instalación, asegúrate de contar con lo siguiente:

* Acceso de tipo administrador a la tienda de Adobe Commerce en donde instalarás el plugin
* Versión instalada de Magento Commerce Cloud desde la 2.4 hasta la 2.4.3.
* [Descargar previamente el archivo .zip del plugin](https://prontopagalatam-my.sharepoint.com/:f:/g/personal/tahbet_reategui_prontopaga_com/Eg9ZKZSWz6tOkFFvIVhajxYBztk09ndEYM9c53afjr2uQw?e=XhEXJp)
* SSL de 246 _bits_ como mínimo
* Accesos a SFTP o terminal del servidor para ejecutar comandos

## Instalación

Para instalar el plugin de pagos ProntoPaga en Adobe Commerce, sigue estas instrucciones:

1. Subir la carpeta app mediante FTP a la carpeta de instalación de Magento. Por
   ejemplo:`/var/www/html/app`
2. Aplica el siguiente comando en el directorio raíz de Magento:

`$ composer require improntus/module-prontopaga
$ php bin/magento module:enable Improntus_ProntoPaga --clear-static-content
$ php bin/magento setup:upgrade
$ php bin/magento setup:static-content:deploy`

3. Una vez terminado, ve al administrador de tu sitio web y :
   1. Dirígete al menú **Tiendas** -> Configuración
   2. Selecciona **Ventas** -> Métodos de pago
   3. Busca ProntoPaga y escribe el _Merchant ID_, Usuario y Contraseña según el entorno a utilizar:
      1. **Entorno de integración (pruebas):**
      * En este entorno las transacciones no serán contabilizadas y no tendrán validez.
      * Te aconsejamos no ingresar tarjetas reales.
      * Nota: Colocar la opción debug: Yes
      1. **Entorno de producción:**
      * En este modo las transacciones serán reales y serán contabilizadas, por lo tanto, deberá
        colocar tarjetas reales.
      * Nota: Colocar la opción debug: No

### Descripción de los campos

<br />

# Configuración del Módulo de Pago en Magento

# Configuración del Módulo de Pago en Magento

<br />

\<table>
&#x20; \<thead>
&#x20;   \<tr style="background-color:#f46f25; color:white; text-align:left;">
&#x20;     \<th>Configuración\</th>
&#x20;     \<th>Descripción\</th>
&#x20;   \</tr>
&#x20; \</thead>
&#x20; \<tbody>
&#x20;   \<tr>\<td>\<b>Enable\</b>\</td>\<td>Habilita o deshabilita el método de pago.\</td>\</tr>
&#x20;   \<tr>\<td>\<b>Título\</b>\</td>\<td>Nombre del método de pago que aparece en el pedido (Administrador Magento).\</td>\</tr>
&#x20;   \<tr>\<td>\<b>Merchant ID\</b>\</td>\<td>Código de comercio en Soles creado al momento de la afiliación.\</td>\</tr>
&#x20;   \<tr>\<td>\<b>Merchant ID Dollar\</b>\</td>\<td>Código de comercio en Dólares creado al momento de la afiliación.\</td>\</tr>
&#x20;   \<tr>\<td>\<b>Usuario\</b>\</td>\<td>Usuario de acceso que permite invocar al API de Seguridad y crear un token de acceso.\</td>\</tr>
&#x20;   \<tr>\<td>\<b>Contraseña\</b>\</td>\<td>Contraseña de acceso que permite invocar al API de Seguridad y crear un token de acceso.\</td>\</tr>
&#x20;   \<tr>\<td>\<b>Debug\</b>\</td>\<td>Activa o desactiva el modo producción.\<br>• YES ⇒ Desarrollo\<br>• NO ⇒ Producción\</td>\</tr>
&#x20;   \<tr>\<td>\<b>Título del formulario\</b>\</td>\<td>Nombre del método de pago que aparece en el checkout.\</td>\</tr>
&#x20;   \<tr>\<td>\<b>Descripción en el formulario\</b>\</td>\<td>Descripción del método de pago que aparece en el checkout.\</td>\</tr>
&#x20;   \<tr>\<td>\<b>Subir logo\</b>\</td>\<td>Subir imagen del logo que aparecerá en el formulario.\<br>Tamaño sugerido: 187x40px.\</td>\</tr>
&#x20;   \<tr>\<td>\<b>Color del botón\</b>\</td>\<td>Define el color del botón “Pagar” en el formulario.\<br>Valor por defecto: \<span style="color:#FF0000; font-weight:bold;">#FF0000\</span>\</td>\</tr>
&#x20;   \<tr>\<td>\<b>Mostrar cantidad\</b>\</td>\<td>Muestra el importe a pagar en el formulario.\</td>\</tr>
&#x20;   \<tr>\<td>\<b>Tamaño botón\</b>\</td>\<td>Tamaño del botón de pago.\<br>• SMALL\<br>• MEDIUM\<br>• LARGE\<br>• DEFAULT\</td>\</tr>
&#x20;   \<tr>\<td>\<b>Política de devolución URL\</b>\</td>\<td>Dirección URL de las políticas de devolución.\</td>\</tr>
&#x20;   \<tr>\<td>\<b>WebSite Ip\</b>\</td>\<td>Dirección IP del servidor.\</td>\</tr>
&#x20;   \<tr>\<td>\<b>Términos y Condiciones URL\</b>\</td>\<td>Dirección URL de los términos y condiciones del comercio.\</td>\</tr>
&#x20; \</tbody>
\</table>


<br />

| Descripción                                                                   |
| :---------------------------------------------------------------------------- |
| Habilita o deshabilita em método de pago                                      |
| Nombre del método de pago que aparece en el pedido (Administrador de Magento) |

## Verificación de la instalación y configuración

Una vez instalado el plugin desde la terminal, verifica la instalación en el Admin de Adobe Commerce y termina la configuración, siguiendo estos pasos:

## Prueba tu integración

Para asegurar el correcto funcionamiento de ProntoPaga en tu cuenta de Adobe Commerce, realiza una prueba de pago siguiendo estos pasos:

1. Agrega un producto al carrito, para ello selecciona Add to Cart.

<Image align="center" width="500px" src="https://files.readme.io/75754c87e33d4c0d3d2a1ee9f1c8791c28be3eed4962111ad111db9753433dbe-image.png" />

1. Una vez en la página del carrito, selecciona la forma de pago y haz clic en **Place Order**.

<Image align="center" className="border" border={true} width="500px" src="https://files.readme.io/614b71076823a0457837bbf586a0b11a026811d2de50e7b2a7a9c32147062cd0-image.png" />

Completa los campos con los datos de prueba de tu tarjeta.

1. ¡Listo! Recibirás la confirmación del pago en el correo electrónico registrado.

> 👍 Set de pruebas
>
> Te sugerimos hacer varias pruebas (exitosas y no exitosas) por cada método de pago, para confirmar el correcto funcionamiento de la pasarela.

## Solución de problemas comunes

A continuación, se presenta una tabla con los problemas más comunes asociados a esta instalación, así como las soluciones sugeridas.

<br />

| Problema | Solución sugerida |
| :------- | :---------------- |

* Debes validar que la versión que estás instalando sea la correcta, de lo contrario te aparecerá un mensaje de error.

### Ayuda con un pedido

En caso de requerir ayuda con un pedido específico, por favor comparte con nosotros el número de referencia del pedido.

<br />

## Desinstalación

En caso de que desees desactivar el plugin momentáneamente, sigue estos pasos:

<br />

## Recursos adicionales

Estos son algunos enlaces que podrían ser de utilidad durante este proceso:

* [Documentación oficial de Adobe Commerce](https://developer.adobe.com/commerce/docs/)
* [Repositorio de ProntoPaga](https://ci.prontopaga.com/users/sign_in)
* Soporte de ProntoPaga (en caso de errores persistentes con la pasarela): [roger.pecho@prontopaga.com](mailto:roger.pecho@prontopaga.com)

##
