---
title: Glosario de pagos digitales
excerpt: Conoce los términos de la industria de pagos dentro de nuestra documentación
deprecated: false
hidden: false
metadata:
  title: Glosario de pagos digitales | ProntoPaga Docs
  description: >-
    Learn about the definitions most commonly used by ProntoPaga within the
    payments sector.
  image: >-
    https://files.readme.io/5b893b6158e8ce07ba46d6d15bfd84e3c373f6cf4371fb0fc173bdd3545994b6-Prontopaga_Logotipo.JPG
  keywords:
    - Glosario ProntoPaga
    - Definiciones ProntoPaga
    - Términos ProntoPaga
  robots: index
---
<Tabs>
  <Tab title="A">
    **<h3>Adobe Commerce (antes Magento)</h3>** Adobe Commerce es la evolución comercial de un sistema de código abierto Magento. Permite crear e-commerce medianas y grandes con gran flexibilidad, gestionar un catálogo, inventario, envíos, etc. La integración con Prontopaga a través de un plugin facilita el checkout, tokenización y el flujo completo de pago dentro del e-commerce.

    Conoce más acerca de este plugin en el siguiente [artículo](https://docs.prontopaga.com/docs/magento#/).

    **<h3>Afiliación</h3>** Autorización del método de pago por parte de un usuario para que pueda ser utilizado de forma recurrente sin necesidad de ingresar sus credenciales nuevamente. En la [integración de ProntoPaga con Yape](https://docs.prontopaga.com/docs/yape-on-file-recurrent#/), la afiliación permite al cliente registrar su cuenta Yape una vez, y luego la plataforma hace los cobros recurrentes de forma automática.

    Este método es muy útil en comercios que usan modelos de suscripción, reduciendo la fricción de UX y mejorando la experiencia de usuario.

    **<h3>API</h3>** Conjunto de reglas, protocolos y endpoints que permiten que tu sistema de software se comunique con otro. En el sector de pagos, gracias a las APIs puedes generar operaciones como crear un cobro, consultar el estado de una transacción, iniciar un reembolso o programar un payout.

    Se basa en estándares como JSON sobre HTTPS, lo que asegura interoperabilidad entre distintas plataformas.
  </Tab>

  <Tab title="B">
    **<h3>Back-end</h3>** La capa del servidor que procesa la lógica de negocio y comunica el sistema del comercio con ProntoPaga.

    Aquí se validan los webhooks, se gestionan las llaves secretas, se almacenan órdenes y se realiza la conciliación financiera. Es la parte “invisible” para el cliente final, pero crítica para la seguridad y el flujo de pagos.

    **<h3>Balance Disponible</h3>** Es el monto que realmente está listo para ser retirado por el comercio en ese momento. Se calcula restando al saldo neto el saldo diferido y el bloqueado. Representa la liquidez inmediata del comercio.

    **<h3>Balance (Wallet empresarial)</h3>**
    Billetera empresarial que muestra el balance total de tu comercio. Esto incluye saldos disponibles, diferidos y retenidos. Proporciona una visión completa de los montos disponibles en la Consola de Prontopaga. Para saber más, visita nuestro [artículo](https://docs.prontopaga.com/docs/balance-wallet#/).

    **<h3>Bearer Token</h3>** Es un tipo de credencial de seguridad utilizado en APIs. El cliente incluye este token para demostrar que tiene permiso de acceder al recurso solicitado.

    A este tipo de credenciales suele llamárseles “al portador”, pues quien posea el token puede usarlo sin restricciones, por lo que deben mantenerse en secreto y transmitirse únicamente por conexiones seguras (HTTPS).

    Suelen tener caducidad alcances definidos, limitando qué operaciones puede ejecutar.

    **<h3>BeMovil</h3>** Plataforma ecuatoriana que permite realizar retiros de dinero en efectivo mediante una amplia red de puntos físicos autorizados. Funciona como un método alternativo para usuarios que no cuenta con cuenta bancaria. Es ideal para retiros rápidos sin depender del sistema bancario tradicional.

    Conoce más acerca de este método de PayOut, visita nuestro [artículo](https://docs.prontopaga.com/docs/payouts-ecuador-cash#/).

    **<h3>Body</h3>** Parte del mensaje HTTP que contiene los datos que envías en una petición (request) POST, PUT o GET. Normalmente va en formato JSON e incluye parámetros como monto, moneda, país o método de pago.

    Los parámetros del body pueden ser de un tipo de dato distinto, como String, Number o Boolean. Toda la información que necesitas para crear tu petición, puedes encontarla en nuestra sección de API Reference.

    Al momento de crearlos, debes asegurarte de que todos los parámetros estén incluidos dentro de su estructura para que la API procese la transacción.
  </Tab>

  <Tab title="C">
    **<h3>CCI</h3>** iglas de Código de Cuenta Interbancario utilizado en Perú. Se trata de un número único asignado a una cuenta bancaria que permite identificarla para transferencias. Para realizar un PayOut (retiro) instantáneo, el cliente debe ingresar los datos necesarios, en los que se incluye el CCI. Conoce más acerca de cómo funciona este método de retiro en el siguiente [artículo](https://docs.prontopaga.com/docs/instant-payouts#/).

		**<h3>Certificación</h3>** Proceso formal en donde se valida que una integración cumple todos los requisitos técnicos y de seguridad antes de pasar a producción. En muchos casos, esto incluye que se ejecuten casos de prueba (éxito, error, contracargo, etc.) y documentar resultados. Una vez aprobado, se otorgan credenciales de producción.

    **<h3>Changelog</h3>** Se trata de un registro cronológico de cambios en la API y la plataforma: nuevas funcionalidades, endpoints deprecados, mejoras de seguridad.

    Si quieres conocer más acerca de los cambios que se han hecho en ProntoPaga, visita nuestra [pestaña de Changelog](https://docs.prontopaga.com/changelog#/).

    **<h3>Checkout</h3>** Es la interfaz lista para usarse que verán tus clientes finales para simplificar cobros. Puede ser una página redirigida o un modal embebido. Incluye métodos de pago, validaciones antifraude y cumplimiento PCI.

    Reduce tiempo de integración y garantiza que la experiencia cumpla los estándares de calidad necesarios.
    
		**<h3>Códigos bancarios </h3>** Identificadores usados para determinar qué banco y a qué tipo de cuenta se envía un pago. Estos deben incluirse dentro del parámetro bankcode del body request al crear un nuevo [PayIn (pago)](https://docs.prontopaga.com/docs/c%C3%B3digos-bancarios-para-payins-con-transferencia#/) o [PayOut (retiro)](https://docs.prontopaga.com/docs/bank-codes-transfer#/).  

Cada país cuenta con sus propios códigos bancarios. 

    **<h3>Código del país (ISO 3166-1 alpha-2)</h3>**
    Código estándar de dos letras para identificar países (por ejemplo: AR, BR y CL). Conoce más acerca de los códigos usados en ProntoPaga en el siguiente [artículo](https://docs.prontopaga.com/docs/countries-currencies-accounts#/).

    **<h3>Código de moneda (ISO 4217)</h3>**
    Código estándar de tres letras para identificar monedas (Por ejemplo: ARS, BRL y CLP). Conoce más acerca de los códigos usados en ProntoPaga en el siguiente [artículo](https://docs.prontopaga.com/docs/countries-currencies-accounts#/).

    **<h3>Colección de Postman</h3>** Archivo estructurado (generalmente en formato JSON) que agrupa un conjunto de peticiones a una API. Permite a desarrolladores probar, documentar y compartir endpoints de forma organizada. En el caso de ProntoPaga, nuestra colección de Postman incluye ejemplos listos de endpoints (crear un PayIn, consultar balances, iniciar un PayOut, etc.), con parámetros y credenciales de prueba, facilitando la integración y validación de flujos de pago sin necesidad de escribir código desde cero.

    Conoce más acerca en el siguiente [artículo](https://docs.prontopaga.com/reference/postman#/).

    **<h3>Cybersource</h3>** Es una plataforma de procesamiento de pagos y gestión de fraude adquirida por Visa en 2010. Ofrece servicios de gateway, prevención de fraude, tokenización y orquestación global de medios de pago. Está orientada a comercios grandes y empresas multinacionales, con alcance en más de 190 países.
  </Tab>

  <Tab title="D">
    **<h3>Dashboard</h3>** El Portal de servicios de ProntoPaga contiene un resumen en tiempo real de las transacciones de tu comercio, que incluye información como el monto en depósitos, monto en retiros o los principales métodos de pago, así como filtros por fecha, moneda y comercio. Conoce más sobre el módulo Dashboard en el siguiente [artículo](https://docs.prontopaga.com/docs/m%C3%B3dulo-dashboard#/).   
    
		**<h3>Datos de prueba</h3>** Credenciales, tarjetas o cuentas bancarias que permiten realizar simulaciones de flujos de PayIns (pagos) o PayOuts (retiro) sin necesidad de mover dinero real. En ProntoPaga, los datos de prueba son utilizados en el ambiente Sandbox. 

Conoce los datos de prueba de [PayIns (pagos)](https://docs.prontopaga.com/docs/test-data#/) o [PayOuts (retiro)](https://docs.prontopaga.com/docs/test-data-payouts#/) en sus artículos correspondientes. 
    
	**<h3>Decision Manager (DM)</h3>** Herramienta de prevención de fraude desarrollada por Cybersource (Visa). Funciona como un motor que evalúa cada transacción en tiempo real, aplicando reglas configurables y modelos de machine learning. Permite simular políticas con escenario, ajustar la tolerancia al riesgo y maximizar la tasa de aprobación reduciendo falsos positivos.

    **<h3>Demo</h3>** Aplicación o entorno de demostración que simula el flujo de pago real. Permite a comercios y desarrolladores visualizar la experiencia completa que verá el cliente final sin necesidad de escribir código. Suele acompañarse de ejemplos de credenciales y tarjetas de prueba.

    Puedes encontrar nuestras demos de [PayIns](https://docs.prontopaga.com/docs/payins-overview#/) o [PayOuts](https://www.figma.com/proto/sR8GayinfgLhXyMxlKjNJI/Demos-PayOuts-Prontopaga?page-id=11830%3A66971\&node-id=11830-66973\&viewport=1195%2C172%2C0.04\&t=ALYxaSbw4N7OP646-1\&scaling=scale-down\&content-scaling=fixed\&starting-point-node-id=11830%3A66973) en los enlace correspondientes.
  </Tab>

  <Tab title="E">
    **<h3>Efectivo</h3>** Dentro de ProntoPaga, es un método de pago donde el usuario usa efectivo para realizar su pago en puntos físicos, haciendo que la transacción se refleja como PayIn en la plataforma.

    Puedes conocer acerca de este método de pago en los siguientes artículos de [Perú](https://docs.prontopaga.com/docs/payins-peru-cash#/) y [Ecuador](https://docs.prontopaga.com/docs/payins-ecuador-cash#/).

    **<h3>Endpoint</h3>** Es una URL concreta de la API que permite ejecutar una operación.

    Ejemplo:

    * [https://sandbox.prontopaga.com/api/payment/new](https://sandbox.prontopaga.com/api/payment/new) para crear un cobro.
    * [https://sandbox.prontopaga.com/api/balance](https://sandbox.prontopaga.com/api/balance) para consultar saldos.

    Cada endpoint define el tipo de HTTP (los más usados en ProntoPaga son POST, y GET), los parámetros requeridos y las respuestas posibles ( las más conocidas son la respuesta 200: exitosa y 400: rechazada).

    **<h3>Environments / Entornos</h3>** Se trata de espacios aislados en los que se ejecutan las pruebas y operaciones de pago. Los ambientes usados por ProntoPaga son:

    * Sandbox, donde se simulan transacciones sin dinero real.

    * Producción, donde fluyen los pagos reales.

    Estos entornos suelen usar credenciales diferentes (como tu Bearer Token y secretKey dentro de ProntoPaga) y URLs separadas para evitar mezclar datos, permitiendo a los comercios desarrollar y probar flujos de pago completos antes de arriesgar dinero o exponer información sensible de clientes.
  </Tab>

  <Tab title="F">
    **<h3>Firma</h3>** Mecanismo que asegura que los datos de una petición o notificación no fueron manipulados. Normalmente se genera un hash (ej. HMAC SHA256) con una clave secreta compartida. El comercio recalcula la firma y la compara con la recibida para validar la autenticidad del mensaje.

    Si quieres conocer más acerca de las firmas, haz clic [aquí](https://docs.prontopaga.com/docs/sign-transactions#/).

    **<h3>Front-end</h3>** La capa visible para el usuario (ya sea una web o una aplicación). Aquí es donde se capturan datos, muestran formularios de pago o cajas de checkout.

    Estos siempre se enfocan en la experiencia de usuario: tiempos de carga, validaciones claras y confianza visual.
  </Tab>

  <Tab title="I">
    **<h3>iFrame</h3>** Elemento HTML que permite insertar contenido externo dentro de un sitio. En el sector de pagos, se usa para embebed formularios seguros (como el campo de tarjeta) de modo que los datos sensibles nunca toquen tu servidor, facilitando cumplir normativas de seguridad sin comprometer la experiencia de usuario.

    **<h3>Integración</h3>** Proceso de conectar tu aplicación, página web o sistema interno con un procesador de pagos o una orquestadora. Puede hacerse de distintas formas: APIs directas, SDKs (kits de desarrollo), iFrames que embeben formularios seguros, o plugins ya listos para plataformas de e-commerce. Una integración no solo habilita procesar cobros, sino también administrar contracargos, verificar identidades, emitir reembolsos y reconciliar balances.

    La mayoría de estas características están presentes en ProntoPaga.
  </Tab>

  <Tab title="M">
    **<h3>Marcas de tarjetas</h3>** Identificadores del tipo de tarjeta usada (VISA, Mastercard, American Express, etc.). En pasarelas de pago son utilizadas para determinar reglas, comisiones, compatibilidad, parámetros de tokenización o riesgo. En el checkout y tokenización, la marca puede influir en el proceso de autorización y en las comisiones.
  </Tab>

  <Tab title="O">
    **<h3>One-Click Payments</h3>** Método de pago que permite al usuario pagar con un solo clic, usando un medio de pago previamente afiliado (tarjeta, wallet, cuenta). En la integración de ProntoPaga con Yape, el cliente no necesita ingresar nuevamente sus datos: con su cuenta Yape afiliada puede completar la compra en un paso. 

Conoce más sobre esta integración de ProntoPaga en el siguiente [artículo](https://docs.prontopaga.com/docs/yape-on-file-ocp#/). 
  </Tab>

  <Tab title="P">
    **<h3>Paga con Tu Banco</h3>**
    Método de transferencia exclusivo de ProntoPaga vía enlace redirigido al banco del usuario para completar el pago o retiro, disponible en múltiples países.

    **<h3>Parámetros</h3>** Datos específicos que se envían en una solicitud API. Estos parámetros pueden incluirse en rutas de endpoints (/payments/{}) o en el body (JSON).

    Los parámetros son aquellos que permiten personalizar el comportamiento de cada operación (y que para un mismo endpoint, el resultado sea diferente cuando cambiamos los datos del parámetro).

    **<h3>PayIns</h3>** Se refiere al flujo de entrada de dinero, es decir, los cobros que tus usuarios o clientes hacen a tu comercio. Estos pueden provenir de múltiples métodos: tarjetas de crédito/débito, transferencias bancarias, billeteras digitales o pagos en efectivo a través de corresponsales. Todos estos métodos están disponibles en ProntoPaga.

    Los PayIns cuentan con diferentes estados dentro de ProntoPaga, que son: new, created, success, canceled, rejected, pending y expired.

    Conoce más acerca de los estados de PayIns en este [artículo](https://docs.prontopaga.com/docs/payins-status#/).

    **<h3>PayOuts</h3>** Son las salidas de dinero desde tu comercio hacia un tercero: proveedores, usuarios de un marketplace o la misma cuenta bancaria del comercio.

    Funcionan como retiros programados y también pasan por estados (conoce más de los estados de PayOuts [aquí](https://docs.prontopaga.com/docs/payouts-status#/)). Los PayOuts suelen tener límites, validaciones contra la prevención de fraude y ventanas de liquidación. Un Payout puede agrupar múltiples PayIns menos comisiones y contracargos.

    Conoce más acerca de los PayOuts en  el siguiente [artículo](https://docs.prontopaga.com/docs/payouts-overview#/).

    **<h3>Payphone</h3>**
    Método de pago integrado a ProntoPaga usado en Ecuador que permite aceptar pagos con tarjeta Visa o Mastercard, de crédito o débito, de cualquier banco en dispositivos físicos tipo POS. Para completar una transacción utilizando este método de pago, el cliente debe ingresar los datos de su tarjeta (número, fecha de expiración y código CVV).

    Si quieres conocer más acerca de este método, visita el siguiente [artículo](https://docs.prontopaga.com/docs/payins-ecuador-card#/).

    **<h3>Pendiente por Retiro</h3>** Monto que el comercio ya solicitó retirar (PayOut iniciado) pero que aún no se ha liquidado en su cuenta bancaria. Este estado intermedio permite distinguir entre lo que está disponible y lo que ya está “en camino”.

    **<h3>PIX</h3>**
    Sistema de pagos instantáneos de Brasil integrado en ProntoPaga, que permite PayIns y PayOuts en tiempo real. PIX fue creado y administrado por el Banco Central de Brasil, mediante el cual puedes realizar transacciones en tiempo real, tales como transacciones mediante el uso de códigos QR, claves PIX o transferencias directas.

    **<h3>PIX+</h3>**
    Expansión de PIX basada en Open Finance; permite interacciones financieras más flexibles e integradas en Brasil.

    **<h3>Plugins</h3>** En ProntoPaga contamos con módulos listos para instalar en plataformas como WooCommerce, Shopify, Magento o VTEX que conectan tu comercio con nosotros. Esto reduce el tiempo de desarrollo y permiten a comercios sin equipo técnico integrar cobros de manera segura.

    Puedes revisar nuestra [sección de plugins](https://docs.prontopaga.com/docs/overview-plugins#/) para conocer cómo realizar la integración.

    **<h3>Producción</h3>** Es el ambiente real donde fluyen los pagos con dinero verdadero. A diferencia del ambiente Sandbox, en Producción se procesan transacciones que impactan directamente en cuentas bancarias y balances de tu comercio.

    En ProntoPaga, Producción requiere credenciales específicas (Bearer Token y SecretKey del ambiente), las cuales solo se entregan una vez completada la certificación técnica. En este entorno, se aplican todas las validaciones antifraude, ventanas de liquidación y políticas regulatorias, por lo que es crítico mantener las credenciales seguras y monitorear constantemente las transacciones.

    **<h3>Puntos físicos de pago / de retiros</h3>**
    Ubicaciones físicas (corresponsales) donde los usuarios pueden realizar pagos en efectivo o cobrar retiros.Si deseas saber más, este método es usado en:

    * Ecuador  – Con puntos físicos de [pago](https://docs.prontopaga.com/docs/physical-points-payins-ecuador#/) y [retiro](https://docs.prontopaga.com/docs/physical-points-payouts#/).

    * Perú – con puntos físicos de [pago](https://docs.prontopaga.com/docs/physical-points-payins-peru#/).
  </Tab>

  <Tab title="Q">
    **<h3>QR</h3>** Código de barras bidimensional que almacena información y puede ser leído con una cámara. En pagos, los QR contienen instrucciones de pago: ya sea un enlace a un checkout, una orden de transferencia o un identificador único de transacción.

    Es usado por su simplicidad y compatibilidad con billeteras (wallets) digitales.
  </Tab>

  <Tab title="S">
    **<h3>Saldo Bloqueado</h3>** Fondos retenidos por situaciones especiales, como contracargos, disputas abiertas o revisiones de fraude. Estos montos permanecen inaccesibles hasta que la investigación concluya. El saldo bloqueado protege tanto al cliente como al comercio, evitando retiros que luego no podrían cubrir reembolsos.

    **<h3>Saldo Diferido</h3>** Es la porción del saldo que aún no puede retirarse porque está en periodo de espera. Normalmente corresponde a fondos que deben cumplir con reglas de liberación para reducir riesgos de contracargos o fraudes. Una vez cumplido ese tiempo, pasa al saldo disponible.

    **<h3>Saldo Neto</h3>** Es el saldo total del comercio dentro de la plataforma, sumando todo el dinero registrado (disponible, diferido y retenido), reflejando el total de lo que el comercio tiene, aunque no todo esté inmediatamente utilizable, ya que suelen incluirse pagos recién recibidos que aún no cumplen la ventana de liquidación y montos en disputa.

    **<h3>Sandbox</h3>** Se trata de un ambiente aislado de pruebas donde se pueden ejecutar transacciones ficticias con tarjetas de prueba y montos inventados. En ProntoPaga, nos permite probar integraciones, entrenar equipos de soporte y verificar lógicas de negocio sin ningún tipo de riesgo financiero.

    **<h3>SecretKey</h3>** Son credenciales secretas que identifican y autentican un sistema frente a la API del procesador de pagos. A diferencia de las llaves públicas, las secretKeys nunca deben exponerse en el front-end ni en código, ya que se usan para firmar solicitudes, crear cargos o programar retiros.

    En ProntoPaga contarás con llaves para cada entorno (sandbox y producción). La llave de producción requiere que estés certificado por la administración de ProntoPaga. Una vez hecho, podrás usar los datos reales y en vivo.
  </Tab>

  <Tab title="T">
    **<h3>Tipos de cuenta</h3>** En ProntoPaga existen deferentes tipos de cuenta, que varían según el país, por ejemplo: Una cuenta Corriente es de tipo 1 en Brasil, pero tipo C en Chile.

    Conoce más acerca de los tipos de cuentas en el siguiente [artículo](https://docs.prontopaga.com/docs/countries-currencies-accounts#/).

    **<h3>Transacción</h3>** Es la unidad básica de movimiento de dinero. Puede ser un cobro (PayIn), un retiro (PayOut), un reembolso, un contracargo o incluso una pre-autorización. Cada transacción tiene un identificador único y estados que permiten su trazabilidad.

    Además, para efectos contables, es el registro fundamental para conciliar balances y saldos.
  </Tab>

  <Tab title="W">
    **<h3>Wallet</h3>** En el sector de pagos, el término puede referirse a dos cosas:

    * **Wallet del usuario:** Aplicaciones como Apple Pay, Google Pay o billeteras propias que almacenan tarjetas tokenizadas y permiten pagar de forma rápida y segura.
    * **Wallet del comercio:** Balance virtual que cuentan todos los comercios dentro de ProntoPaga, donde se acumulan los PayIns hasta que se ejecutan PayOuts. Este Wallet refleja saldos disponibles, diferidos y bloqueados.

    **<h3>Webhook</h3>** Mecanismo de notificación automática: cuando ocurre un evento en la plataforma (ejemplo: pago aprobado, contracargo iniciado, payout rechazado), ProntoPaga envía un mensaje POST a una URL configurada por el comercio. De esta forma, el sistema del comercio puede reaccionar en tiempo real (enviar confirmaciones, actualizar estados, liberar productos).

    Para conocer más acerca de los webhooks, haz clic [aquí](https://docs.prontopaga.com/update/docs/webhooks#/).
  </Tab>
</Tabs>
