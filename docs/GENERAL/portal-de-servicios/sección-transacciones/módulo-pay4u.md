---
title: Módulo Pay4U
deprecated: false
hidden: true
metadata:
  robots: index
---
## Pay4U

En esta carpeta podrás consultar todo lo referente a nuestro servicio de pagos Pay4U. Además del módulo específico de **Pagos Pay4U**, esta carpeta cuenta también con módulos para los listados de **Proveedores**, **Colaboradores** y **Prestadores de servicio**.

A continuación, puedes consultar el diagrama de flujo para conocer el proceso de configuración de destinatarios:

<Image align="center" alt="Diagrama General Pay4U" border={true} src="https://files.readme.io/f2e1fb157731061c64a6a1848f492cfa710be28837950b696eccf6f7333a392b-Pay4U_part1.png" className="border" />

<br />

### Proveedores

La categoría de **Proveedores** es generalmente utilizada para asociados a los que se les debe realizar pagos frecuentes o recurrentes.

Este módulo te permite crear un nuevo proveedor, así como consultar el listado de todos los proveedores que tienes registrados. Además, puedes ver sus datos, modificarlos, así como descargar el contrato de cada uno (cargado durante la creación de un proveedor).

El módulo con el listado de proveedores puede verse similar al siguiente:

<Image align="center" alt="Categoría proveedores" border={true} src="https://files.readme.io/d56daa686cf54594eb5286aace94ad8ea86249999b5dd74e2e5290079ce1529a-Proyecto_nuevo.png" className="border" />

<br />

#### Crear un proveedor

Para crear un nuevo proveedor, sigue estos pasos: 

1. Haz clic en el botón de la esquina superior derecha **Crear Proveedor**. 

<Image align="center" alt="Botón Crear proveedor" border={true} src="https://files.readme.io/2737237d60e5a1873963296d17277d27ed3588ca157d69ae71160bf3cf7e8fcd-boton_crear_proveedor.png" className="border" />

2. Serás redirigido a una nueva pestaña, en donde deberás llenar los datos solicitados. Todos son requeridos. 

<Image align="center" alt="Formulario Crear proveedor" border={true} width="80% " src="https://files.readme.io/2feb917188bf4ecd8b4d46ab0ebb44edf7814378a4fb0c2f5444e664359d14f5-Formulario_crear_proveedor.png" className="border" />

<Callout icon="📘" theme="info">
  **Archivos de validación**

  Al crear un proveedor, se pueden subir hasta tres archivos, cada uno con un tamaño máximo de 25 MB, para su validación. 
</Callout>

3. Haz clic en el botón superior derecho **Guardar,** o, si así lo requieres, **Crear y añadir otro**.

<br />

#### Ver detalle de un proveedor

Puedes consultar el detalle de cualquiera de los proveedores listados. Para hacerlo: 

1. Haz clic en el menú de tres puntos, ubicado al final de los campos descriptivos del proveedor, es decir, hasta el lado derecho de la pantalla.  
2. Del menú desplegable, selecciona la opción **Ver**.

<Image align="center" alt="Opción Ver" border={true} width="20% " src="https://files.readme.io/2676179092bfeae46e34078016345f42257164c3c6f64e7a9bd7a4fdbae88b2c-Opcion_ver.png" className="border" />

Serás redirigido a la página de detalle del proveedor. Verás la información dividida en las categorías de: **Detalle del Proveedor**, **Datos de la cuenta del Proveedor**, **Contrato del Proveedor** y **Estado del registro**. 

<br />

#### Modificar los datos de un proveedor

Puedes modificar los datos de cualquiera de los proveedores listados. Para hacerlo: 

1. Haz clic en el menú de tres puntos, ubicado al final de los campos descriptivos del proveedor, es decir, hasta el lado derecho de la pantalla.  
2. Del menú desplegable, selecciona la opción **Modificar**. 

<Image align="center" alt="Opción Ver" border={true} width="20% " src="https://files.readme.io/2676179092bfeae46e34078016345f42257164c3c6f64e7a9bd7a4fdbae88b2c-Opcion_ver.png" className="border" />

3. Serás redirigido a la página editable de datos del proveedor. Verás la información dividida en las categorías de: **Datos de la cuenta del proveedor**, **Contrato del Proveedor** y **Estado del registro**.

