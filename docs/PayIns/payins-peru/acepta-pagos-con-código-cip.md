---
title: Acepta pagos con código CIP
excerpt: 'Conoce el paso a paso de cómo crear un pago con código CIP en Perú. '
deprecated: false
hidden: true
metadata:
  robots: index
---
Crear un pago con esta modalidad consiste en hacer una solicitud para crear un **código CIP** a través de nuestra API. Esta solicitud podrá realizarse tanto para la versión web como para la versión _mobile_. Una vez realizada con éxito, el cliente podrá realizar sus pagos ingresando el código CIP en diferentes plataformas integradas del BCP (Banco de Crédito del Perú) sin necesidad de usar tarjeta bancaria. 

<Callout icon="👍" theme="okay">
  **CIP**

  El **Código de Identificación de Pago único (CIP)** es generado por ProntoPaga y vincula una operación específica con el usuario.
</Callout>

***

## ¿Cómo funciona?

BCP es un banco que opera en Perú y permite realizar pagos de cargos, cuotas o consumos mediante código CIP en sus distintas plataformas digitales. Para completar un pago con cualquiera de estas plataformas, el usuario debe seleccionar la opción:

* Yape
* VíaBCP (banca por internet)
* Telecrédito (banca negocios)
* Banca Móvil BCP (_app_)

El monto se recaudará directamente de la cuenta BCP del cliente. 

El proceso de pago con código CIP en Perú consta de cuatro etapas principales:

1. **Selección de método.** El cliente elige pagar vía banca por internet/móvil en tu sitio web o aplicación.
2. **Solicitud.** ProntoPaga genera el **código CIP** y muestra al cliente los datos para realizar el pago.
3. **Cuenta**. El cliente inicia sesión en su plataforma elegida para realizar el pago. La siguiente parte del flujo varía según el canal que elija el cliente:

<br />

<Cards columns={4}>
  <Card title="**🌐 En Yape:**">
    Se genera un código QR para que el cliente lo escanee desde la apliación de su celular.
  </Card>

  <Card title="**📱En App Banca móvil BCP:**">
    La opción de pago con wallet abre la aplicación del cliente y se valida la identidad para confirmar el pago.
  </Card>

  <Card title="🌐 En web">
    Se genera un código QR para que el cliente lo escanee desde la apliación de su celular.
  </Card>

  <Card title="🌐 En web">
    Se genera un código QR para que el cliente lo escanee desde la apliación de su celular.
  </Card>
</Cards>

<br />

**📱En App Banca  BCP:**

**🖥️ En Banca por internet:**

<Cards columns={1}>
  <Card title="Si se tiene desactivado el servicio de validación pago de terceros">
    El cliente debe hacer clic en el botón **Solicitar aprobación**. Luego, será redirigido a la aplicación de Yape mediante un deeplink dinámico generado a demanda, el cual estará activo por 15 minutos.

    Después de ingresar su clave de acceso, aparecerá un modal en la pantalla, donde podrá aprobar la afiliación directamente.
  </Card>
</Cards>

**🖥️ En telecrédito web:**

<Cards columns={1}>
  <Card title="Si se tiene desactivado el servicio de validación pago de terceros">
    El cliente debe hacer clic en el botón **Solicitar aprobación**. Luego, será redirigido a la aplicación de Yape mediante un deeplink dinámico generado a demanda, el cual estará activo por 15 minutos.

    Después de ingresar su clave de acceso, aparecerá un modal en la pantalla, donde podrá aprobar la afiliación directamente.
  </Card>
</Cards>

<br />

<br />

<br />

<br />

en la opción de **Pagar servicios**, busca **ProntoPaga** e ingresa el código CIP. El dinero se mueve desde la cuenta del cliente hacia la cuenta de tu comercio.

1. **Confirmación**. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.
