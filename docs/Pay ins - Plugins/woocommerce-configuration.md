---
title: '[DEPRECATED] Guía de Configuración - WC'
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: >-
    The document provides instructions for configuring the ProntoPaga plugin in
    WooCommerce.
  keywords:
    - woocommerce
    - ' configuration'
    - ' guide'
    - ' woocommerce plugin'
    - ' payins'
    - ' prontopaga'
    - ' prontopaga plugin'
  robots: index
next:
  description: ''
---
Una vez instalado el plugin de ProntoPaga para WooCommerce, podemos proceder a hacer las configuraciones necesarias. 

## Instrucciones para configurar el plugin

1. En la barra lateral izquierda ubica la opción **WooCommerce **y haz clic en la sección **Ajustes**.

   [block:image]{"images":[{"image":["https://files.readme.io/9a7d97d-config1-77ca90585877bf8bf8fa05083c473f0c.png","",""],"align":"center"}]}[/block]

2. En **Ajustes**, selecciona la pestaña **Pagos**. Al entrar, busca en la lista de **Método de pago** el método "BNC - Interfaz de Pago Electrónico - ProntoPaga", y haz clic en el botón **Gestionar.**

   [block:image]{"images":[{"image":["https://files.readme.io/a989424-config2-5c0d087c35f05e9e4e106adce9687252.png","",""],"align":"center"}]}[/block]

3. Introduce los siguientes parámetros de configuración:  
   a. Habilita el método de pago.  
   b. Token de autenticación del comercio, proporcionado por ProntoPaga.  
   c. API Key (llave secreta), proporcionada por ProntoPaga.  
   d. Título. Es el título que el usuario verá durante el proceso de pago.  
   e. URL, valor por defecto: <https://sandbox.insospa.com/api/>  
   f. Descripción. Es la descripción que el usuario verá durante el proceso de pago.  
   g. Imagen. Es la imagen que se mostrará al desplegar el método de pago en la página de _checkout_. Puedes descargar los logos de los diferentes métodos de pago en [este enlace](https://drive.google.com/uc?export=download&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr).

   [block:image]{"images":[{"image":["https://files.readme.io/3814976-config3-672eb4ac5c583797dc84fe6f4cacc289.png","",""],"align":"center"}]}[/block]

4. Presiona el botón **Guardar cambios**.

5. Es necesario instalar otro plugin para agregar un campo al formulario de pago. Recomendamos instalar el plugin "Checkout Field Editor (Checkout Manager) for WooCommerce". Para hacerlo:

5.1 En la barra lateral izquierda selecciona la opción **Plugins** y haz clic en la sección **Add New Plugin**.

5.2 En la pantalla de **Añadir Plugins**, ingresa la palabra clave "Checkout" en el campo de búsqueda. Luego, ubica en la lista el plugin "Checkout Field Editor (Checkout Manager) for WooCommerce" y haz clic en el botón **Instalar ahora**.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/88cf6e5-config5-ce8e03727e1f7d871ec20af8edcf4e65.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


5.3 A continuación, haz clic en el botón **Activar**.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/eb61aab-configC-f125d2bb0a74c19c9fcac193e185a889.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


5.4 Posteriormente, en la barra lateral izquierda selecciona la opción WooCommerce y haz clic en la sección **Formulario de pago**.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0d3deb0-configD-7cae22fc3207ba82185035c762898185.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


5.5 Una vez en la pantalla de **Formulario de Pago**, en la pestaña de **Checkout Fields**, haz clic en el botón **+Añadir un campo**. Al hacerlo, se abrirá una ventana modal:  
i. En la ventana modal de **New Field**, ingresa el término "client_document" en el campo **Nombre**.  
ii. En el campo **Etiqueta**, ingresa la descripción del campo, en este caso, "RUT".  
iii. Haz clic en el botón **Save & Close**.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/03c8c52-configE-3c3eef2b081529ba79dcd7013695e246.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]