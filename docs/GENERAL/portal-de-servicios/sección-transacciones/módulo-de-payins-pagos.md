---
title: Módulo de Payins (pagos)
deprecated: false
hidden: true
metadata:
  robots: index
---
## Payins (pagos)

En este módulo se muestra una tabla detallada con la información de todos los pagos registrados hasta el momento. La tabla incluye diversos campos descriptivos, como: número de referencia, nombre del comprador, número de identificación del comprador, tipo y método de pago, detalle del método de pago (en caso de ser necesario), comercio, monto, moneda, estado del pago, fecha de creación del pago, fecha de liberación del pago, liquidación automática y contracargo (en caso de haberse realizado).

<Image align="center" border={true} src="https://files.readme.io/4efe5410a963f759646623b2769609fffd63e8c5d40e97c7f64c36511aa22e0c-Panel_Payins.png" className="border" />

<br />

### Ver detalle de un pago

Puedes consultar el detalle de cualquiera de los pagos que aparecen en la tabla de **Payins (pagos)**. Para hacerlo:

1. Haz clic en el menú de tres puntos, ubicado al final de los campos descriptivos del pago, es decir, hasta el lado derecho de la pantalla.
2. Del menú desplegable, selecciona la opción **Ver**.

<Image align="center" alt="Botón Ver" border={true} src="https://files.readme.io/3cc90bd4ab76964957c0a7dea707d2a5b68536d88a1250cf0e72587c793c9c06-Boton_Ver_Modulo_Payins.png" className="border" />

3. Serás redirigido a la página de detalle del pago. Verás la información dividida en las categorías de: **Identificación**, **Datos del usuario**, **Datos de pago**, **Datos Adicionales** y **Autenticación y evaluación de riesgo**.

<Image align="center" alt="Detalles de pago" border={true} width="75% " src="https://files.readme.io/294e75e39d65c60b15c56fa7c2a191ffb52a9336d49fe94f224931f5f7d05159-Detalles_de_pago.png" className="border" />

<br />

### Ver datos completos

Una vez dentro de la página de detalle de un pago, podrás acceder a los **Datos Completos**, en donde verás toda la información del pago en formato JSON. Para ello, haz clic en el botón superior derecho de **Datos Completos**.

<Image align="center" alt="Datos completos" border={true} src="https://files.readme.io/1ec3ad016f88e953570eae5a4707c8f593001cda234fcde6f7633963734e1fca-Datos_completos.png" className="border" />

<br />

### Reembolsar un pago

Desde el módulo de pagos podrás reembolsar un pago específico. Para hacerlo:

1. Identifica en el listado de pagos el pago que deseas reembolsar.
2. Haz clic en el menú de tres puntos, ubicado al final de los campos descriptivos del pago, es decir, hasta el lado derecho de la pantalla.
3. Selecciona la opción de **Reembolso**.

<Image align="center" alt="Botón reembolso" border={true} src="https://files.readme.io/6200c670675a06b09c36db749e858a284490d387c384d6d35f85537bdd275ffc-Boton_Reembolso.png" className="border" />

<Callout icon="📘" theme="info">
  **Nota**

  Solo verás la opción de **Reembolso** en este menú, en pagos con estado “exitoso”.
</Callout>

4. Al hacer clic en **Reembolso**, serás redirigido a una página con el detalle del pago recién reembolsado. Ahí verás la información general, así como un mensaje de éxito en la parte superior de la pantalla.

<Image align="center" alt="Mensaje de devolución" border={true} width="40% " src="https://files.readme.io/b5e78d341f8174750e32c472e21e9dd710a03b042947a90975d3abcbe94577ed-devolucion_mensaje.png" className="border" />

<br />

### Filtros

El módulo de **Pagos** también cuenta con la opción de filtrar el listado. Esto facilita la localización rápida de pagos específicos. Puedes ver todas las opciones disponibles de filtrado haciendo clic en el botón superior de **Filtros**.

<Image align="center" alt="Filtros de Payins" border={true} width="30% " src="https://files.readme.io/67e4bb2024e1cad987aa7f20f4f7e1a05c5c7487e8264f1289d698f1f5c0fc85-filtros_de_payins.png" className="border" />

<br />

### Ordenar por campo

Otra manera de modificar cómo se ve la información de la tabla de **Pagos**, es ordenándola por alguno de los campos descriptivos superiores. Para hacerlo:

1. Haz clic en las flechas que se encuentran al lado de un campo específico.

<Image align="center" alt="Campo Monto 1" border={true} src="https://files.readme.io/2a712aec5a1c828e8cc00650445199cd4dc66a206af02e976cd6c49299431751-Monton_1.png" className="border" />

2. Se ordenarán de forma descendente, si la flecha está hacia abajo.

<Image align="center" alt="Campo Monto 2" border={true} width="15% " src="https://files.readme.io/b68e51bc94bd35817d1dd2a818e0662e7ff73862d6003cd1c9e851064775a165-Monto_2.png" className="border" />

3. Para cambiar el orden a ascendente, haz clic nuevamente en la flecha.

<Image align="center" alt="Campo Monto 3" border={true} width="16% " src="https://files.readme.io/861dcf61f543eee67c8d95ebd89eb032fd37d14ecd64425ad8c5cbd778c813af-Monto_3.png" className="border" />