<Callout icon="🚧" theme="warn">
  **Modificación de datos**

  Una vez creado el proveedor, solo podrás modificar los siguientes datos: **información de la cuenta bancaria **(**banco**, **titular**, **tipo de cuenta** y **número de cuenta**). El resto de datos no pueden ser modificados. 
</Callout>

4. Al terminar de editar, haz clic en el botón superior derecho **Guardar cambios**. 

<br />

#### Filtros

El módulo de **Proveedores** cuenta con la opción de filtrar el listado. Esto facilita la localización rápida de proveedores específicos. Puedes ver todas las opciones disponibles de filtrado haciendo clic en el botón superior derecho de **Filtros**.

<Image align="center" alt="Filtros " border={true} width="30% " src="https://files.readme.io/d9c813ab534fe1352b4eec7c6a0adda6abf87220c807be645dd99cb15f3a6888-filtros_proveedores.png" className="border" />

<br />

#### Ordenar por campo

Otra manera de modificar cómo se ve la información de la tabla de **Proveedores**, es ordenándola por alguno de los campos descriptivos superiores. Para hacerlo: 

1. Haz clic en las flechas que se encuentran al lado de un campo específico. 

<Image align="center" alt="Ordenar por campo " border={true} src="https://files.readme.io/ce4151017397460fd7229df8df7c99c2f766f31782e3bf1e2c524db70eda35c6-Ordenar_por_campo_1.png" className="border" />

2. Se ordenarán de forma descendente, si la flecha está hacia abajo. 

<Image align="center" alt="Ordenar por campo descendente" border={true} src="https://files.readme.io/f7b8a1431566a221a8d90b1685882f4a2e5dffde88a8c934914d6c17584cb850-Ordenar_por_campo_2.png" className="border" />

3. Para cambiar el orden a ascendente, haz clic nuevamente en la flecha. 

<Image align="center" alt="Ordenar por campo ascendente" border={true} src="https://files.readme.io/38853a9729b9b67dc3905897239bc8f5d1b4b1d2bf8a62acec810e1415d74ea5-Ordenar_por_campo_3.png" className="border" />

***

<br />

### Colaboradores

La categoría de **Colaboradores** es utilizada para realizar el pago de remuneraciones, por lo tanto, la cantidad de registros de colaboradores es mayor. Por esta razón, tras registrarse un colaborador, es posible generar un archivo con los registros seleccionados, completar los datos y usarlo después en pagos masivos.

Este módulo te permite crear un nuevo colaborador, así como consultar el listado de todos los colaboradores que tienes registrados. Además, puedes ver sus datos, modificarlos, así como descargar el contrato de cada uno (cargado durante la creación de un colaborador). 

El módulo con el listado de colaboradores puede verse similar al siguiente: 

<Image align="center" alt="Colaboradores" border={true} src="https://files.readme.io/51daf70cb817002c40d4b3c4111daa31fcc17936ae987e1dbfe910b42f40dd28-Proyecto_nuevo.png" className="border" />

<br />

#### Crear un colaborador

Para crear un nuevo colaborador, sigue estos pasos: 

1. Haz clic en el botón de la esquina superior derecha **Crear Colaborador**.

<Image align="center" border={true} src="https://files.readme.io/4f241d89fc51d8e521ab76370381fda177db42d981a0b5be961904eccd46d6fe-boton_crear_colaborador.png" className="border" />

2. Serás redirigido a una nueva pestaña, en donde deberás llenar los datos solicitados. Todos son requeridos.

<Image align="center" alt="Formulario crear un colaborador" border={true} width="80% " src="https://files.readme.io/08eb3b4f6cb038e1d5f53ae636df5a2f5039757dd61b1815de49197c1c86f068-formulario_crear_colaborador.png" className="border" />

<Callout icon="📘" theme="info">
  **Archivos de validación**

  Al crear un colaborador, se pueden subir hasta tres archivos, cada uno con un tamaño máximo de 25 MB, para su validación. 
</Callout>

3. Haz clic en el botón superior derecho **Guardar,** o, si así lo requieres, **Crear y añadir otro**.

<br />

#### Ver detalle de un colaborador

Puedes consultar el detalle de cualquiera de los colaboradores listados. Para hacerlo: 

