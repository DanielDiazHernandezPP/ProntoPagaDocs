---
title: Configura el plugin de Adobe Commerce (Magento)
excerpt: 'Conoce cómo configurar el plugin para Adobe Commerce (Magento). '
deprecated: false
hidden: false
metadata:
  title: Configura el plugin de Adobe Commerce (Magento) | ProntoPaga Docs
  description: >-
    Learn how to install, configure, and test the ProntoPaga payment plugin for
    Magento (Adobe Commerce). This guide walks you through setup requirements,
    plugin installation, API credential configuration, supported currencies and
    payment methods, and how to troubleshoot common issues.   
  image: >-
    https://files.readme.io/b418e00d857c464d2927c3fbaf7750b03d1b5996c0f5b68f421fc95a2569c2ac-Prontopaga_logotipo.png
  keywords:
    - Adobe Commerce
    - magento plugin
    - plugin magento prontopaga
    - prontopaga magento
    - acepta pagos con magento
    - plugin de pagos magento
    - prontopaga
  robots: index
next:
  description: ''
---
En ProntoPaga desarrollamos este **_plugin_ para integrarse específicamente con Adobe Commerce (antes Magento)**, permitiéndote aceptar pagos de forma segura, rápida y eficiente. Adobe Commerce es una plataforma de código abierto para personalizar, administrar y optimizar una tienda de comercio electrónico.

Esta guía te llevará paso a paso a través del **proceso de instalación, configuración y prueba del _plugin_ de pagos ProntoPaga** para Adobe Commerce.

***

## Requisitos

Antes de comenzar con la instalación, debes contar con lo siguiente:

