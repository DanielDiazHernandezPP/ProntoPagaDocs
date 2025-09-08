---
title: Glosario
excerpt: Conoce los términos de la industria de pagos dentro de esta documentación.
deprecated: false
hidden: true
metadata:
  robots: index
---
<Tabs>
  <Tab title="A">
    * **API:** Conjunto de reglas, protocolos y endpoints que permiten que tu sistema de software se comunique con otro. En el sector de pagos, gracias a las APIs puedes generar operaciones como crear un cobro, consultar el estado de una transacción, iniciar un reembolso o programar un payout.

      Se basa en estándares como JSON sobre HTTPS, lo que asegura interoperabilidad entre distintas plataformas.
  </Tab>

  <Tab title="B">
    * **Back-end:** La capa del servidor que procesa la lógica de negocio y comunica el sistema del comercio con ProntoPaga.

      Aquí se validan los webhooks, se gestionan las llaves secretas, se almacenan órdenes y se realiza la conciliación financiera. Es la parte “invisible” para el cliente final, pero crítica para la seguridad y el flujo de pagos.

    * **Balance Disponible:** Es el monto que realmente está listo para ser retirado por el comercio en ese momento. Se calcula restando al saldo neto el saldo diferido y el bloqueado. Representa la liquidez inmediata del comercio.

    * **Bearer Token:** Es un tipo de credencial de seguridad utilizado en APIs. El cliente incluye este token para demostrar que tiene permiso de acceder al recurso solicitado.

      A este tipo de credenciales suele llamárseles “al portador”, pues quien posea el token puede usarlo sin restricciones, por lo que deben mantenerse en secreto y transmitirse únicamente por conexiones seguras (HTTPS).

      Suelen tener caducidad alcances definidos, limitando qué operaciones puede ejecutar.

    * **Body:** Parte del mensaje HTTP que contiene los datos que envías en una petición (request) POST, PUT o GET. Normalmente va en formato JSON e incluye parámetros como monto, moneda, país o método de pago.

      Los parámetros del body pueden ser de un tipo de dato distinto, como String, Number o Boolean. Toda la información que necesitas para crear tu petición, puedes encontarla en nuestra sección de API Reference.\\

      Al momento de crearlos, debes asegurarte de que todos los parámetros estén incluidos dentro de su estructura para que la API procese la transacción.
  </Tab>

  <Tab title="C">
    * **Certificación:** Proceso formal en donde se valida que una integración cumple todos los requisitos técnicos y de seguridad antes de pasar a producción. En muchos casos, esto incluye que se ejecuten casos de prueba (éxito, error, contracargo, etc.) y documentar resultados. Una vez aprobado, se otorgan credenciales de producción.

    * **Changelog:** Se trata de un registro cronológico de cambios en la API y la plataforma: nuevas funcionalidades, endpoints deprecados, mejoras de seguridad.

      Si quieres conocer más acerca de los cambios que se han hecho en ProntoPaga, visita nuestra pestaña de Changelog.

    * **Checkout:** Es Interfaz lista para usarse que verán tus clientes finales para simplificar cobros. Puede ser una página redirigida o un modal embebido. Incluye métodos de pago, validaciones antifraude y cumplimiento PCI.

      Reduce tiempo de integración y garantiza que la experiencia cumpla los estándares de calidad necesarios.

    * **Cybersource:** Es una plataforma de procesamiento de pagos y gestión de fraude adquirida por Visa en 2010. Ofrece servicios de gateway, prevención de fraude, tokenización y orquestación global de medios de pago. Está orientada a comercios grandes y empresas multinacionales, con alcance en más de 190 países.
  </Tab>

  <Tab title="D">
    * **Decision Manager (DM):** Herramienta de prevención de fraude desarrollada por Cybersource (Visa). Funciona como un motor que evalúa cada transacción en tiempo real, aplicando reglas configurables y modelos de machine learning. Permite simular políticas con escenario, ajustar la tolerancia al riesgo y maximizar la tasa de aprobación reduciendo falsos positivos.

    * **Demo:** Aplicación o entorno de demostración que simula el flujo de pago real. Permite a comercios y desarrolladores visualizar la experiencia completa que verá el cliente final sin necesidad de escribir código. Suele acompañarse de ejemplos de credenciales y tarjetas de prueba.

      Puedes encontrar nuestras demo de PayIns o [PayOuts](https://www.figma.com/proto/sR8GayinfgLhXyMxlKjNJI/Demos-PayOuts-Prontopaga?page-id=11830%3A66971\&node-id=11830-66973\&viewport=1195%2C172%2C0.04\&t=ALYxaSbw4N7OP646-1\&scaling=scale-down\&content-scaling=fixed\&starting-point-node-id=11830%3A66973) en los links correspondientes.
  </Tab>

  <Tab title="E">
    * **Endpoint:** Es una URL concreta de la API que permite ejecutar una operación. Ejemplo: [https://sandbox.prontopaga.com/api/payment/new](https://sandbox.prontopaga.com/api/payment/new) para crear un cobro o [https://sandbox.prontopaga.com/api/balance](https://sandbox.prontopaga.com/api/balance) para consultar saldos.

      Cada endpoint define el tipo de HTTP (los más usados en ProntoPaga son POST, y GET), los parámetros requeridos y las respuestas posibles ( las más conocidas son la respuesta 200: exitosa y 400: rechazada).

    * **Environments / Entornos** Se trata de espacios aislados en los que se ejecutan las pruebas y operaciones de pago. Los ambientes usados por ProntoPaga son:

    * Sandbox, donde se simulan transacciones sin dinero real.

    * Producción, donde fluyen los pagos reales.

      Estos entornos suelen usar credenciales diferentes (como tu Bearer Token y secretKey dentro de ProntoPaga) y URLs separadas para evitar mezclar datos, permitiendo a los comercios desarrollar y probar flujos de pago completos antes de arriesgar dinero o exponer información sensible de clientes.
  </Tab>

  <Tab title="F">
    * **Firma:** Mecanismo que asegura que los datos de una petición o notificación no fueron manipulados. Normalmente se genera un hash (ej. HMAC SHA256) con una clave secreta compartida. El comercio recalcula la firma y la compara con la recibida para validar la autenticidad del mensaje.

      Si quieres conocer más acerca de las firmas, haz clic [aquí](https://docs.prontopaga.com/docs/sign-transactions#/).

    * **Front-end:** La capa visible para el usuario (ya sea una web o una app). Aquí es donde se capturan datos, muestrannformularios de pago o cajas de checkout.

      Estos siempre se enfocan en la experiencia de usuario: tiempos de carga, validaciones claras y confianza visual.
  </Tab>

  <Tab title="I">
    * **iFrame:** Elemento HTML que permite insertar contenido externo dentro de un sitio. En el sector de pagos, se usa para embebed formularios seguros (como el campo de tarjeta) de modo que los datos sensibles nunca toquen tu servidor, facilitando cumplir normativas de seguridad sin comprometer la experiencia de usuario.

    * **Integración** Proceso de conectar tu aplicación, página web o sistema interno con un procesador de pagos o una orquestadora. Puede hacerse de distintas formas: APIs directas, SDKs (kits de desarrollo), iFrames que embeben formularios seguros, o plugins ya listos para plataformas de e-commerce. Una integración no solo habilita procesar cobros, sino también administrar contracargos, verificar identidades, emitir reembolsos y reconciliar balances.

      La mayoría de estas características están presentes en ProntoPaga.
  </Tab>

  <Tab title="P">
    * **Parámetro:s** Datos específicos que se envían en una solicitud API. Estos parámetros pueden incluirse en rutas de endpoints (/payments/{}) o en el body (JSON).

      Los parámetros son aquellos que permiten personalizar el comportamiento de cada operación (y que para un mismo endpoint, el resultado sea diferente cuando cambiamos los datos del parámetro).

    * **PayIns:** Se refiere al flujo de entrada de dinero, es decir, los cobros que tus usuarios o clientes hacen a tu comercio. Estos pueden provenir de múltiples métodos: tarjetas de crédito/débito, transferencias bancarias, billeteras digitales o pagos en efectivo a través de corresponsales. Todos estos métodos están disponibles en ProntoPaga.

      Los PayIns cuentan con diferentes estados dentro de ProntoPaga, que son: new, created, success, canceled, rejected, pending y expired.

      Conoce más acerca de los estados de PayIns en este artículo.

    * **PayOuts:** Son las salidas de dinero desde tu comercio hacia un tercero: proveedores, usuarios de un marketplace o la misma cuenta bancaria del comercio.

      Funcionan como retiros programados y también pasan por estados (conoce más de los estados de PayOuts aquí). Los PayOuts suelen tener límites, validaciones contra la prevención de fraude y ventanas de liquidación. Un Payout puede agrupar múltiples PayIns menos comisiones y contracargos.

    * **Pendiente por Retiro:** Monto que el comercio ya solicitó retirar (PayOut iniciado) pero que aún no se ha liquidado en su cuenta bancaria. Este estado intermedio permite distinguir entre lo que está disponible y lo que ya está “en camino”.

    * **Plugins:** En ProntoPaga contamos con módulos listos para instalar en plataformas como WooCommerce, Shopify, Magento o VTEX que conectan tu comercio con nosotros. Esto reduce el tiempo de desarrollo y permiten a comercios sin equipo técnico integrar cobros de manera segura.

      Puedes revisar nuestra sección de plugins para conocer cómo realizar la integración.
  </Tab>

  <Tab title="Q">
    **QR (Quick Response Code)**\
    Código de barras bidimensional que almacena información y puede ser leído con una cámara. En pagos, los QR contienen instrucciones de pago: ya sea un link a un checkout, una orden de transferencia o un identificador único de transacción. Es usado por su simplicidad y compatibilidad con billeteras (wallets) digitales.
  </Tab>

  <Tab title="S">
    **Sandbox**\
    Se trata de un ambiente aislado de pruebas donde se pueden ejecutar transacciones ficticias con tarjetas de prueba y montos inventados. En ProntoPaga, nos permite probar integraciones, entrenar equipos de soporte y verificar lógicas de negocio sin ningún tipo de riesgo financiero.

    **Saldo Bloqueado**\
    Fondos retenidos por situaciones especiales, como contracargos, disputas abiertas o revisiones de fraude. Estos montos permanecen inaccesibles hasta que la investigación concluya. El saldo bloqueado protege tanto al cliente como al comercio, evitando retiros que luego no podrían cubrir reembolsos.

    **Saldo Diferido**\
    Es la porción del saldo que aún no puede retirarse porque está en periodo de espera. Normalmente corresponde a fondos que deben cumplir con reglas de liberación para reducir riesgos de contracargos o fraudes. Una vez cumplido ese tiempo, pasa al saldo disponible.

    **Saldo Neto**\
    Es el saldo total del comercio dentro de la plataforma, sumando todo el dinero registrado (disponible, diferido y retenido), reflejando el total de lo que el comercio tiene, aunque no todo esté inmediatamente utilizable, ya que suelen incluirse pagos recién recibidos que aún no cumplen la ventana de liquidación y montos en disputa.

    **SecretKey / API Keys**\
    Son credenciales secretas que identifican y autentican un sistema frente a la API del procesador de pagos. A diferencia de las llaves públicas, las secretKeys nunca deben exponerse en el front-end ni en código, ya que se usan para firmar solicitudes, crear cargos o programar retiros.\
    En ProntoPaga contarás con llaves para cada entorno (sandbox y producción). La llave de producción requiere que estés certificado por la administración de ProntoPaga. Una vez hecho, podrás usar los datos reales y en vivo.
  </Tab>

  <Tab title="T">
    **Transacción**\
    Es la unidad básica de movimiento de dinero. Puede ser un cobro (PayIn), un retiro (PayOut), un reembolso, un contracargo o incluso una pre-autorización. Cada transacción tiene un identificador único y estados que permiten su trazabilidad. Además, Para efectos contables, es el registro fundamental para conciliar balances y saldos.
  </Tab>

  <Tab title="W">
    **Wallet (billetera / monedero digital)**\
    En pagos, el término puede referirse a dos cosas:

    * Wallet del usuario: aplicaciones como Apple Pay, Google Pay o billeteras propias que almacenan tarjetas tokenizadas y permiten pagar de forma rápida y segura.
    * Wallet del comercio: balance virtual que cuentan todos los comercios dentro de ProntoPaga, donde se acumulan los PayIns hasta que se ejecutan PayOuts. Este Wallet refleja saldos disponibles, diferidos y bloqueados.

    **Webhook**\
    Mecanismo de notificación automática: cuando ocurre un evento en la plataforma (ejemplo: pago aprobado, contracargo iniciado, payout rechazado), ProntoPaga envía un mensaje POST a una URL configurada por el comercio. De esta forma, el sistema del comercio puede reaccionar en tiempo real (enviar confirmaciones, actualizar estados, liberar productos). Para conocer más acerca de los webhooks, haz clic aquí.
  </Tab>
</Tabs>

<br />