1. Haz clic en el menú de tres puntos, ubicado al final de los campos descriptivos del colaborador, es decir, hasta el lado derecho de la pantalla.  
2. Del menú desplegable, selecciona la opción **Ver**.

<Image align="center" alt="Opción Ver" border={true} width="20% " src="https://files.readme.io/2676179092bfeae46e34078016345f42257164c3c6f64e7a9bd7a4fdbae88b2c-Opcion_ver.png" className="border" />

3. Serás redirigido a la página de detalle del colaborador. Verás la información dividida en las categorías de: **Detalle del Colaborador**, **Datos de la cuenta del Colaborador**, **Contrato del Colaborador** y **Estado del registro**. 

<br />

#### Modificar los datos de un colaborador

Puedes modificar los datos de cualquiera de los colaboradores listados. Para hacerlo: 

Haz clic en el menú de tres puntos, ubicado al final de los campos descriptivos del colaborador, es decir, hasta el lado derecho de la pantalla.  

Del menú desplegable, selecciona la opción **Modificar**. 

<Image align="center" alt="Opción Ver" border={true} width="20% " src="https://files.readme.io/2676179092bfeae46e34078016345f42257164c3c6f64e7a9bd7a4fdbae88b2c-Opcion_ver.png" className="border" />

3. Serás redirigido a la página de detalle del colaborador. Verás la información dividida en las categorías de: **Detalle del Colaborador**, **Datos de la cuenta del Colaborador**, **Contrato del Colaborador** y **Estado del registro**. 

<Callout icon="🚧" theme="warn">
  Modificación de datos

  Una vez creado el colaborador, solo podrás modificar los siguientes datos: **información de la cuenta bancaria** (**banco**, **titular**, **tipo de cuenta** y **número de cuenta**). El resto de datos no pueden ser modificados.
</Callout>

4. Al terminar de editar, haz clic en el botón superior derecho **Guardar cambios**. 

<br />

#### Filtros

El módulo de **Colaboradores** cuenta con la opción de filtrar el listado. Esto facilita la localización rápida de colaboradores específicos. Puedes ver todas las opciones disponibles de filtrado haciendo clic en el botón superior derecho de **Filtros**.

<Image align="center" alt="Filtros " border={true} width="30% " src="https://files.readme.io/d9c813ab534fe1352b4eec7c6a0adda6abf87220c807be645dd99cb15f3a6888-filtros_proveedores.png" className="border" />

<br />

#### Ordenar por campo

Otra manera de modificar cómo se ve la información de la tabla de **Colaboradores**, es ordenándola por alguno de los campos descriptivos superiores. Para hacerlo: 

1. Haz clic en las flechas que se encuentran al lado de un campo específico. 

<Image align="center" alt="Ordenar por campo " border={true} src="https://files.readme.io/ce4151017397460fd7229df8df7c99c2f766f31782e3bf1e2c524db70eda35c6-Ordenar_por_campo_1.png" className="border" />

2. Se ordenarán de forma descendente, si la flecha está hacia abajo. 

<Image align="center" alt="Ordenar por campo descendente" border={true} src="https://files.readme.io/f7b8a1431566a221a8d90b1685882f4a2e5dffde88a8c934914d6c17584cb850-Ordenar_por_campo_2.png" className="border" />

3. Para cambiar el orden a ascendente, haz clic nuevamente en la flecha. 

<Image align="center" alt="Ordenar por campo ascendente" border={true} src="https://files.readme.io/38853a9729b9b67dc3905897239bc8f5d1b4b1d2bf8a62acec810e1415d74ea5-Ordenar_por_campo_3.png" className="border" />

***

<br />

### Prestadores de servicios

Se sugiere utilizar la categoría de **Prestadores de servicio** para asociados a los que se les debe realizar pagos una sola vez o de forma esporádica.

Este módulo te permite crear un nuevo prestador de servicio, así como consultar el listado de todos los que tienes registrados. Además, puedes ver sus datos, modificarlos, así como descargar el contrato de cada uno (cargado durante la creación de un prestador de servicio). 

El módulo con el listado de prestadores de servicio puede verse similar al siguiente: 

