---
title: Acepta pagos con código CIP
excerpt: 'Conoce el paso a paso de cómo crear un pago con código CIP en Perú. '
deprecated: false
hidden: true
metadata:
  robots: index
---
Crear un pago con esta modalidad consiste en hacer una solicitud para crear un **código CIP** a través de nuestra API. Esta solicitud podrá realizarse tanto para versión web como para versión mobile. Una vez realizada con éxito, el cliente podrá realizar sus pagos ingresando el código CIP en diferentes plataformas integradas sin necesidad de usar tarjeta.

El monto se recauda directamente desde la cuenta BCP asociada a:

* Yape
* VíaBCP (banca por internet)
* Telecrédito (banca negocios)
* Banca Móvil BCP (_app_)

<Callout icon="👍" theme="okay">
  **CIP**

  El **Código de Identificación de Pago único (CIP)** es generado por ProntoPaga y vincula una operación específica con el usuario.
</Callout>

***

## ¿Cómo funciona?

Payphone es una billetera digital ecuatoriana que permite recibir pagos, administrar dinero y realizar transacciones desde el celular. Para completar una transacción utilizando este método de pago, el cliente debe seleccionar "Paga con QR/Wallet - Payphone", tener la aplicación instalada en su dispositivo móvil, una cuenta creada con saldo disponible o un medio de pago vinculado, y aprobar el pago desde la aplicación.

El proceso de pago con código CIP en Perú consta de cuatro etapas principales:

1. **Selección de método.** El cliente elige pagar vía banca por internet/móvil en tu sitio web o aplicación.
2. **Solicitud.** ProntoPaga genera el **código CIP** y muestra al cliente los datos para realizar el pago.
3. **Cuenta**. El cliente inicia sesión en su plataforma elegida para realizar el pago. La siguiente parte del flujo varía según el canal que elija el cliente:

**🌐 En Yape:**

<Cards columns={4}>
  <Card title="Si se tiene desactivado el servicio de validación pago de terceros">
    Se le pide al cliente ingresar su número de celular para solicitar el pago. Luego, se le muestra en pantalla un instructivo para abrir su aplicación y aprobar el pago en la sección de **Aprobar compras**.
  </Card>
</Cards>

**📱En App Banca móvil BCP:**

<Cards columns={1}>
  <Card title="Si se tiene desactivado el servicio de validación pago de terceros">
    El cliente debe hacer clic en el botón **Solicitar aprobación**. Luego, será redirigido a la aplicación de Yape mediante un deeplink dinámico generado a demanda, el cual estará activo por 15 minutos.

    Después de ingresar su clave de acceso, aparecerá un modal en la pantalla, donde podrá aprobar la afiliación directamente.
  </Card>
</Cards>

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

1. en la opción de **Pagar servicios**, busca **ProntoPaga** e ingresa el código CIP. El dinero se mueve desde la cuenta del cliente hacia la cuenta de tu comercio.
2. **Confirmación**. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.
