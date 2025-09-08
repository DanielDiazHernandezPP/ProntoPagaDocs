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

&#x20;     En el sector de pagos, gracias a las APIs puedes generar operaciones como crear un cobro, consultar el estado de una transacción, iniciar un reembolso o programar un payout.

&#x20;     Se basa en estándares como JSON sobre HTTPS, lo que asegura interoperabilidad entre distintas plataformas.
&#x20; \</Tab>

&#x20; \<Tab title="B">
&#x20;   \* \*\*Balance disponible:\*\* Es el monto que realmente está listo para ser retirado por el comercio en ese momento. Se calcula restando al saldo neto el saldo diferido y el bloqueado. Representa la liquidez inmediata del comercio.
&#x20;   \* \*\*Back-end:\*\* La capa del servidor que procesa la lógica de negocio y comunica el sistema del comercio con ProntoPaga.&#x20;
&#x20;  &#x20;
&#x9;		Aquí se validan los webhooks, se gestionan las llaves secretas, se almacenan órdenes y se realiza la conciliación financiera. Es la parte “invisible” para el cliente final, pero crítica para la seguridad y el flujo de pagos.
\* \*\*Bearer Token:\*\* Es un tipo de credencial de seguridad utilizado en APIs. El cliente incluye este token para demostrar que tiene permiso de acceder al recurso solicitado.

&#x20;     A este tipo de credenciales sueles llamárseles “al portador”, pues quien posea el token puede usarlo sin restricciones, por lo que deben mantenerse en secreto y transmitirse únicamente por conexiones seguras (HTTPS).

&#x20;     Suelen tener caducidad alcances definidos, limitando qué operaciones puede ejecutar.
&#x20; \</Tab>

&#x20; \<Tab title="C">
&#x20;   \* \*\*Certificación:\*\* Proceso formal en donde se valida que una integración cumple todos los requisitos técnicos y de seguridad antes de pasar a producción.

&#x20;     En muchos casos, esto incluye que se ejecuten casos de prueba (éxito, error, contracargo, etc.) y documentar resultados. Una vez aprobado, se otorgan credenciales de producción.
&#x20;   \* \*\*Changelog:\*\* Se trata de un registro cronológico de cambios en la API y la plataforma: nuevas funcionalidades, endpoints deprecados, mejoras de seguridad.

&#x20;     Si quieres conocer más acerca de los cambios que se han hecho en ProntoPaga, visita nuestra pestaña de Changelog.
&#x20;   \* \*\*Checkout:\*\* Es Interfaz lista para usar  que verán tus clientes finales para simplificar cobros. Puede ser una página redirigida o un modal embebido. Incluye métodos de pago, validaciones antifraude y cumplimiento PCI.
&#x20;  &#x20;
&#x9;		Reduce tiempo de integración y garantiza que la experiencia cumpla los estándares de calidad necesarios.
&#x20;   \* \*\*Cybersource\*\*
&#x20; \</Tab>

&#x20; \<Tab title="First Tab">
&#x20;   Welcome to the content that you can only see inside the first Tab.
&#x20; \</Tab>

&#x20; \<Tab title="Second Tab">
&#x20;   Here's content that's only inside the second Tab.
&#x20; \</Tab>

&#x20; \<Tab title="Third Tab">
&#x20;   Here's content that's only inside the third Tab.
&#x20; \</Tab>

&#x20; \<Tab title="First Tab">
&#x20;   Welcome to the content that you can only see inside the first Tab.
&#x20; \</Tab>

&#x20; \<Tab title="Second Tab">
&#x20;   Here's content that's only inside the second Tab.
&#x20; \</Tab>

&#x20; \<Tab title="Third Tab">
&#x20;   Here's content that's only inside the third Tab.
&#x20; \</Tab>

&#x20; \<Tab title="First Tab">
&#x20;   Welcome to the content that you can only see inside the first Tab.
&#x20; \</Tab>

&#x20; \<Tab title="Second Tab">
&#x20;   Here's content that's only inside the second Tab.
&#x20; \</Tab>

&#x20; \<Tab title="Third Tab">
&#x20;   Here's content that's only inside the third Tab.
&#x20; \</Tab>
\</Tabs>

<br />

<br />

<br />

<br />

\<Tabs>
\<Tab title="A">

* **API:** Conjunto de reglas, protocolos y endpoints que permiten que tu sistema de software se comunique con otro.

```
```

```
```

\<Tab title="B">

* **Balance disponible:** Es el monto que realmente está listo para ser retirado por el comercio en ese momento. Se calcula restando al saldo neto el saldo diferido y el bloqueado. Representa la liquidez inmediata del comercio.
* **Bearer Token** Es un tipo de credencial de seguridad utilizado en APIs. El cliente incluye este token para demostrar que tiene permiso de acceder al recurso solicitado.

```
```

```
```

\<Tab title="C">

* **Changelog:** Se trata de un registro cronológico de cambios en la API y la plataforma: nuevas funcionalidades, endpoints deprecados, mejoras de seguridad.

```
```

\</Tab>
\<tab title="D">

* **Desicion Manager (DM):**
  \</Tabs>

\<Tab title="C">

* **Changelog:**
* **Checkout:**
* **Cybersource (A Visa Solution):**
  \</Tab>

\<Tab title="D">

* **Decisión Manager (DM:**
* **Demo:**
  \</Tab>
  \<Tab title="E">
* **Endpoint:**
* **Enviroments:** Se trata de espacios aislados en los que se ejecutan las pruebas y operaciones de pago. Los ambientes usados por ProntoPaga son

\<Tab title="F">

* **Firma:**
* **Front-end:**
  \</Tab>

\<Tab title="I">

* **iFrame:**

\<Tab title="P">

* **Parámetros:**
* **PayIns:**
* **PayOuts:**
* **Pendiente por Retiro:** Saldo en retiros pendientes.
* **Plugins:**
  \</Tab>

\<Tab title="Q">

* **QR:**
  \</Tab>

\<Tab title="S">

* **Saldo bloqueado:** Saldo bloqueado por procesos de contracargos.
* **Saldo Diferido:** Saldo a la espera de cumplir el tiempo necesario para estar disponible.
* **Saldo Neto:** Saldo total del comercio, contando el saldo ya disponible para retiro y el saldo diferido.
* **Sandbox:**
* **SecretKey:**
  \</Tab>

\<Tab title="W">

* **Wallet:**
* **Weebhok:** Medio de automatización de respuesta ante un evento específico.
  \</Tab>
  \</Tabs>

<br />

<br />