<Image align="center" alt="Prestadores de servicio vista general" border={true} src="https://files.readme.io/821d2a28c8c3f2d062e2595c5d7427c69f09717f17aaf9065dea049793376173-Prestador_de_servicio.png" className="border" />

<br />

#### Crear un prestador de servicio

Para crear un nuevo prestador de servicio, sigue estos pasos: 

1. Haz clic en el botón de la esquina superior derecha **Crear prestador de servicio**.

<Image align="center" alt="Botón prestadores de servicio" border={true} src="https://files.readme.io/850b6d42d38500137c3aea22cafa7281323cc0bd24b322ae3a98adebcdf6e532-Boton_prestador_de_servicio.png" className="border" />

2. Serás redirigido a una nueva pestaña, en donde deberás llenar los datos solicitados. Todos son requeridos. 

<Image align="center" alt="Formulario prestadores de servicio" border={true} width="80% " src="https://files.readme.io/3f672bf589ff2ee175b18c9add005d6844f2f01df751fd9e00c7f29a5c522cde-Formilario_prestadores_de_servicio.png" className="border" />

<Callout icon="📘" theme="info">
  **Archivos de validación**

  Al crear un prestador de servicio, se pueden subir hasta tres archivos, cada uno con un tamaño máximo de 25 MB, para su validación.
</Callout>

<br />

#### Ver detalle de un prestador de servicio

Puedes consultar el detalle de cualquiera de los prestadores de servicio listados. Para hacerlo: 

1. Haz clic en el menú de tres puntos, ubicado al final de los campos descriptivos del prestador de servicio, es decir, hasta el lado derecho de la pantalla.  
2. Del menú desplegable, selecciona la opción **Ver**. 

<Image align="center" alt="Menú desplegable prestador de servicio" border={true} src="https://files.readme.io/58f43fd32b074ad71f0095e84c4b361379f72ecbc47fc3572b213dfa12fb190b-Ver_prestador_de_servicio.png" className="border" />

3. Serás redirigido a la página de detalle del prestador de servicio. Verás la información dividida en las categorías de: **Detalle del Prestador de Servicio**, **Datos de la cuenta del Prestador de Servicio**, **Contrato del Prestador de Servicio** y **Estado del registro**. 

<br />

#### Modificar los datos de un prestador de servicio

Puedes modificar los datos de cualquiera de los prestadores de servicio listados. Para hacerlo: 

Haz clic en el menú de tres puntos, ubicado al final de los campos descriptivos del prestador de servicio, es decir, hasta el lado derecho de la pantalla.  

Del menú desplegable, selecciona la opción **Modificar**. 

<Image align="center" alt="Botón desplegable modificar" border={true} src="https://files.readme.io/97c96fa1f6b47193de603231581c8d1b38681a256d82de5bd4a84679ef5d6771-Modificar_prestador_de_servicio.png" className="border" />

3. Serás redirigido a la página de detalle del prestador de servicio. Verás la información dividida en las categorías de: **Detalle del Prestador de Servicio**, **Datos de la cuenta del Prestador de Servicio**, **Contrato del Prestador de Servicio** y **Estado del registro**. 

<Callout icon="🚧" theme="warn">
  **Modificación de datos**

  Una vez creado el proveedor, solo podrás modificar los siguientes datos: **información de la cuenta bancaria **(**banco**, **titular**, **tipo de cuenta** y **número de cuenta**). El resto de datos no pueden ser modificados.
</Callout>

4. Al terminar de editar, haz clic en el botón superior derecho **Guardar cambios**. 

<br />

#### Filtros

El módulo de **Prestadores de servicio** cuenta con la opción de filtrar el listado. Esto facilita la localización rápida de colaboradores específicos. Puedes ver todas las opciones disponibles de filtrado haciendo clic en el botón superior derecho de **Filtros**. 

<Image align="center" alt="Filtros " border={true} width="30% " src="https://files.readme.io/d9c813ab534fe1352b4eec7c6a0adda6abf87220c807be645dd99cb15f3a6888-filtros_proveedores.png" className="border" />

<br />

#### Ordenar por campo

Otra manera de modificar cómo se ve la información de la tabla de **Prestadores de servicio**, es ordenándola por alguno de los campos descriptivos superiores. Para hacerlo: 

1. Haz clic en las flechas que se encuentran al lado de un campo específico. 

