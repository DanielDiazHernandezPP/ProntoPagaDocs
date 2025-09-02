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
En ProntoPaga desarrollamos este **_plugin_ para integrarse específicamente con Adobe Commerce (antes Magento)**, permitiéndote aceptar pagos de forma segura, rápida y eficiente. Adobe Commerce es una plataforma de código abierto para personalizar, administrar y optimizar una tienda de comercio electrónico.

Esta guía te llevará paso a paso a través del **proceso de instalación, configuración y prueba del _plugin_ de pagos ProntoPaga** para Adobe Commerce.

***

## Requisitos

Antes de comenzar con la instalación, debes contar con lo siguiente:

* [Archivo .zip del _plugin_ previamente descargado](https://prontopagalatam-my.sharepoint.com/:f:/g/personal/tahbet_reategui_prontopaga_com/Eg9ZKZSWz6tOkFFvIVhajxYBztk09ndEYM9c53afjr2uQw?e=XhEXJp) 
* Acceso con **permiso de administrador a la tienda de Adobe Commerce** en donde instalarás el _plugin_
* Magento Commerce Cloud **versión 2.4 hasta 2.4.3** instalada
* Certificado SSL de al **menos 246 bits**
* Acceso a **SFTP o terminal del servidor** para ejecutar comandos

***

## Instalación

Para **instalar el plugin de pagos ProntoPaga en Adobe Commerce**, sigue estas instrucciones:

1. Sube la carpeta _app_ mediante FTP a la carpeta de instalación de Magento.
   **Ejemplo**: `/var/www/html/app`Deberá ver la carpeta app de ProntoPaga. 
2. Ejecuta los siguientes comandos en el directorio raíz de Magento:

```
$ composer require improntus/module-prontopaga
$ php bin/magento module:enable Improntus_ProntoPaga --clear-static-content
$ php bin/magento setup:upgrade
$ php bin/magento setup:static-content:deploy
```

***

### Verificación de la instalación y configuración

Una vez instalado el plugin desde la terminal, termina la configuración, siguiendo estos pasos:

1. Ve al administrador de tu sitio web 
2. Dirígete al menú **Tiendas** -> Configuración
3. Selecciona **Ventas** -> Métodos de pago
4. Busca **ProntoPaga** y escribe el **_Merchant ID_, Usuario y Contraseña** según el entorno que usarás:
   1. ⚙️**Entorno de integración (pruebas):**
   * Las transacciones no serán contabilizadas ni tendrán validez.
   * Te recomendamos **no utilizar tarjetas reales**.
   * Configuración: `debug: Yes`
   1. ✅**Entorno de producción:**
   * Las transacciones **serán reales y contabilizadas**, por lo tanto, debes ingresar tarjetas reales.
   * Configuración`debug: No`

### Descripción de los campos

La siguiente tabla presenta una descripción de todos los **campos que debes llenar al configurar el _plugin_** de Magento.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th>Configuración</th>
      <th>Descripción</th>
    </tr>
  </thead>
  <tbody>
    <tr><td><b><em>Enable<em></b></td><td>Habilita o deshabilita el método de pago.</td></tr>
    <tr><td><b>Título</b></td><td>Nombre del método de pago que aparece en el pedido (administrador Magento).</td></tr>
    <tr><td><b><em>Merchant ID<em></b></td><td>Código de comercio en soles creado al momento de la afiliación.</td></tr>
    <tr><td><b><em>Merchant ID Dollar<em></b></td><td>Código de comercio en dólares creado al momento de la afiliación.</td></tr>
    <tr><td><b>Usuario</b></td><td>Usuario de acceso que permite invocar al API de seguridad y crear un token de acceso.</td></tr>
    <tr><td><b>Contraseña</b></td><td>Contraseña de acceso que permite invocar al API de Seguridad y crear un <em>token<em> de acceso.</td></tr>
    <tr><td><b><em>Debug<em></b></td><td>Activa o desactiva el modo producción.<br>• <em>YES<em> ⇒ Desarrollo<br>• NO ⇒ Producción</td></tr>
    <tr><td><b>Título del formulario</b></td><td>Nombre del método de pago que aparece en el <em>checkout<em>.</td></tr>
    <tr><td><b>Descripción en el formulario</b></td><td>Descripción del método de pago que aparece en el <em>checkout<em>.</td></tr>
    <tr><td><b>Subir logo</b></td><td>Subir imagen del logo que aparecerá en el formulario.<br>Tamaño sugerido: 187x40px.</td></tr>
    <tr><td><b>Color del botón</b></td><td>Define el color del botón “Pagar” en el formulario.<br>Valor por defecto: <span style="color:#FF0000; font-weight:bold;">#FF0000</span></td></tr>
    <tr><td><b>Mostrar cantidad</b></td><td>Muestra el importe a pagar en el formulario.</td></tr>
    <tr><td><b>Tamaño botón</b></td><td>Tamaño del botón de pago.<br>• <em>SMALL<em><br>• <em>MEDIUM<em><br>• <em>LARGE<em><br>• <em>DEFAULT<em></td></tr>
    <tr><td><b>Política de devolución URL</b></td><td>Dirección URL de las políticas de devolución.</td></tr>
    <tr><td><b><em>WebSite<em> Ip</b></td><td>Dirección IP del servidor.</td></tr>
    <tr><td><b>Términos y condiciones URL</b></td><td>Dirección URL de los términos y condiciones del comercio.</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

***

## Prueba tu integración

Para asegurar el correcto funcionamiento de ProntoPaga en tu cuenta de Adobe Commerce, realiza una prueba de pago siguiendo estos pasos:

1. Agrega un producto al carrito, para ello selecciona Add to Cart.

<Image align="center" width="500px" src="https://files.readme.io/75754c87e33d4c0d3d2a1ee9f1c8791c28be3eed4962111ad111db9753433dbe-image.png" />

2. Una vez en la página del carrito, selecciona la forma de pago y haz clic en **Place Order**.

<Image align="center" className="border" border={true} width="500px" src="https://files.readme.io/614b71076823a0457837bbf586a0b11a026811d2de50e7b2a7a9c32147062cd0-image.png" />

3. Completa los campos con los datos de prueba de tu tarjeta.
4. ¡Listo! Recibirás la confirmación del pago en el correo electrónico registrado.

> 👍 Set de pruebas
>
> Te sugerimos hacer varias pruebas (exitosas y no exitosas) por cada método de pago, para confirmar el correcto funcionamiento de la pasarela.

## Solución de problemas comunes

A continuación, se presenta una tabla con los problemas más comunes asociados a esta instalación, así como las soluciones sugeridas.

| Problema                       | Solución sugerida                                                            |
| :----------------------------- | :--------------------------------------------------------------------------- |
| Error de instalación de plugin | Debes validar que la versión de Magento que estás instalando sea la correcta |

***

### Ayuda con un pedido

Si necesitas ayuda con un pedido o identificas **errores persistentes con la pasarela**, por favor, comunícate con soporte de ProntoPaga al correo electrónico [roger.pecho@prontopaga.com](mailto:roger.pecho@prontopaga.com).

***

## Desinstalación

Si deseas desactivar el plugin momentáneamente, sigue estos pasos:

`Elimina` el 

## Recursos adicionales

Estos son algunos enlaces que podrían ser de utilidad durante este proceso:

* [Documentación oficial de Adobe Commerce](https://developer.adobe.com/commerce/docs/)
* [Repositorio de ProntoPaga](https://ci.prontopaga.com/users/sign_in)

<br />
