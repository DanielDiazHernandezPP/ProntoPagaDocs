---
title: Glosario
excerpt: Conoce los términos de la industria de pagos dentro de esta documentación.
deprecated: false
hidden: true
metadata:
  robots: index
---
\<Tabs>
&#x20; \<Tab title="A">
&#x20;   \* \*\*API:\*\* Conjunto de reglas, protocolos y endpoints que permiten que tu sistema de software se comunique con otro.

&#x20;     En el sector de pagos, gracias a las APIs puedes generar operaciones como \*\*crear un cobro\*\*, \*\*consultar el estado de una transacción\*\*, \*\*iniciar un reembolso\*\* o \*\*programar un payout\*\*.

&#x20;     Las APIs se basan en estándares como JSON sobre HTTPS, lo que asegura interoperabilidad entre distintas plataformas.
&#x20; \</Tab>

&#x20; \<Tab title="B">
&#x20;   \* \*\*Balance Disponible:\*\* Saldo disponible para retiro. Es el resultado del saldo neto menos el saldo diferido.
&#x20;   \* \*\*Bearer Token:\*\* Es un tipo de credencial de seguridad utilizado en APIs. El cliente incluye este token en la cabecera \*\*Authorization: Bearer \<token>\*\* para demostrar que tiene permiso de acceder al recurso solicitado.&#x20;
&#x20;  &#x20;
&#x9;			A este tipo de credenciales también se les llama “al portador”, pues quien posea el token puede usarlo sin restricciones, por lo que deben mantenerse en secreto y transmitirse únicamente por conexiones seguras (HTTPS).&#x20;

&#x20;   Suelen tener caducidad alcances definidos, limitando qué operaciones puede ejecutar.

&#x20;   \* \*\*Body:\*\*
&#x20; \</Tab>

&#x20; \<Tab title="C">
&#x20;   \* \*\*Changelog:\*\*
&#x20;   \* \*\*Checkout:\*\*
&#x20;   \* \*\*Cybersource (A Visa Solution):\*\*
&#x20; \</Tab>

&#x20; \<Tab title="D">
&#x20;   \* \*\*Decisión Manager (DM:\*\*
&#x20;   \* \*\*Demo:\*\*
&#x20; \</Tab>

&#x20; \<Tab title="E">
&#x20;   \* \*\*Endpoint:\*\*
&#x20;   \* \*\*Enviroments:\*\* Se trata de espacios aislados en los que se ejecutan las pruebas y operaciones de pago. Los ambientes usados por ProntoPaga son:

&#x20;     \* Sandbox, donde se simulan transacciones sin dinero real.
&#x20;     \* Producción, donde fluyen los pagos reales.

&#x20;   Estos entornos suelen usar credenciales diferentes (como tu Bearer Token y secretKey dentro de ProntoPaga) y URLs separadas para evitar mezclar datos, permitiendo a los comercios desarrollar y probar flujos de pago completos antes de arriesgar dinero o exponer información sensible de clientes.
&#x20; \</Tab>

&#x20; \<Tab title="F">
&#x20;   \* \*\*Firma:\*\*
&#x20;   \* \*\*Front-end:\*\*
&#x20; \</Tab>

&#x20; \<Tab title="I">
&#x20;   \* \*\*iFrame:\*\*

&#x20;   \* \*\*Integración:\*\* Proceso de conectar tu aplicación, página web o sistema interno con un procesador de pagos o una orquestadora. Puede hacerse de distintas formas:

&#x20;     \* APIs directas.

&#x20;     \* SDKs (kits de desarrollo).

&#x20;     \* iFrames que embeben formularios seguros.

&#x20;     \* Plugins ya listos para plataformas de e-commerce.

&#x20;     Una integración no solo habilita procesar cobros, sino también administrar contracargos, verificar identidades, emitir reembolsos y reconciliar balances. Todas estar características están presentes en ProntoPaga.
&#x20; \</Tab>

&#x20; \<Tab title="P">
&#x20;   \* \*\*Parámetros:\*\*
&#x20;   \* \*\*PayIns:\*\*
&#x20;   \* \*\*PayOuts:\*\*
&#x20;   \* \*\*Pendiente por Retiro:\*\* Saldo en retiros pendientes.
&#x20;   \* \*\*Plugins:\*\*
&#x20; \</Tab>

&#x20; \<Tab title="Q">
&#x20;   \* \*\*QR:\*\*
&#x20; \</Tab>

&#x20; \<Tab title="S">
&#x20;   \* \*\*Saldo bloqueado:\*\* Saldo bloqueado por procesos de contracargos.
&#x20;   \* \*\*Saldo Diferido:\*\* Saldo a la espera de cumplir el tiempo necesario para estar disponible.
&#x20;   \* \*\*Saldo Neto:\*\* Saldo total del comercio, contando el saldo ya disponible para retiro y el saldo diferido.
&#x20;   \* \*\*Sandbox:\*\*
&#x20;   \* \*\*SecretKey:\*\*
&#x20; \</Tab>

&#x20; \<Tab title="W">
&#x20;   \* \*\*Wallet:\*\*
&#x20;   \* \*\*Weebhok:\*\* Medio de automatización de respuesta ante un evento específico.
&#x20; \</Tab>
\</Tabs>

<br />

<br />