* Descargar previamente el [archivo .zip](https://drive.google.com/uc?export=download\&id=1ZnY6Rj4Xw_9xwWTJC7zz-n1zYN729UOb) del _plugin_.
* Tener **permiso de administrador en la tienda de Adobe Commerce** donde instalarás el _plugin_
* Contar con la **versión 2.4 hasta 2.4.3** de Magento Commerce Cloud instalada
* Disponer de un certificado SSL de al **menos 246 bits**
* Acceso a **SFTP o terminal del servidor** para ejecutar comandos

***

## Instalación

Para **instalar el plugin de pagos ProntoPaga en Adobe Commerce**, sigue estas instrucciones:

1. Sube la carpeta _app_ mediante FTP a la carpeta de instalación de Magento.
   **Ejemplo**: `/var/www/html/app`Deberás ver la carpeta app de ProntoPaga.
2. Ejecuta los siguientes **comandos en el directorio raíz** de Magento:

```
$ composer require improntus/module-prontopaga
$ php bin/magento module:enable Improntus_ProntoPaga --clear-static-content
$ php bin/magento setup:upgrade
$ php bin/magento setup:static-content:deploy
```

3. ¡Listo! **El _plugin_ ha sido instalado correctamente**. Ahora puedes continuar con la configuración desde el panel de administración de Magento.”.

***

### Verificación de la instalación y configuración

Una vez instalado el plugin desde la terminal, termina la configuración, siguiendo estos pasos:

1. Ve al administrador de tu sitio web
2. Dirígete al menú **Tiendas** -> Configuración
3. Selecciona **Ventas** -> Métodos de pago
4. Busca **ProntoPaga** y escribe el **_Merchant ID_, Usuario y Contraseña** según el entorno que usarás:
   1. ⚙️ **Entorno de integración (pruebas):**
   * Las transacciones no serán contabilizadas ni tendrán validez.
   * Te recomendamos **no utilizar tarjetas reales**.
   * Configuración: `debug: Yes`
   <br />
   1. ✅ **Entorno de producción:**
   * Las transacciones **serán reales y contabilizadas**, por lo tanto, debes ingresar tarjetas reales.
   * Configuración`debug: No`

<Image align="center" border={true} width="500px" src="https://files.readme.io/f38a4bb87e18441c01a124652b617efcb34d9ba07ded4001b3cba4d401076d4b-image.png" className="border" />

***

### Campos de configuración

La siguiente tabla presenta una descripción de todos los **campos que debes llenar al configurar el _plugin_** de Magento.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Configuración
      </th>

      <th>
        Descripción
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **_Enable_**
      </td>

      <td>
        Habilita o deshabilita el método de pago.
      </td>
    </tr>

    <tr>
      <td>
        **Título**
      </td>

      <td>
        Nombre del método de pago que aparece en el pedido (administrador Magento).
      </td>
    </tr>

    <tr>
      <td>
        **_Merchant ID_**
      </td>

      <td>
        Código de comercio en soles creado al momento de la afiliación.
      </td>
    </tr>

    <tr>
      <td>
        **_Merchant ID Dollar_**
      </td>

      <td>
        Código de comercio en dólares creado al momento de la afiliación.
      </td>
    </tr>

    <tr>
      <td>
        **Usuario**
      </td>

      <td>
        Usuario de acceso que permite invocar al API de seguridad y crear un token de acceso.
      </td>
    </tr>

    <tr>
      <td>
        **Contraseña**
      </td>

      <td>
        Contraseña de acceso que permite invocar al API de Seguridad y crear un token de acceso.
      </td>
    </tr>

    <tr>
      <td>
        _**Debug**_
      </td>

      <td>
        Activa o desactiva el modo producción.

        * _YES ⇒ Desarrollo_
        * _NO ⇒ Producción_
      </td>
    </tr>

    <tr>
      <td>
        **Título del formulario**
      </td>

      <td>
        Nombre del método de pago que aparece en el _checkout_.
      </td>
    </tr>

    <tr>
      <td>
        **Descripción en el formulario**
      </td>

      <td>
        Descripción del método de pago que aparece en el _checkout_.
      </td>
    </tr>

    <tr>
      <td>
        **Subir logo**
      </td>

      <td>
        Subir imagen del logo que aparecerá en el formulario.
        Tamaño sugerido: 187x40px.
      </td>
    </tr>

    <tr>
      <td>
        **Color del botón**
      </td>

      <td>
        Define el color del botón “Pagar” en el formulario.
        Valor por defecto: **#FF0000**
      </td>
    </tr>

    <tr>
      <td>
        **Mostrar cantidad**
      </td>

      <td>
        Muestra el importe a pagar en el formulario.
      </td>
    </tr>

    <tr>
      <td>
        **Tamaño botón**
      </td>

      <td>
        Tamaño del botón de pago.

        * _SMALL_
        * _MEDIUM_
        * _LARGE_
        * _DEFAULT_
      </td>
    </tr>

    <tr>
      <td>
        **Política de devolución URL**
      </td>

      <td>
        Dirección URL de las políticas de devolución.
      </td>
    </tr>

    <tr>
      <td>
        _**WebSite Ip**_
      </td>

      <td>
        Dirección IP del servidor.
      </td>
    </tr>

    <tr>
      <td>
        **Términos y condiciones URL**
      </td>

      <td>
        Dirección URL de los términos y condiciones del comercio.
      </td>
    </tr>
  </tbody>
</Table>

***

## Prueba tu integración

Para asegurar el correcto funcionamiento de ProntoPaga en tu cuenta de Adobe Commerce, **realiza una prueba de pago** siguiendo estos pasos:

1. Ingresa a tu cuenta de Adobe Commerce con tu usuario y contraseña.
2. Selecciona un producto y haz clic **Add to Cart**.

<Image align="center" border={true} width="300px" src="https://files.readme.io/410cf78022f6d78742bcc5c4a74e64cd23cb4657c77afa05104f4ffbac4c1554-image.png" className="border" />

3. Dirígete al carrito de compras, ubicado en la parte superior derecha de tu página y haz clic en **Proceed to Checkout**

<Image align="center" border={true} width="350px" src="https://files.readme.io/18b54951366a5e121eee4a487d10a541cc5583c8bd16babbf5f7243a136d5cd9-image.png" className="border" />

4. Llena el formulario con tus datos personales y selecciona **Next**.
5. En esta sección, selecciona el método de pago, ingresa tu documento de identidad y haz clic en **Place Order**.

<Image align="center" border={true} width="400px" src="https://files.readme.io/614b71076823a0457837bbf586a0b11a026811d2de50e7b2a7a9c32147062cd0-image.png" className="border" />

6. Completa los campos con los datos de prueba de tu tarjeta.
7. ¡Listo! **Recibirás la confirmación del pago** en el correo electrónico registrado.

> 👍 Set de pruebas
>
> Te sugerimos **hacer varias pruebas (exitosas y no exitosas)** por cada método de pago, para confirmar el correcto funcionamiento del plugin.

***

## Solución de problemas comunes

A continuación, se presenta una tabla con los problemas más comunes asociados a esta instalación, así como las soluciones sugeridas.

| Problema                                  | Solución sugerida                                                            |
| :---------------------------------------- | :--------------------------------------------------------------------------- |
| Error de instalación de _plugin_          | Debes validar que la versión de Magento que estás instalando sea la correcta |
| El _plugin_ no aparece en el Admin        | Verifica si se instaló en el _workspace_ correcto y si fue publicado         |
| Error de redirección al pagar             | Revisa las credenciales API configuradas                                     |
| ProntoPaga no aparece como opción de pago | Asegúrate de que el _plugin_ esté activo y configurado                       |

***

## Desinstalación

Si deseas desactivar el plugin, sigue estos pasos:

1. **Accede al servidor**   : Conéctate a tu servidor a través de SSH usando un usuario con los permisos adecuados o el terminal desde tu Cpanel.   Por ejemplo: ssh usuario@tuservidor.
2. **Cambia al directorio raíz de Magento**   : Ubica la carpeta donde está instalado Magento:   `cd /ruta/a/tu/magento`
3. **Verifica el nombre exacto del módulo:**   Lista todos los módulos instalados para identificar el nombre del _plugin_ que deseas desinstalar:

* `   php bin/magento`
* module: status  . El módulo aparecerá con un formato similar a:  **Vendor_NombreDelModulo**  .  Apunta el nombre exacto, ya que lo necesitarás para el siguiente paso.

4. **Deshabilita el módulo**   : Desactiva el módulo para evitar que Magento intente cargarlo:

* php bin/magento - module: disable - Vendor_NombreDelModulo

**Verifica que se haya deshabilitado correctamente:**

* php bin/magento - module: status
  Debe aparecer en la lista de **módulos deshabilitados**.

5. **Ejecuta el comando de desinstalación**   : Magento ofrece un comando específico para **desinstalar completamente el módulo**, incluyendo datos en la base de datos.

* php bin/magento
* module: uninstall
* Vendor_NombreDelModulo
* **Advertencia**: Este paso elimina datos relacionados con el módulo.  Si solo deseas deshabilitarlo sin borrar información, omite este paso.

6. **Limpia caché y genera archivos**   : Después de la desinstalación, limpia la caché y vuelve a compilar:

```
php bin/magento setup:upgrade
php bin/magento cache:flush
php bin/magento setup:di:compile
php bin/magento setup:static-content:deploy -f
```

7. **Elimina los archivos del módulo (opcional)**   : Si el _plugin_ fue instalado manualmente, borra la carpeta del directorio app/code o de _vendor_ si fue instalado vía Composer.

* **Si fue instalado manualmente:**  rm -rf app/code/Vendor/NombreDelModulo
* **Si fue instalado vía Composer**: primero, busca el nombre exacto del paquete:  composer show  , luego desinstálalo:  composer remove - vendor/nombre-del-paquete

8. **Verifica el funcionamiento**

* Ingresa al Dashboard de Magento y confirma que la tienda funciona correctamente.
* Revisa que el plugin ya no aparezca en Stores > Configuration > Advanced > Advanced.
* Prueba procesos críticos, como el flujo de pago y la carga de productos.
* Listo, habrás desinstalado el _plugin_.

***

## Ayuda con un pedido

Si necesitas ayuda con un pedido o identificas **errores persistentes con el plugin**, por favor, comunícate con soporte de ProntoPaga al correo electrónico [support@prontopaga.com](mailto:support@prontopaga.com).

***

## Recursos adicionales

Estos son algunos enlaces que podrían ser de utilidad durante este proceso:

* [Documentación oficial de Adobe Commerce](https://developer.adobe.com/commerce/docs/)
* [Repositorio de ProntoPaga](https://ci.prontopaga.com/users/sign_in)

<br />
