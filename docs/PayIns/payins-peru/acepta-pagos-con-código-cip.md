---
title: Acepta pagos con código CIP
excerpt: 'Conoce el paso a paso de cómo crear un pago con código CIP en Perú. '
deprecated: false
hidden: true
metadata:
  robots: index
---
Crear un pago con esta modalidad consiste en hacer una solicitud para crear un **código CIP** a través de nuestra API. Esta solicitud podrá realizarse tanto para la versión web como para la versión _mobile_. Una vez realizada con éxito, el cliente podrá realizar sus pagos ingresando el código CIP en diferentes plataformas integradas del **BCP (Banco de Crédito del Perú)** sin necesidad de usar tarjeta bancaria.

<Callout icon="👍" theme="okay">
  **CIP**

  El **Código de Identificación de Pago único (CIP)** es generado por ProntoPaga y vincula una operación específica con el usuario.
</Callout>

***

## ¿Cómo funciona?

BCP es un banco que opera en Perú y permite realizar pagos de cargos, cuotas o consumos mediante código CIP en sus distintas plataformas digitales. Para completar un pago con cualquiera de estas plataformas, el usuario debe seleccionar la opción:

* Yape
* VíaBCP (banca por internet)
* Telecrédito web BCP (banca negocios)
* Banca Móvil BCP (_app_)

El proceso de pago con código CIP en Perú consta de cuatro etapas principales:

1. **Selección de método.** El cliente elige pagar vía banca por internet/móvil en tu sitio web o aplicación.
2. **Solicitud.** ProntoPaga genera el **código CIP** y muestra al cliente los datos para realizar el pago.
3. **Cuenta**. El cliente inicia sesión en su plataforma elegida para realizar el pago. La siguiente parte del flujo varía según el canal que elija el cliente:

<Cards columns={4}>
  <Card title="📱 En Yape:">
    El usuario abre su app Yape y elige la opción Yapear servicios. En el buscador ingresa ProntoPaga y luego digita el código CIP para completar la transacción.
  </Card>

  <Card title="📱En App Banca móvil BCP:">
    El usuario inicia sesión en su app Banca móvil BCP y selecciona la opción Pagar servicios. En el buscador ingresa ProntoPaga y digita el número de código CIP para finalizar la transacción.
  </Card>

  <Card title="💻 En VíaBCP Banca por internet">
    El usuario ingresa a su banca por internet del BCP y selecciona la opción Pagar servicios. En el buscador ingresa ProntoPaga y digita el número de código CIP otorgado para continuar la transacción.
  </Card>

  <Card title="🌐 En Telecrédito web BCP">
    El usuario inicia sesión en Telecrédito web y selecciona la opción Pagar servicios. En el buscador ingresa ProntoPaga y luego digita el código CIP asignado para completar la transacción.
  </Card>
</Cards>

4. **Pago**. El monto se recaudará directamente de la cuenta BCP del cliente.

<br />
