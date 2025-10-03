---
title: Módulo Pay4U
deprecated: false
hidden: true
metadata:
  robots: index
---
## Pay4U

En esta carpeta podrás consultar todo lo referente a nuestro servicio de pagos Pay4u. Además del módulo específico de **Pagos Pay4u**, esta carpeta cuenta también con módulos para los listados de **Proveedores**, **Colaboradores** y **Prestadores de Servicio**.

A continuación, puedes consultar el diagrama de flujo para conocer el proceso de configuración de destinatarios:

<Image align="center" alt="Diagrama General Pay4U" border={true} src="https://files.readme.io/f2e1fb157731061c64a6a1848f492cfa710be28837950b696eccf6f7333a392b-Pay4U_part1.png" className="border" />

<br />

### Proveedores

La categoría de **Proveedores** es generalmente utilizada para asociados a los que se les debe realizar pagos frecuentes o recurrentes.

Este módulo te permite crear un nuevo proveedor, así como consultar el listado de todos los proveedores que tienes registrados. Además, puedes ver sus datos, modificarlos, así como descargar el contrato de cada uno (cargado durante la creación de un proveedor).

El módulo con el listado de proveedores puede verse similar al siguiente:

<Image align="center" alt="Categoría proveedores" border={true} src="https://files.readme.io/bd33dad5f83fd898a7ea34291ea33d45ef8214f19ee53d3b1bc0cdd74d2f3d48-proveedores.png" className="border" />

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

<Callout icon="📘" theme="info">
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

<Image align="center" alt="Colaboradores" border={true} src="https://files.readme.io/c2773ec5c2c69604b2684822784d4b4ed46314e55fe0fa6ebf5345bf7e75a331-Colaboradores_modulo.png" className="border" />

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

<Callout icon="📘" theme="info">
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

<br />