<Image align="center" alt="Ordenar por campo " border={true} src="https://files.readme.io/ce4151017397460fd7229df8df7c99c2f766f31782e3bf1e2c524db70eda35c6-Ordenar_por_campo_1.png" className="border" />

2. Se ordenarán de forma descendente, si la flecha está hacia abajo. 

<Image align="center" alt="Ordenar por campo descendente" border={true} src="https://files.readme.io/f7b8a1431566a221a8d90b1685882f4a2e5dffde88a8c934914d6c17584cb850-Ordenar_por_campo_2.png" className="border" />

3. Para cambiar el orden a ascendente, haz clic nuevamente en la flecha. 

<Image align="center" alt="Ordenar por campo ascendente" border={true} src="https://files.readme.io/38853a9729b9b67dc3905897239bc8f5d1b4b1d2bf8a62acec810e1415d74ea5-Ordenar_por_campo_3.png" className="border" />

***

<br />

### Generar Pay4U

En este módulo verás un listado de todos los pagos Pay4U realizados a tus proveedores, colaboradores y prestadores de servicio. Además, podrás crear pagos Pay4U masivos o individuales. 

El listado general del módulo podría verse similar al siguiente: 

<Image align="center" alt="Pay4U General" border={true} width="100% " src="https://files.readme.io/29fe7959b79457e04d617fa2337cf884d4e7c8dcf9d61526bf798c4ce115b19f-pay4u.png" className="border" />

A continuación, puedes consultar el diagrama de flujo para conocer el proceso de creación de pagos Pay4U:

<Image align="center" alt="Diagrama Pay4U" border={true} src="https://files.readme.io/d3e3f6aa49170ded42a306866451630149e6b2d13d3d2c596c2ce0c0bcaf0149-Pay4U_part2_1.png" className="border" />

<br />

#### Crear Pay4U masivo

Mediante la opción para pagos Pay4U masivos, **solo se podrán ejecutar pagos destinados a colaboradores** debido a que son transferencias recurrentes por un valor repetitivo que consta en el contrato, mientras que, para proveedores y prestadores de servicios, la frecuencia y los valores cambia, por lo que siempre será requerida una factura para cada transacción.

<Callout icon="🚧" theme="warn">
  **Remuneraciones hacia colaboradores**

  Los pagos de las remuneraciones se realizan el mismo día para todos los colaboradores.
</Callout>

Para crear un pago Pay4U masivo, sigue estos pasos: 

Haz clic en el botón ubicado en la parte superior derecha **+Crear Masivo**. 

<Image align="center" alt="Botón crear masivo" border={true} src="https://files.readme.io/0427d3a3ce42ccb553d2f7a1b0978515e6d9c51c5d09b52e79a803c67e9fd12a-Boton_crear_masivo.png" className="border" />

2. Serás redirigido a una nueva pestaña, en donde deberás seguir las instrucciones en pantalla para rellenar el formulario.

<Image align="center" alt="Formulario crear Pay4U masivo" border={true} width="80% " src="https://files.readme.io/b10ebaa1554027abdccdc4ef6d9720d63ecaa4271ae86885c822e7c57a7e320b-formulario_crear_pay4u_masivo.png" className="border" />

<Callout icon="❗️" theme="error">
  **Importante**

  Se cuentan con plantillas para ingresar manualmente la información de los colaboradores, pero no se recomienda debido a la complejidad del proceso. Al igual que en los archivos individuales de Pay4U, los destinatarios deben estar registrados en el país correspondiente al balance. Lo ideal es usar el archivo descargable desde el módulo de **Colaboradores** mencionado en este mismo artículo, ya que contiene la información precargada y minimiza errores.
</Callout>

3. Al terminar de llenar todos los campos, haz clic en el botón superior derecho **Guardar**.

<br />

#### Crear Pay4U individual

Para crear un pago Pay4u individual, sigue estos pasos:

Haz clic en el botón ubicado en la parte superior derecha **+Crear Individual**.

<Image align="center" alt="Botón crear individual" border={true} src="https://files.readme.io/a15123d187ff056e0654eb1ba9f2425610bdd092661ac6540fe0a38613e5a174-boton_crer_inividual.png" className="border" />

2. Serás redirigido a una nueva pestaña, en donde deberás llenar los campos del formulario.

<Image align="center" alt="Formulario crear Pay4U individual" border={true} width="80% " src="https://files.readme.io/7f380f761e345fb459e0f065b1bd52fc4200c9a77ceac572b7af7df4a63dc0e5-Formulario_crear_individual.png" className="border" />

3. Al terminar de llenar todos los campos, haz clic en el botón superior derecho **Guardar**, o, si así lo requieres, **Crear y añadir otro**.

<Callout icon="❗️" theme="error">
  **Importante**

  El destinatario seleccionado debe ser registrado en el país que corresponde al balance elegido.
</Callout>

<br />

#### Ver detalle de un Pay4U

Puedes consultar el detalle de cualquiera de los Pay4U listados. Para hacerlo: 

1. Haz clic en el menú de tres puntos, ubicado al final de los campos descriptivos del pago, es decir, hasta el lado derecho de la pantalla.  
2. Del menú desplegable, selecciona la opción **Ver**.

<Image align="center" alt="Botón desplegable ver detalle Pay4U" border={true} src="https://files.readme.io/f57fd75f6c75c4f8551fd1d1046f63f6c6d345f120a5cff2b3ad144016cbe1d2-Ver_detalle_Pay4U.png" className="border" />

3. Serás redirigido a la página de detalle del pago. Verás la información dividida en las categorías de: **Datos de la transacción**, **Información del pago**, **Retiros Asociados** y **Registro Histórico**. 

<br />

#### Modificar los datos de un Pay4U

Puedes modificar los datos de cualquiera de los Pay4U listados. Para hacerlo: 

1. Haz clic en el menú de tres puntos, ubicado al final de los campos descriptivos del pago, es decir, hasta el lado derecho de la pantalla.  
2. Del menú desplegable, selecciona la opción **Modificar**.

<Image align="center" alt="Botón desplegable ver detalle Pay4U" border={true} src="https://files.readme.io/f57fd75f6c75c4f8551fd1d1046f63f6c6d345f120a5cff2b3ad144016cbe1d2-Ver_detalle_Pay4U.png" className="border" />

3. Serás redirigido a la página editable de datos del Pay4U, en donde podrás hacer los ajustes necesarios. 
4. Al terminar de editar, haz clic en el botón superior derecho **Guardar cambios**.

<Callout icon="📘" theme="info">
  **Nota**

  Solo podrás modificar los datos de los Pay4U cuyo estado sea distinto a **Exitoso**. De lo contrario, solo podrás ver los detalles. 
</Callout>

<br />

#### Filtros

El módulo de Generar Pay4U cuenta con la opción de filtrar el listado. Esto facilita la localización rápida de pagos específicos. Puedes ver todas las opciones disponibles de filtrado haciendo clic en el botón superior derecho de **Filtros**.

<Image align="center" alt="Filtros Pay4U" border={true} width="30% " src="https://files.readme.io/e103ec60fee69706b5fcd32396ab78f08fe94ad61af5fa3dd45c5d6a147f6228-filtros_pay4U.png" className="border" />

<br />

#### Ordenar por campo

Otra manera de modificar cómo se ve la información de la tabla de **Generar Pay4U**, es ordenándola por alguno de los campos descriptivos superiores. Para hacerlo: 

1. Haz clic en las flechas que se encuentran al lado de un campo específico. 

<Image align="center" alt="Ordenar por campo " border={true} src="https://files.readme.io/ce4151017397460fd7229df8df7c99c2f766f31782e3bf1e2c524db70eda35c6-Ordenar_por_campo_1.png" className="border" />

2. Se ordenarán de forma descendente, si la flecha está hacia abajo. 

<Image align="center" alt="Ordenar por campo descendente" border={true} src="https://files.readme.io/f7b8a1431566a221a8d90b1685882f4a2e5dffde88a8c934914d6c17584cb850-Ordenar_por_campo_2.png" className="border" />

3. Para cambiar el orden a ascendente, haz clic nuevamente en la flecha. 

<Image align="center" alt="Ordenar por campo ascendente" border={true} src="https://files.readme.io/38853a9729b9b67dc3905897239bc8f5d1b4b1d2bf8a62acec810e1415d74ea5-Ordenar_por_campo_3.png" className="border" />
