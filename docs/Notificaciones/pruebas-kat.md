---
title: pruebas Kat
deprecated: false
hidden: true
metadata:
  robots: index
---
<Accordion title="My Accordion Title" icon="fa-info-circle">
  Lorem ipsum dolor sit amet, **consectetur adipiscing elit.** Ut enim
  ad minim veniam, quis nostrud exercitation ullamco. Excepteur sint
  occaecat cupidatat non proident!
</Accordion>

***

| En web | En mobileó |
| :----- | :--------- |
|        |            |
|        |            |

<br />

<Accordion title={<span style={{ fontSize: '18px', fontWeight: 'bold' }}>🏦 Flujo de validación pago a terceros</span>}>
  Conoce el flujo de validacion de pago a terceros, tanto para flujo web como flujo mobile.

  <Table align={["left","left","left","left"]}>
    <thead>
      <tr>
        <th style={{ textAlign: "left" }}>
          En web
        </th>

        <th style={{ textAlign: "left" }}>
          En mobile
        </th>

        <th style={{ textAlign: "left" }}>
          Límites de transacciones en curso:
        </th>

        <th style={{ textAlign: "left" }}>
          Tiempo de espera para la segunda transacción:
        </th>
      </tr>
    </thead>

    <tbody>
      <tr>
        <td style={{ textAlign: "left" }}>
          a. **Si se tiene desactivado el servicio de validación pago de terceros:** Se le pide al cliente ingresar su número de celular para solicitar el pago. Luego se le muestra en pantalla un instructivo para abrir su aplicación y aprobar el pago en la sección de **Aprobar compras**.

          b. **Si se tiene activado el servicio de validación pago de terceros:** Se le pide al cliente confirmar su número de celular para solicitar el pago. Si los datos no coinciden, se le muestra un mensaje de error. Si los datos coinciden, se le manda la solicitud directamente a su aplicación de Yape (por notificación y correo). El cliente ingresa, ve en pantalla las solicitudes por aprobar, selecciona la indicada y hace clic en **Confirmar**.
        </td>

        <td style={{ textAlign: "left" }}>
          CLP $350.000
        </td>

        <td style={{ textAlign: "left" }}>
          * **DigiPass y Mi Pass**: hasta $5.000.000 diarios (CLP)
          * **DigiCard**:
            hasta $2.000.000 diarios (CLP)
        </td>

        <td style={{ textAlign: "left" }}>
          12 horas
        </td>
      </tr>
    </tbody>
  </Table>
</Accordion>

<br />

### General (todos los países)

A continuación se muestran varios posibles casos de rechazo, junto con su descripción.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Mensaje de rechazo
      </th>

      <th>
        Descripción
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        The client is blocked
      </td>

      <td>
        El cliente se bloquea en lista negra.
      </td>
    </tr>

    <tr>
      <td>
        Exceeds daily limit,
        5,000,000.00 BRL available for the day,
        10,000,000.00 BRL available for the week,
        30,000,000.00 BRL available for the month.
        Maximum deposit per transaction 6,000,000.00 BRL
      </td>

      <td>
        El cliente ha superado los límites establecidos para la transacción o comercio.
      </td>
    </tr>

    <tr>
      <td>
        High fraudulent score - DM
      </td>

      <td>
        La transacción tiene un alto nivel de riesgo de fraude.
      </td>
    </tr>
  </tbody>
</Table>

***

### Argentina

#### Tarjeta

A continuación se muestran varios posibles casos de rechazo, junto con su descripción.

| Mensaje de rechazo     | Descripción                                                                                                                |
| :--------------------- | :------------------------------------------------------------------------------------------------------------------------- |
| INSUFFICIENT_FUNDS     | Saldo insuficiente para realizar la transacción.                                                                           |
| RECHAZADO POR EL BANCO | Tu banco rechazó la transacción. Contáctate con ellos para más información.                                                |
| DO_NOT_HONOR           | Tu banco rechazó la transacción. Intenta con otra tarjeta o contacta a tu banco.                                           |
| INVALID_SECURITY_CODE  | El código CVV ingresado no es correcto. Verifica e inténtalo nuevamente.                                                   |
| INVALID_CARD_DATA      | Los datos de la tarjeta ingresados son incorrectos. Revisa los datos e inténtalo de nuevo.                                 |
| REPORTED_STOLEN        | No se puede realizar la transacciones. La tarjeta ha sido reportada como robada. Contacta a tu banco para más información. |
| ERROR                  | Se ha producido un error en la transacción. Inténtalo nuevamente o usa otro método de pago.                                |

***

### Brasil

A continuación se muestran varios posibles casos de rechazo, junto con su descripción.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Mensaje de rechazo
      </th>

      <th>
        Descripción
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Exceeds daily limit,
        5,000,000.00 BRL available for the day,
        10,000,000.00 BRL available for the week,
        30,000,000.00 BRL available for the month.
        Maximum deposit per transaction 6,000,000.00 BRL
      </td>

      <td>
        El cliente ha superado los límites establecidos para la transacción o comercio.
      </td>
    </tr>

    <tr>
      <td>
        Error while creating the payment in the Pix service. Please try again
      </td>

      <td>
        Error al crear el pago en el servicio Pix.
      </td>
    </tr>

    <tr>
      <td>
        Error generating Pix QR Code
      </td>

      <td>
        Error al generar el código QR Pix.
      </td>
    </tr>

    <tr>
      <td>
        Error generating Pix AccessToken
      </td>

      <td>
        Error al generar el Token de Acceso Pix.
      </td>
    </tr>
  </tbody>
</Table>

***

### Chile

#### Paga Con Tu Banco

A continuación se muestran varios posibles casos de rechazo, junto con su descripción.

| Mensaje de rechazo                     | Descripción                         |
| :------------------------------------- | :---------------------------------- |
| Bank not recognized                    | Banco no reconocido en la metadata. |
| No destination account for BancoEstado | BancoEstado sin cuenta configurada. |
| Failed to assign destination account   | Error al asignar cuenta destino.    |
| Unexpected internal error              | Error inesperado.                   |

#### Tarjeta

A continuación se muestran varios posibles casos de rechazo, junto con su descripción.

| Mensaje de rechazo         | Descripción                                                                                           |
| :------------------------- | :---------------------------------------------------------------------------------------------------- |
| Excede monto máximo        | La transacción excede el monto máximo establecido.                                                    |
| Problema en la transacción | Se ha producido un error en la transacción. Inténtalo nuevamente o usa otro método de pago.           |
| Rechazo general            | Se ha producido un rechazo general de la transacción. Inténtalo nuevamente o usa otro método de pago. |

***

### Ecuador

#### Efectivo

A continuación se muestran varios posibles casos de rechazo, junto con su descripción.

| Mensaje de rechazo                            | Descripción                                                  |
| :-------------------------------------------- | :----------------------------------------------------------- |
| Excede límite Depósito Máximo por Transacción | Se ha excedido el límite de depósito máximo por transacción. |

#### Tarjeta / Wallet

A continuación se muestran varios posibles casos de rechazo, junto con su descripción.

| Mensaje de rechazo                                                   | Descripción                                                                           |
| :------------------------------------------------------------------- | :------------------------------------------------------------------------------------ |
| There is already a pending payment for that phone number.            | El cliente tiene una transacción de pago pendiente para ese mismo número de teléfono. |
| Failed payment: There is already a pending payment transaction.      | El cliente tiene una transacción de pago pendiente.                                   |
| The identity document does not match the one registered in PayPhone. | El documento ingresado no coincide con el documento registrado en Payphone.           |

***

### Perú

#### Paga Con Tu Banco

A continuación se muestran varios posibles casos de rechazo, junto con su descripción.

| Mensaje de rechazo                          | Descripción                                                                              |
| :------------------------------------------ | :--------------------------------------------------------------------------------------- |
| Bank not recognized                         | El banco no se encuentra reconocido en la metadata.                                      |
| Failed to assign destination account        | Se ha producido un error al asignar cuenta destino.                                      |
| Unexpected internal error                   | Se ha producido un error inesperado. Inténtalo nuevamente o usa otro método de pago.     |
| Payment cancelled by user                   | El pago ha sido cancelado por el cliente.                                                |
| Account blocked by your bank                | Tu cuenta ha sido bloqueada por tu banco.                                                |
| Las credenciales ingresadas son incorrectas | Las credenciales proporcionadas por el cliente son incorrectas.                          |
| Error de servicio                           | Se ha producido un error en el servicio. Inténtalo nuevamente o usa otro método de pago. |

<br />

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Documentación técnica de ProntoPaga">
    <title>Documentación ProntoPaga</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
    <style>
    /* Variables globales */
        :root {
            --pp-primary: #FC2B5F;
            --pp-secondary: #FF6B8C;
            --pp-tertiary: #E2E8F0;
            --pp-bg-light: #FFF0F2; 
            --pp-gradient: linear-gradient(220.16deg, var(--pp-secondary) 0%, var(--pp-primary) 99.36%);
            --pp-text-dark:; #1E293B
            --pp-text-light: #F9F9F9;
            --pp-shadow-sm: 0 4px 6px rgba(0, 0, 0, 0.05);
            --pp-shadow-lg: 0 12px 24px rgba(252, 43, 95, 0.15);
            --pp-border-radius: 1.5rem;
            --pp-border-radius-sm: 1.25rem;
            --pp-spacing-xs: 0.5rem;
            --pp-spacing-sm: 0.75rem;
            --pp-spacing: 1rem;
            --pp-spacing-md: 1.25rem;
            --pp-spacing-lg: 2rem;
            --pp-transition: all 0.3s ease;
            /* BORRAR VARIABLE CUANDO SE SUBA A PRODUCCIÓN */
            --Header-button-color: black;

        } 
    /* BORRAR VARIABLE CUANDO SE SUBA A PRODUCCIÓN */

        .bg-dark-test {
            background-color: #242e34 !important;
            --Header-button-color: #FFFFFF;
        }
    /* Tipografía */
        .hero-title {
            color: var(--Header-button-color);
            font-size: 4.5rem !important;
            font-weight: 700 !important;
            line-height: 1.1 !important;
            padding: var(--pp-spacing-);
        }

        .gradient-text {
            background: var(--pp-gradient);
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .lead {
            font-size: 1.25rem;
            font-weight: 400;
            padding-right: var(--pp-spacing);
          	padding-top: 3rem;

        }
    /* PATRÓN BACKGROUND */

        [data-color-mode="dark"] body {
            background-color: #242e34;
        }
        .background-decoration {
            position: relative;
            width: 100%;
            height: 0;
            z-index: -1;
        }

        .bg-cards {
            position: absolute;
            width: 100%;
            height: auto;
            aspect-ratio: 75/30;
            top: -5rem;
            object-fit: contain;
            max-width: 100vw;
        }
        .fade-left {
            -webkit-mask-image: linear-gradient(to right, rgba(0, 0, 0, 0) 0%, rgba(0, 0, 0, 1) 20%) !important;
            mask-image: linear-gradient(to right, rgba(0, 0, 0, 0) 0%, rgba(0, 0, 0, 1) 20%) !important;
            -webkit-mask-size: 100% 100% !important;
            mask-size: 100% 100%;
            -webkit-mask-repeat: no-repeat !important;
            mask-repeat: no-repeat;
        }
    /* Grid para tarjetas */
        .cards-container {
            display: grid;
            grid-template-columns: repeat(12, 1fr);
            gap: 24px;
        }

    /* Tarjetas individuales */
        .card-item {
            border-radius: var(--pp-border-radius);
            box-shadow: var(--pp-shadow-sm);
            overflow: hidden;
            transition: var(--pp-transition);
            display: flex;
            flex-direction: column;
            height: 100%;
        }

        .card-item:hover {
            transform: translateY(-3px);
        }

    /* Tamaños de tarjetas */
        .card-lg {
            grid-column: span 8;
        }

        .card-sm {
            grid-column: span 4;
        }

    /* Imagen de tarjeta */
        .card-image {
            background-color: var(--pp-bg-light);
            padding: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            height: 185px;
            position: relative;
            z-index: 1;
        }
        .card-image img {
            position: absolute;
            width: 25rem;
            height: 20rem;
            top: 71%;
            left: 50%;
            transform: translate(-50%, -50%);
        }
        .card-content {
            background-color: white;
            padding: 20px;
            display: flex;
            z-index: 2;
            flex-direction: column;
            flex: 1;
        }

        /*body.bg-dark-test .card-content {
            background-color: #3A4950;
        }*/

        [data-color-mode="dark"] .card-content {
            background-color: #3A4950;
        }

        /*body.bg-dark-test .card-title {
            color: white;
        }*/

        [data-color-mode="dark"] .card-title {
            color: white;
        }

        /*body.bg-dark-test .card-description {
            color: white;
        }*/

        [data-color-mode="dark"] .card-description {
            color: white;
        }

        /*body.bg-dark-test .lead{
            color: white;
        }*/

        [data-color-mode="dark"] .card-lead {
            color: white;
        }

        /*body.bg-dark-test .bg-cards {
            content: url('https://documentacion-prontopaga.s3.us-east-1.amazonaws.com/background+linear.svg');
            opacity: 0.3;
        }*/

        [data-color-mode="dark"] .bg-cards {
            content: url('https://documentacion-prontopaga.s3.us-east-1.amazonaws.com/background+linear.svg');
            opacity: 0.3;
        }
    /* Título de tarjeta */
        .card-title {
            font-size: 1.25rem!important;
            font-weight: 700!important;
            color: var(--pp-text-dark)!important;
            margin-top: 8px!important;
          	margin-bottom: 0.25rem !important;
            line-height: 1.25rem!important;
        }

    /* Descripción de tarjeta */
        .card-description {
            z-index: 2!important;
            font-size: 1rem!important;
            font-weight: 400!important;
            color: var(--pp-text-light)!important;
            margin-top: 14px!important;
            margin-bottom: 18px!important;
            line-height: 1.188rem!important;
            flex: 1;
        }

        .btn-pp {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            font-size: 0.875rem;
            font-weight: 500;
            border-radius: var(--pp-border-radius);
            text-decoration: none;
            transition: all 0.3s ease;
            cursor: pointer;
            min-width: 160px;
        }

        .btn-pp-primary {
            background: var(--pp-gradient);
            color: white;
            border: none;
        }

        .btn-pp-primary:hover,
        .btn-pp-primary:focus {
            transform: translateY(-2px);
            color: white;
            text-decoration: none;
        }

        .btn-pp-primary:active {
            transform: translateY(0);
            box-shadow: var(--pp-shadow-sm);
        }

    /* Botón de tarjeta */
        .card-button {
            display: inline-block;
            text-align: left;
            margin-top: auto;
        }

        .btn-saber-mas {
            display: inline-block;
            background-color: transparent;
            color: var(--pp-secondary)!important;
            border: 1px solid var(--pp-tertiary)!important;
            border-radius: 20px;
            padding: 6px 16px;
            font-size: 0.875rem;
            text-decoration: none;
            transition: var(--pp-transition);
        }

        .btn-saber-mas:hover {
            background-color: var(--pp-secondary)!important;
            border: 1px solid var(--pp-secondary)!important;
            color: white!important;
        }

    @media (max-width: 991px) {

        .btn-pp {
            width: 50%;
            font-size: 0.75rem;
            padding: var(--pp-spacing-xs) var(--pp-spacing-sm);
            margin-left: 0.7rem;
        }

        .hero-title {
            font-size: 3.38rem !important;
            line-height: 1.15 !important;
        }
        .lead {
            font-size: 1rem;
            padding: var(--pp-spacing-sm);
          	padding-top: 3rem!important;

        }

        .bg-cards {
            width: min(50rem, 100%);
            top: -3rem;
        }

        .cards-container {
            gap: 16px;
        }
          
        .card-lg, .card-sm {
            grid-column: span 6;
        }
    }

    @media (max-width: 767px) {

        main.container {
            padding-top: 0 !important;
        }

        .containerP {
            margin: 0 auto;
        }

        .hero-title {
            margin-bottom: var(--pp-spacing);
        }

        .lead {
            font-size: 1rem;
            padding-left: 1%;
            text-align: left;
        }

        .btn-pp {
            width: 100%;
            justify-content: center;
            padding: 0.75rem 1rem;
            height: 2.5rem;
          	margin-left: 0;
        }

        .background-decoration {
            position: relative;
            width: 100%;
        }

        .bg-cards {
            position: absolute;
            width: 100%; 
            height: auto;
            top: -4rem;
            left: 50%;
            transform: translateX(-50%);
        }

        .btn-pp-primary {
            font-size: 1rem;
        }

        .cards-container {
            gap: 12px;
            padding: 0 var(--pp-spacing);
        }

        .card-lg, .card-sm {
            grid-column: span 12;
        }
          
        .card-image {
            height: 24.625dvh;
        }
    }
    </style>
</head>
<body>
  <main class="container py-5">
      <!-- Hero Section -->
        <section class="containerP container row align-items-center mb-5" aria-labelledby="hero-title">
            <div class="col-md-6">
                <h1 id="hero-title" class="hero-title">
                    <span class="d-block">Integra</span>
                    <span class="gradient-text d-block">ProntoPaga</span>
                    <span class="d-block">paso a paso</span>
                </h1>
            </div>
            <div class="col-md-6">
                <p class="lead">Explora nuestras guías y ejemplos para integrar <i>Prontopaga</i> y proporcionar a tus clientes acceso a métodos de pago, procesadores y sistemas de prevención de fraude a nivel mundial.</p>
                <a href="https://docs.prontopaga.com/docs/welcome" class="btn btn-pp btn-pp-primary" aria-label="Comenzar integración con ProntoPaga" role="button">Comenzar integración</a>
            </div>
        </section>

        <div class="background-decoration" aria-hidden="true">
            <img class="bg-cards fade-left" src="https://documentacion-prontopaga.s3.us-east-1.amazonaws.com/Union.svg" alt="" role="presentation">
        </div>
        <!-- Tarjetas de contenido -->
      <div class="container py-4">
        <div class="cards-container">
            <!-- Primeros pasos -->
            <div class="card-item card-lg">
                <div class="card-image">
                    <img src="https://documentacion-prontopaga.s3.us-east-1.amazonaws.com/Primeros_pasos.svg" alt="Ilustración de primeros pasos">
                </div>
                <div class="card-content">
                    <h2 class="card-title">Primeros pasos</h2>
                    <p class="card-description">Obtén tus claves de API y conoce lo necesario para realizar tu primera solicitud, así como los conceptos clave para integrarte.</p>
                    <div class="card-button">
                        <a href="https://docs.prontopaga.com/docs/first-steps" class="btn-saber-mas">Saber más</a>
                    </div>
                </div>
            </div>

            <!-- Referencia API -->
            <div class="card-item card-sm">
                <div class="card-image">
                    <img src="https://documentacion-prontopaga.s3.us-east-1.amazonaws.com/Referencia_API.svg" alt="Ilustración de referencia API">
                </div>
                <div class="card-content">
                    <h2 class="card-title">Referencia API</h2>
                    <p class="card-description">Los endpoints de nuestra referencia API cuentan con diversos ejemplos creados para mejorar tu experiencia de integración.</p>
                    <div class="card-button">
                        <a href="https://docs.prontopaga.com/reference/payment-methods" class="btn-saber-mas">Saber más</a>
                    </div>
                </div>
            </div>

            <!-- Integra PayIns -->
            <div class="card-item card-sm">
                <div class="card-image">
                    <img src="https://documentacion-prontopaga.s3.us-east-1.amazonaws.com/Integra_PayIns.svg" alt="Ilustración de PayIns">
                </div>
                <div class="card-content">
                    <h2 class="card-title">Integra PayIns</h2>
                    <p class="card-description">Conoce cómo integrar nuestros diferentes métodos de pago</p>
                    <div class="card-button">
                        <a href="https://docs.prontopaga.com/docs/payins-brazil-pix" class="btn-saber-mas">Saber más</a>
                    </div>
                </div>
            </div>

            <!-- Integra PayOuts -->
            <div class="card-item card-lg">
                <div class="card-image">
                    <img src="https://documentacion-prontopaga.s3.us-east-1.amazonaws.com/Integra_PayOuts.svg" alt="Ilustración de PayOuts">
                </div>
                <div class="card-content">
                    <h2 class="card-title">Integra PayOuts</h2>
                    <p class="card-description">Revisa nuestras guías de pay outs para conocer un paso a paso de cómo integrar nuestros diferentes métodos de retiro.</p>
                    <div class="card-button">
                        <a href="https://docs.prontopaga.com/docs/payouts-brazil-pix" class="btn-saber-mas">Saber más</a>
                    </div>
                </div>
            </div>

            <!-- Métodos por país -->
            <div class="card-item card-lg">
                <div class="card-image">
                    <img src="https://documentacion-prontopaga.s3.us-east-1.amazonaws.com/Me%CC%81todos_por_pai%CC%81s.svg" alt="Ilustración de métodos por país">
                </div>
                <div class="card-content">
                    <h2 class="card-title">Métodos por país</h2>
                    <p class="card-description">Entérate de todos los lugares en donde operamos. Con nuestras láminas de cobertura por país, conoce todos nuestros métodos disponibles.</p>
                    <div class="card-button">
                        <a href="https://docs.prontopaga.com/docs/methods-per-country-brazil" class="btn-saber-mas">Saber más</a>
                    </div>
                </div>
            </div>

            <!-- ¿Cómo usar este sitio? -->
            <div class="card-item card-sm">
                <div class="card-image">
                    <img src="https://documentacion-prontopaga.s3.us-east-1.amazonaws.com/%C2%BFCo%CC%81mo_usar_este_sitio.svg" alt="Ilustración de guía del sitio">
                </div>
                <div class="card-content">
                    <h2 class="card-title">¿Cómo usar este sitio?</h2>
                    <p class="card-description">Conoce el paso a paso de como usar nuestro sitio.</p>
                    <div class="card-button">
                        <a href="https://docs.prontopaga.com/reference/quick-guide-doc" class="btn-saber-mas">Saber más</a>
                    </div>
                </div>
            </div>

            <!-- Plugin de Woocommerce -->
            <div class="card-item card-sm">
                <div class="card-image">
                    <img src="https://documentacion-prontopaga.s3.us-east-1.amazonaws.com/Plugin_de_Woocommerce.svg" alt="Ilustración de WooCommerce">
                </div>
                <div class="card-content">
                    <h2 class="card-title">Plugin de Woocommerce</h2>
                    <p class="card-description">Descubre el proceso paso a paso para instalar WooCommerce de manera fácil y efectiva.</p>
                    <div class="card-button">
                        <a href="https://docs.prontopaga.com/docs/overview-plugins" class="btn-saber-mas">Saber más</a>
                    </div>
                </div>
            </div>

            <!-- Colección de Postman -->
            <div class="card-item card-lg">
                <div class="card-image">
                    <img src="https://documentacion-prontopaga.s3.us-east-1.amazonaws.com/Coleccio%CC%81n_de_Postman.svg" alt="Ilustración de Postman">
                </div>
                <div class="card-content">
                    <h2 class="card-title">Colección de Postman</h2>
                    <p class="card-description">Contamos con una colección de Postman en donde podrás hacer pruebas con todos nuestros endpoints, incluso sin credenciales.</p>
                    <div class="card-button">
                        <a href="https://docs.prontopaga.com/reference/postman" class="btn-saber-mas">Saber más</a>
                    </div>
                </div>
            </div>
        </div>
    </div>
  </main>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
`}</HTMLBlock>

<br />

<HTMLBlock>{`
<div class="selectors">
  <a class="selector" href="/docs/vtex">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a9/VTEX_Logo.svg/305px-VTEX_Logo.svg.png?20211207023221" style="max-height:70px" class="icon-plugin">
  </a>
  <a class="selector" href="/docs/shopify">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/e7/Shopify_logo.svg/800px-Shopify_logo.svg.png?20200909100300" style="max-height:70px" class="icon-plugin">
  </a>
</div>
`}</HTMLBlock>

***

| Mensajes de rechazo |
| :------------------ |
|                     |
|                     |

<br />

<br />

***

<HTMLBlock>{`
<div class="background-decoration" aria-hidden="true">
            <img class="bg-cards fade-left" src="https://documentacion-prontopaga.s3.us-east-1.amazonaws.com/Union.svg" alt="" role="presentation">
        </div>
        <!-- Tarjetas de contenido -->
      <div class="container py-4">
        <div class="cards-container">
            <!-- PrestaShop -->
            <div class="card-item card-lg">
                <div class="card-image">
                    <img src="https://files.readme.io/0622c4c5eda1747285ef87390e320dcf9dd1aafa518601634ce7c7b729d91a94-prestashop.svg" alt="Prestashop Logo">
                </div>
                <div class="card-content">
                    <h2 class="card-title">PrestaShop</h2>
                    <p class="card-description">Consulta su Guía de instalación y configuración aquí.</p>
                    <div class="card-button">
                        <a href="https://docs.prontopaga.com/docs/prestashop#/" class="btn-saber-mas">Saber más</a>
                    </div>
                </div>
            </div>
`}</HTMLBlock>

<br />

***

<br />

<br />

<Accordion title="My Accordion Title">
  * **Si se tiene desactivado el servicio de validación pago de terceros**. Se le pide al cliente ingresar su número de celular para solicitar el pago. Luego se le muestra en pantalla un instructivo para abrir su aplicación y aprobar el pago en la sección de **Aprobar compras**.
    * **Si se tiene activado el servicio de validación pago de terceros**. Se le pide al cliente confirmar su número de celular para solicitar el pago. Si los datos no coinciden, se le muestra un mensaje de error. Si los datos coinciden, se le manda la solicitud directamente a su aplicación de Yape (por notificación y correo). El cliente ingresa, ve en pantalla las solicitudes por aprobar, selecciona la indicada y hace clic en **Confirmar**.
</Accordion>

## ¿Cómo funciona?

Yape es una aplicación que permite realizar pagos y transferencias de dinero en Perú, utilizando solo el número de celular. Con Yape, los usuarios pueden hacer pagos en línea, recargar saldo en su cuenta o realizar compras en comercios afiliados. Para completar una transacción utilizando este método de pago, el cliente debe seleccionar la opción "Paga con Yape", tener una cuenta creada y aprobar la compra desde su aplicación.

El proceso de pago con wallet en Perú consta de cinco etapas principales:

1. **Selección de método.** Durante el checkout, el cliente elige pagar con Yape en tu sitio web o aplicación.
2. **Solicitud.** ProntoPaga se comunica con la wallet y genera la solicitud de pago.
3. **Aprobación.** El flujo de aprobación del pago varía según el dispositivo del cliente y si tu comercio tiene o no activado el servicio de validación de pago de terceros:

   1. **En web:**

<Cards columns={2}>
  <Card title="Si se tiene desactivado el servicio de validación pago de terceros">
    Se le pide al cliente ingresar su número de celular para solicitar el pago. Luego se le muestra en pantalla un instructivo para abrir su aplicación y aprobar el pago en la sección de **Aprobar compras**.
  </Card>

  <Card title="Si se tiene activado el servicio de validación pago de terceros">
    Se le pide al cliente confirmar su número de celular para solicitar el pago. Si los datos no coinciden, se le muestra un mensaje de error. Si los datos coinciden, se le manda la solicitud directamente a su aplicación de Yape (por notificación y correo). El cliente ingresa, ve en pantalla las solicitudes por aprobar, selecciona la indicada y hace clic en **Confirmar**.
  </Card>
</Cards>

<HTMLBlock>{`
<button>
  <i aria-hidden class="fa-duotone fa-solid fa-computer-classic"></i>
  Download to Floppy
</button>
`}</HTMLBlock>

<br />

<button>
  <i aria-hidden class="fa-duotone fa-solid fa-computer-classic" />

  Download to Floppy
</button>

<br />

<i aria-label="Download to Floppy" class="fa-duotone fa-solid fa-computer-classic" />

<HTMLBlock>{`
<i aria-label="Download to Floppy" class="fa-duotone fa-solid fa-computer-classic"></i>
`}</HTMLBlock>

<br />

<i class="fa-duotone fa-solid fa-house" />

<i class="fa-duotone fa-solid fa-copyright" />

<i class="fa-duotone fa-solid fa-bomb" />

<i class="fa-duotone fa-solid fa-umbrella" />

<i class="fa-duotone fa-solid fa-paper-plane" />

<i class="fa-duotone fa-solid fa-computer-classic" />

<i class="fa-duotone fa-solid fa-crab" />

<i class="fa-duotone fa-solid fa-bullseye-pointer" />

<i class="fa-duotone fa-solid fa-wheelchair-move" />

<i class="fa-duotone fa-solid fa-table-tennis-paddle-ball" />

***

<br />

<Tabs>
  <Tab title="En web">
    * **Si se tiene desactivado el servicio de validación pago de terceros**. Se le pide al cliente ingresar su número de celular para solicitar el pago. Luego se le muestra en pantalla un instructivo para abrir su aplicación y aprobar el pago en la sección de **Aprobar compras**.
    * **Si se tiene activado el servicio de validación pago de terceros**. Se le pide al cliente confirmar su número de celular para solicitar el pago. Si los datos no coinciden, se le muestra un mensaje de error. Si los datos coinciden, se le manda la solicitud directamente a su aplicación de Yape (por notificación y correo). El cliente ingresa, ve en pantalla las solicitudes por aprobar, selecciona la indicada y hace clic en **Confirmar**.
  </Tab>

  <Tab title="En mobile">
    * **Si se tiene desactivado el servicio de validación pago de terceros:** El cliente ve el botón de **Abrir Yape**, el cual lo redireccionará a la aprobación del pago en su aplicación.
    * **Si se tiene activado el servicio de validación pago de terceros:** Se le pide al cliente confirmar su número de celular para solicitar el pago. Si los datos no coinciden, se le muestra un mensaje de error. Si los datos coinciden, se le manda la solicitud directamente a su aplicación de Yape (por notificación y correo). El cliente ingresa, ve en pantalla las solicitudes por aprobar, selecciona la indicada y hace clic en **Confirmar**.
  </Tab>
</Tabs>

***

# Embedded form

> This is a Embedded form for when platform is web and ui is embedded-form. View the full page at [https://docs.stripe.com/billing/subscriptions/build-subscriptions?platform=web\&ui=embedded-form](https://docs.stripe.com/billing/subscriptions/build-subscriptions?platform=web\&ui=embedded-form).

#### Integration effort

Complexity: 2/5

#### UI customization

Customize the appearance.

1. 1. **En web:**

<Cards columns={1}>
  <Card title="Si se tiene desactivado el servicio de validación pago de terceros">
    Se le pide al cliente ingresar su número de celular para solicitar el pago. Luego se le muestra en pantalla un instructivo para abrir su aplicación y aprobar el pago en la sección de **Aprobar compras**.
  </Card>
</Cards>

<Cards columns={1}>
  <Card title="Si se tiene activado el servicio de validación pago de terceros">
    Se le pide al cliente confirmar su número de celular para solicitar el pago. Si los datos no coinciden, se le muestra un mensaje de error. Si los datos coinciden, se le manda la solicitud directamente a su aplicación de Yape (por notificación y correo). El cliente ingresa, ve en pantalla las solicitudes por aprobar, selecciona la indicada y hace clic en **Confirmar**.
  </Card>
</Cards>

<br />

1. 1. **En web:**
      1. **Si se tiene desactivado el servicio de validación pago de terceros:** Se le pide al cliente ingresar su número de celular para solicitar el pago. Luego se le muestra en pantalla un instructivo para abrir su aplicación y aprobar el pago en la sección de **Aprobar compras**.
      2. **Si se tiene activado el servicio de validación pago de terceros:** Se le pide al cliente confirmar su número de celular para solicitar el pago. Si los datos no coinciden, se le muestra un mensaje de error. Si los datos coinciden, se le manda la solicitud directamente a su aplicación de Yape (por notificación y correo). El cliente ingresa, ve en pantalla las solicitudes por aprobar, selecciona la indicada y hace clic en **Confirmar**.
   2. **En mobile:**
      1. **Si se tiene desactivado el servicio de validación pago de terceros:** El cliente ve el botón de **Abrir Yape**, el cual lo redireccionará a la aprobación del pago en su aplicación.
      2. **Si se tiene activado el servicio de validación pago de terceros:** Se le pide al cliente confirmar su número de celular para solicitar el pago. Si los datos no coinciden, se le muestra un mensaje de error. Si los datos coinciden, se le manda la solicitud directamente a su aplicación de Yape (por notificación y correo). El cliente ingresa, ve en pantalla las solicitudes por aprobar, selecciona la indicada y hace clic en **Confirmar**.

<br />

<br />

<br />

1. **Validación.** Se valida que la información sea correcta, se hace el pago y el dinero se mueve desde la wallet del cliente hacia la cuenta de tu comercio.
2. **Confirmación.** Se le informa el resultado de la transacción al cliente. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

<br />

## Plugins

## 🔌 Nuestros plugins

Los plugins que ya están listos para ser integrados hoy en tu comercio son:

<Cards columns={3}>
  <Card href="https://docs.prontopaga.com/docs/prestashop#/" target="_blank">
    <img src="https://files.readme.io/dab29f87c4fd5dcf40c043bf9cb6ee7cdd6e26bd3d580ccb01010ae9e2b95fde-prestashop_alt_1.png" alt="PrestaShop" style={{ width: '150px', height: '40px', marginBottom: '0px' }} />

    <h3>PrestaShop</h3>
    Consulta su Guía de instalación y configuración aquí.
  </Card>

  <Card href="https://docs.prontopaga.com/docs/vtex#/" target="_blank">
    <img src="https://files.readme.io/0d7d83bbdaf7f085a281bd6340701a1b2cc12698fe8a9109964131c4b82af03c-VTEX.png" alt="VTEX" style={{ width: '100px', height: '40px', marginBottom: '0px' }} />

    <h3>VTEX</h3>
    Consulta su Guía de instalación y configuración aquí.
  </Card>

  <Card href="https://docs.prontopaga.com/docs/woocommerce#/" target="_blank">
    <img src="https://files.readme.io/b53455a90f631d51aa6cb66f51a5873c994374db04d4502f3fe5d2dc76f4e474-pngwing.com_1.png" alt="WooCommerce" style={{ width: '150px', height: '40px', marginBottom: '0px' }} />

    <h3>WooCommerce</h3>
    Consulta su Guía de instalación y configuración aquí.
  </Card>
</Cards>

<br />

## Listado de wallets

<Cards columns={7}>
  <Card href="https://docs.prontopaga.com/docs/vtex#/" target="_blank">
    <b>VTEX</b>
  </Card>

  <Card href="https://docs.prontopaga.com/docs/vtex#/" target="_blank">
    VTEX
  </Card>

  <Card href="https://docs.prontopaga.com/docs/vtex#/" target="_blank">
    VTEX
  </Card>

  <Card href="https://docs.prontopaga.com/docs/vtex#/" target="_blank">
    VTEX
  </Card>

  <Card href="https://docs.prontopaga.com/docs/vtex#/" target="_blank">
    VTEX
  </Card>

  <Card href="https://docs.prontopaga.com/docs/vtex#/" target="_blank">
    VTEX
  </Card>

  <Card href="https://docs.prontopaga.com/docs/vtex#/" target="_blank">
    VTEX
  </Card>
</Cards>

<br />

<Cards columns={1}>
  <Card href="https://docs.prontopaga.com/docs/prestashop#/" target="_blank">
    <img src="https://files.readme.io/dab29f87c4fd5dcf40c043bf9cb6ee7cdd6e26bd3d580ccb01010ae9e2b95fde-prestashop_alt_1.png" alt="PrestaShop" style={{ width: '150px', height: '40px', marginBottom: '0px' }} />

    <h3>PrestaShop</h3>
    Consulta su Guía de instalación y configuración aquí.
  </Card>
</Cards>

<Image align="center" src="https://files.readme.io/0622c4c5eda1747285ef87390e320dcf9dd1aafa518601634ce7c7b729d91a94-prestashop.svg" />

<br />

<Image align="center" width="100px" src="https://files.readme.io/3a3e686276c9c7fab0dc0141e3d54acb3ac6df6da8927c9d542647122dc0d5f0-62e3cccfd889babae63d7512.png" />

<Image align="center" width="100px" src="https://files.readme.io/78df363cf2ad4475247110eeb90f01bb65d460ba35e64bb1fa3522786854e1c0-prestashop_2.png" />

<Image align="center" width="100px" src="https://files.readme.io/237677136a29c3f87dc497f78202b9a0bbb30de9254062377c9db0957c278b13-Woo_logo_color.png" />

<Image align="center" width="100px" src="https://files.readme.io/57d885272860137bab59027756f4d031a8b0179f2ce91142ba94b7f2753e075e-pngwing.com.png" />

<Image align="center" width="100px" src="https://files.readme.io/0d7d83bbdaf7f085a281bd6340701a1b2cc12698fe8a9109964131c4b82af03c-VTEX.png" />

<Image align="center" src="https://files.readme.io/dab29f87c4fd5dcf40c043bf9cb6ee7cdd6e26bd3d580ccb01010ae9e2b95fde-prestashop_alt_1.png" />

<Image align="center" src="https://files.readme.io/0a3c6ce890a44d81d6d832d26dffa484af540dd475751964867802967698b7ee-62e3cccfd889babae63d7512_1.png" />

<Image align="center" src="https://files.readme.io/b53455a90f631d51aa6cb66f51a5873c994374db04d4502f3fe5d2dc76f4e474-pngwing.com_1.png" />

<Image align="center" src="https://files.readme.io/8d699661f5c1917560db8fb08ec0d4aa366ab62ed9f8482d6902d34315265307-Logo_rebel_1.png" />

<br />

## Pruebas QR

## QR con interfaz estándar (flujo completo)

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>QR con Interfaz Estándar</title>
  <style>
    .tabs {
      display: flex;
      cursor: pointer;
      margin-bottom: 10px;
    }
    .tabs div {
      padding: 10px 20px;
      background-color: #f1f1f1;
      margin-right: 5px;
      border: 1px solid #ccc;
      border-radius: 4px 4px 0 0;
    }
    .tabs div:hover {
      background-color: #ddd;
    }
    .tabs .active {
      background-color: #008CBA;
      color: white;
      border-bottom: none;
    }
    .tab-content {
      display: none;
      padding: 20px;
      border: 1px solid #ccc;
      border-top: none;
      border-radius: 0 0 4px 4px;
    }
    .tab-content.active {
      display: block;
    }
  </style>
</head>
<body>

  <h1>QR con Interfaz Estándar - Flujo Completo</h1>

  <div class="tabs">
    <div class="tab" onclick="showTab(1)">¿Cómo funciona?</div>
    <div class="tab" onclick="showTab(2)">Crea un nuevo pago</div>
    <div class="tab" onclick="showTab(3)">Firma de la transacción</div>
    <div class="tab" onclick="showTab(4)">Confirmación de un pago</div>
    <div class="tab" onclick="showTab(5)">Cancelar un pago con QR</div>
  </div>

  <div id="content1" class="tab-content">
    <h2>¿Cómo funciona?</h2>
    <p>Los pagos con QR son una forma de pago digital utilizada en Perú...</p>
    <ul>
      <li><strong>Selección de método:</strong> El cliente elige pagar con QR...</li>
      <li><strong>Generación del QR:</strong> ProntoPaga le entrega un QR único...</li>
      <li><strong>Pago en aplicación:</strong> El cliente escanea el código QR...</li>
      <li><strong>Confirmación:</strong> El cliente recibe una confirmación...</li>
    </ul>
  </div>

  <div id="content2" class="tab-content">
    <h2>Crea un nuevo pago</h2>
    <p>Tu front-end será el encargado de recopilar los datos necesarios...</p>
    <pre>
      JSON
      {
        "currency": "PEN",
        "country": "PE",
        "amount": "100.90",
        "clientName": "John Doe",
        ...
      }
    </pre>
  </div>

  <div id="content3" class="tab-content">
    <h2>Firma de la transacción</h2>
    <p>Para firmar los parámetros de la transacción, usa tu secretKey...</p>
  </div>

  <div id="content4" class="tab-content">
    <h2>Confirmación de un pago</h2>
    <p>Una vez completado el pago, recibirás los datos de la transacción...</p>
  </div>

  <div id="content5" class="tab-content">
    <h2>Cancelar un pago con QR</h2>
    <p>Si un cliente generó un QR pero no realizó el pago...</p>
  </div>

  <script>
    function showTab(tabIndex) {
      var contents = document.querySelectorAll('.tab-content');
      contents.forEach(function(content) {
        content.classList.remove('active');
      });

      var tabs = document.querySelectorAll('.tab');
      tabs.forEach(function(tab) {
        tab.classList.remove('active');
      });

      document.getElementById('content' + tabIndex).classList.add('active');
      tabs[tabIndex - 1].classList.add('active');
    }

    showTab(1);
  </script>

</body>
</html>
`}</HTMLBlock>

<br />

## Pruebas para página de cobertura

<HTMLBlock>{`
<details>
  <summary>🇧🇷 Brasil</summary>
  <p>A continuación, podrás ver listados los métodos con los que contamos en Argentina, tanto para PayIns como para PayOuts.</p>

  <div style="text-align: center;">
    <img 
      src="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" 
      alt="Argentina Coverage"
      style="width: 80%; max-width: 600px; height: auto; transition: all 0.3s ease;" 
      onmouseover="this.style.width='90%'" 
      onmouseout="this.style.width='80%'"
    />
  </div>
</details>
`}</HTMLBlock>

<Accordion title="🇦🇷 Argentina">
  A continuación, podrás ver listados los métodos con los que contamos en Argentina, tanto para PayIns como para PayOuts.

  <div style={{ textAlign: 'center', marginTop: '20px' }}>
    <img src="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" alt="Argentina Coverage" style={{ width: '100%', maxWidth: '500px', height: 'auto' }} />
  </div>
</Accordion>

<Accordion title="Argentina 🇦🇷">
  A continuación, podrás ver listados los métodos con los que contamos en Argentina, tanto para PayIns como para PayOuts.

  <div style={{ textAlign: 'center', marginTop: '20px' }}>
    <a href="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" target="_blank" rel="noopener noreferrer">
      <img src="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" alt="Argentina Coverage" style={{ width: '100%', maxWidth: '500px', height: 'auto', cursor: 'pointer' }} />
    </a>
  </div>
</Accordion>

<HTMLBlock>{`
<details>
  <summary style="font-size: 1.5rem; font-weight: bold;">🇧🇷 Brasil</summary>
  <p>A continuación, podrás ver listados los métodos con los que contamos en Argentina, tanto para PayIns como para PayOuts.</p>

  <div style="text-align: center; transition: all 0.3s ease;">
    <img 
      src="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" 
      alt="Brasil Coverage"
      style="width: 80%; max-width: 600px; height: auto; transition: all 0.3s ease;" 
    />
  </div>
</details>
`}</HTMLBlock>

<br />

<Accordion title="🇧🇷 Brasil">
  A continuación, podrás ver listados los métodos con los que contamos en Brasil, tanto para PayIns como para PayOuts.

  <div style={{ textAlign: 'center' }}>
    <a href="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" target="_blank">
      <img
        src="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png"
        alt="Brasil Coverage"
        style={{
          width: '80%',
          maxWidth: '1000px',
          height: 'auto',
          transition: 'all 0.3s ease'
        }}
        onMouseOver={(e) => (e.target.style.width = '100%')}
        onMouseOut={(e) => (e.target.style.width = '80%')}
      />
    </a>
  </div>
</Accordion>

***

<Accordion title="🇧🇷 Brasil">
  A continuación, podrás ver listados los métodos con los que contamos en Brasil, tanto para PayIns como para PayOuts.

  <div style={{ textAlign: 'center', marginTop: '20px' }}>
    <img src="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" alt="Brasil Coverage" style={{ width: '100%', maxWidth: '800px', height: 'auto' }} />
  </div>
</Accordion>

***

<Accordion title="🇧🇷 Brasil">
  A continuación, podrás ver listados los métodos con los que contamos en Argentina, tanto para PayIns como para PayOuts.

  <div style={{ textAlign: 'center', marginTop: '20px' }}>
    <a href="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" target="_blank">
      <img src="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" alt="Brasil Coverage" style={{ width: '100%', maxWidth: '800px', height: 'auto' }} />
    </a>
  </div>
</Accordion>

<br />

<HTMLBlock>{`
<details>
  <summary style="background-color: #FC2B5F; color: white; padding: 10px 20px; font-size: 1.5rem; font-weight: bold; border-radius: 5px; cursor: pointer;">
    🇧🇷 Brasil
  </summary>
  <p>A continuación, podrás ver listados los métodos con los que contamos en Argentina, tanto para PayIns como para PayOuts.</p>

  <div style="text-align: center; margin-top: 20px;">
    <a href="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" target="_blank">
      <img src="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" alt="Argentina Coverage" style="width: 100%; max-width: 800px; height: auto;" />
    </a>
  </div>
</details>
`}</HTMLBlock>

<br />

prueba 2

<HTMLBlock>{`
<details>
  <summary>🇧🇷 Brasil</summary>
  <p>A continuación, podrás ver listados los métodos con los que contamos en Argentina, tanto para PayIns como para PayOuts.</p>

  <div style="text-align: center;">
    <img 
      src="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" 
      alt="Argentina Coverage"
      style="width: 80%; max-width: 600px; height: auto; transition: all 0.3s ease;" 
      onmouseover="this.style.width='90%'" 
      onmouseout="this.style.width='80%'"
    />
  </div>
</details>
`}</HTMLBlock>

<br />

<HTMLBlock>{`
<details>
  <summary>🇧🇷 Brasil</summary>
  <p>A continuación, podrás ver listados los métodos con los que contamos en Brasil, tanto para PayIns como para PayOuts.</p>

  <div style="text-align: center;">
    <a href="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" target="_blank">
      <img 
        src="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" 
        alt="Brasil Coverage" 
        style="width: 80%; max-width: 800px; height: auto; transition: all 0.3s ease;" 
        onmouseover="this.style.width='150%'" 
        onmouseout="this.style.width='80%'"
      />
    </a>
  </div>
</details>
`}</HTMLBlock>

<HTMLBlock>{`
<details>
  <summary>🇧🇷 Brasil</summary>
  
  <h2>Métodos de pago en Brasil</h2>

  <p>A continuación, podrás ver listados los métodos con los que contamos en BR, tanto para PayIns como para PayOuts.</p>

  <div style="text-align: center;">
    <a href="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" target="_blank">
      <img 
        src="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" 
        alt="Brasil Coverage" 
        style="width: 80%; max-width: 800px; height: auto; transition: all 0.3s ease;" 
        onmouseover="this.style.width='100%'" 
        onmouseout="this.style.width='80%'"
      />
    </a>
  </div>
</details>
`}</HTMLBlock>

<HTMLBlock>{`
<details>
  <summary><h2>🇧🇷 Brasil</h2></summary>
  
  <p>A continuación, podrás ver listados los métodos con los que contamos en Brasil, tanto para PayIns como para PayOuts.</p>

  <div style="text-align: center;">
    <a href="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" target="_blank">
      <img 
        src="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" 
        alt="Brasil Coverage" 
        style="width: 80%; max-width: 800px; height: auto; transition: all 0.3s ease;" 
        onmouseover="this.style.width='100%'" 
        onmouseout="this.style.width='80%'"
      />
    </a>
  </div>
</details>
`}</HTMLBlock>

<HTMLBlock>{`
<details style="border: none;">
  <summary style="cursor: pointer; padding: 10px 0; background: none; border: none; outline: none; font-size: 20px;">
    <h2>🇧🇷 Brasil</h2>
  </summary>

  <p>A continuación, podrás ver listados los métodos con los que contamos en Argentina, tanto para PayIns como para PayOuts.</p>

  <div style="text-align: center;">
    <a href="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" target="_blank">
      <img 
        src="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" 
        alt="Brasil Coverage" 
        style="width: 80%; max-width: 800px; height: auto; transition: all 0.3s ease;" 
        onmouseover="this.style.width='90%'" 
        onmouseout="this.style.width='80%'"
      />
    </a>
  </div>
</details>
`}</HTMLBlock>

<HTMLBlock>{`
<details style="border: none;">
  <summary style="cursor: pointer; padding: 10px 0; background: none; border: none; outline: none; font-size: 20px; list-style: none;">
    <h2>🇧🇷 Brasil</h2>
  </summary>

  <p>A continuación, podrás ver listados los métodos con los que contamos en Argentina, tanto para PayIns como para PayOuts.</p>

  <div style="text-align: center;">
    <a href="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" target="_blank">
      <img 
        src="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" 
        alt="Brasil Coverage" 
        style="width: 80%; max-width: 800px; height: auto; transition: all 0.3s ease;" 
        onmouseover="this.style.width='90%'" 
        onmouseout="this.style.width='80%'"
      />
    </a>
  </div>
</details>
`}</HTMLBlock>

<HTMLBlock>{`
<details style="border: none;">
  <summary style="cursor: pointer; padding: 10px 0; background: none; border: none; outline: none; font-size: 20px; list-style: none;">
    <h3>🇧🇷 Brasil</h3>
  </summary>

  <p>A continuación, podrás ver listados los métodos con los que contamos en Argentina, tanto para PayIns como para PayOuts.</p>

  <div style="text-align: center;">
    <a href="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" target="_blank">
      <img 
        src="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" 
        alt="Brasil Coverage" 
        style="width: 80%; max-width: 1000px; height: auto; transition: all 0.3s ease;" 
        onmouseover="this.style.width='100%'" 
        onmouseout="this.style.width='80%'"
      />
    </a>
  </div>
</details>
`}</HTMLBlock>

2

<details style={{ border: 'none' }}>
  <summary
    style={{
      cursor: 'pointer',
      padding: '10px 0',
      background: 'none',
      border: 'none',
      outline: 'none',
      fontSize: '20px',
      listStyle: 'none'
    }}
  >
    <h1>🇧🇷 Brasil</h1>
  </summary>

  <p>A continuación, podrás ver listados los métodos con los que contamos en Argentina, tanto para PayIns como para PayOuts.</p>

  <div style={{ textAlign: 'center' }}>
    <a href="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" target="_blank">
      <img
        src="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png"
        alt="Brasil Coverage"
        style={{
          width: '80%',
          maxWidth: '1000px',
          height: 'auto',
          transition: 'all 0.3s ease'
        }}
        onMouseOver={(e) => (e.target.style.width = '100%')}
        onMouseOut={(e) => (e.target.style.width = '80%')}
      />
    </a>
  </div>
</details>

3

<br />

## 🇧🇷 Brasil

<details style={{ border: 'none' }}>
  <summary
    style={{
      cursor: 'pointer',
      padding: '10px 0',
      background: 'none',
      border: 'none',
      outline: 'none',
      fontSize: '20px',
      listStyle: 'none'
    }}
  >
    Conoce la cobertura en Brasil
  </summary>

  <p>A continuación, podrás ver listados los métodos con los que contamos en Argentina, tanto para PayIns como para PayOuts.</p>

  <div style={{ textAlign: 'center' }}>
    <a href="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" target="_blank">
      <img
        src="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png"
        alt="Brasil Coverage"
        style={{
          width: '80%',
          maxWidth: '1000px',
          height: 'auto',
          transition: 'all 0.3s ease'
        }}
        onMouseOver={(e) => (e.target.style.width = '100%')}
        onMouseOut={(e) => (e.target.style.width = '80%')}
      />
    </a>
  </div>
</details>

<br />

prueba 3

# prueba para página de wallet en Perú

<Cards columns={2}>
  <Card title="Botón Yape v1" href="https://docs.prontopaga.com/docs/bot%C3%B3n-yape#/" target="_blank">
    <img src="https://files.readme.io/93987a75250f9f38e0196e691806fd8b7fd6b99ef4baf51e766bae2b392d1cf2-yape-app-logo-png_seeklogo-399697.png" alt="Botón Yape v1" style={{ width: '40px', height: '40px', marginRight: '10px' }} />

    Integra pagos únicos con Botón Yape, tanto con iFrame, como sin iFrame.
  </Card>

  <Card title="Botón Yape: One Shot" href="https://docs.prontopaga.com/docs/yape-one-shot#/" target="_blank">
    <img src="https://files.readme.io/b0f30b97d8035a2f4387eaf8d715a913308b29e7a26c09df081e8ea99f4dc1a0-image.png" alt="Botón Yape: One Shot" style={{ width: '40px', height: '40px', marginRight: '10px' }} />

    Integra pagos únicos con Botón Yape, versión web y mobile.
  </Card>
</Cards>

![](https://files.readme.io/b0f30b97d8035a2f4387eaf8d715a913308b29e7a26c09df081e8ea99f4dc1a0-image.png)

<Image align="center" src="https://files.readme.io/93987a75250f9f38e0196e691806fd8b7fd6b99ef4baf51e766bae2b392d1cf2-yape-app-logo-png_seeklogo-399697.png" />

<br />

<Cards columns={2}>
  <Card href="https://docs.prontopaga.com/docs/bot%C3%B3n-yape#/" target="_blank">
    <img src="https://files.readme.io/93987a75250f9f38e0196e691806fd8b7fd6b99ef4baf51e766bae2b392d1cf2-yape-app-logo-png_seeklogo-399697.png" alt="Botón Yape v1" style={{ width: '40px', height: '40px', marginBottom: '0px' }} />

    <h3>Botón Yape v1</h3>
    Integra pagos únicos con Botón Yape, tanto con iFrame, como sin iFrame.
  </Card>

  <Card href="https://docs.prontopaga.com/docs/yape-one-shot#/" target="_blank">
    <img src="https://files.readme.io/93987a75250f9f38e0196e691806fd8b7fd6b99ef4baf51e766bae2b392d1cf2-yape-app-logo-png_seeklogo-399697.png" alt="Botón Yape: One Shot" style={{ width: '40px', height: '40px', marginBottom: '0px' }} />

    <h3>Botón Yape: One Shot</h3>
    Integra pagos únicos con Botón Yape, versión web y mobile.
  </Card>
</Cards>

<br />

<Cards columns={2}>
  <Card href="https://docs.prontopaga.com/docs/yape-on-file-ocp#/" target="_blank">
    <img src="https://files.readme.io/93987a75250f9f38e0196e691806fd8b7fd6b99ef4baf51e766bae2b392d1cf2-yape-app-logo-png_seeklogo-399697.png" alt="Yape On File: One Click Payments" style={{ width: '40px', height: '40px', marginBottom: '0px' }} />

    <h3>Yape On File: One Click Payments</h3>
    Realiza afiliaciones para que tus clientes puedan realizar pagos posteriores en un solo clic.
  </Card>

  <Card href="https://docs.prontopaga.com/docs/yape-on-file-recurrent#/" target="_blank">
    <img src="https://files.readme.io/93987a75250f9f38e0196e691806fd8b7fd6b99ef4baf51e766bae2b392d1cf2-yape-app-logo-png_seeklogo-399697.png" alt="Yape On File: Recurrencia" style={{ width: '40px', height: '40px', marginBottom: '0px' }} />

    <h3>Yape On File: Recurrencia</h3>
    Configura pagos recurrentes para los planes de suscripción que ofrece tu comercio.
  </Card>
</Cards>

<br />

***

# Opción 2

En **Payins**, se modifica el texto en:

1. El primer punto de la sección **Logotipos** (Agregar los logotipos de los diferentes métodos de pago...) y el segundo punto de la misma sección (Todos los nombres y logos de los métodos de pago...)
2. El segundo punto de la sección **Mensajes al usuario** (Montos mínimos y máximos permitidos para cada método de pago.)

En **Payouts**, se modifica el texto en:

1. El primer punto de la sección **Logotipos** (Agregar los logotipos de los diferentes métodos de retiro...) y el segundo punto de la misma sección (Todos los nombres y logos de los métodos de retiro...)
2. El segundo punto de la sección **Mensajes al usuario** (Montos mínimos y máximos permitidos para cada método de retiro.)

# Payins

## Certifica tu integración

La certificación de la integración en _sandbox_ es un paso obligatorio que todos los comercios deben realizar antes de recibir sus credenciales de producción. Su propósito es asegurar que la integración cumpla con los estándares técnicos, funcionales y de seguridad requeridos por ProntoPaga. Dentro de esta sección, se establecen los requisitos que deben cumplirse sin excepción para que la certificación sea aprobada.

### Requisitos de certificación

A continuación, encontrarás los distintos requisitos necesarios para completar tu certificación:

<Tabs>
  <Tab title="ID del cliente">
    * ❌ El DNI o RUT del cliente no debe ser modificable en ningún punto de la transacción.
    * ✅ Es recomendable que este dato no se muestre en el *checkout*. Solo puede estar disponible en la sección de perfil del usuario autenticado.
    * ⚠️ Esta medida tiene como objetivo prevenir fraudes y evitar que se realicen transacciones en nombre de terceros o menores de edad.
  </Tab>

  <Tab title="Logotipos">
    * 📥 Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu *front-end*. Puedes [descargarlos aquí](https://drive.google.com/uc?export=download\&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr).
    * 🔎 Todos los nombres y logos de los métodos de pago habilitados deben mostrarse de forma clara, sin modificaciones visuales o estilísticas que puedan generar confusión o inducir a errores.
    * ✅ Se recomienda ordenarlos según su popularidad o frecuencia de uso, para mejorar la experiencia del usuario y optimizar la conversión.
  </Tab>

  <Tab title="Mensajes al usuario">
    * ✅ El *checkout* debe incluir mensajes claros y visibles que orienten al usuario durante todo el proceso.

    ❗ Es obligatorio mostrar:

    * ℹ️ Montos mínimos y máximos permitidos para cada método de pago.
    * ℹ️ Estados transaccionales con claridad: por ejemplo, **Transacción aprobada** o **Transacción rechazada**, junto con una sugerencia de los pasos a seguir en caso de que corresponda.
  </Tab>

  <Tab title="Consideraciones importantes">
    * ❌ No almacenar datos sensibles del cliente en tu base de datos.
    * ✅ La certificación se otorga únicamente si estos requisitos se cumplen en su totalidad en el entorno de *sandbox*.
    * 💻 Una vez validada la integración, se habilitarán las credenciales para el entorno productivo.
    * ⚠️ El incumplimiento de estos requisitos podrá resultar en la denegación de la certificación.
  </Tab>
</Tabs>

<br />

# Payouts

## Certifica tu integración

La certificación de la integración en _sandbox_ es un paso obligatorio que todos los comercios deben realizar antes de recibir sus credenciales de producción. Su propósito es asegurar que la integración cumpla con los estándares técnicos, funcionales y de seguridad requeridos por ProntoPaga. Dentro de esta sección, se establecen los requisitos que deben cumplirse sin excepción para que la certificación sea aprobada.

### Requisitos de certificación

A continuación, encontrarás los distintos requisitos necesarios para completar tu certificación:

<Tabs>
  <Tab title="ID del cliente">
    * ❌ El DNI o RUT del cliente no debe ser modificable en ningún punto de la transacción.
    * ✅ Es recomendable que este dato no se muestre en el *checkout*. Solo puede estar disponible en la sección de perfil del usuario autenticado.
    * ⚠️ Esta medida tiene como objetivo prevenir fraudes y evitar que se realicen transacciones en nombre de terceros o menores de edad.
  </Tab>

  <Tab title="Logotipos">
    * 📥 Agregar los logotipos de los diferentes métodos de retiro de ProntoPaga a tu *front-end*. Puedes [descargarlos aquí](https://drive.google.com/uc?export=download\&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr).
    * 🔎 Todos los nombres y logos de los métodos de retiro habilitados deben mostrarse de forma clara, sin modificaciones visuales o estilísticas que puedan generar confusión o inducir a errores.
    * ✅ Se recomienda ordenarlos según su popularidad o frecuencia de uso, para mejorar la experiencia del usuario y optimizar la conversión.
  </Tab>

  <Tab title="Mensajes al usuario">
    * ✅ El *checkout* debe incluir mensajes claros y visibles que orienten al usuario durante todo el proceso.

    ❗ Es obligatorio mostrar:

    * ℹ️ Montos mínimos y máximos permitidos para cada método de retiro.
    * ℹ️ Estados transaccionales con claridad: por ejemplo, **Transacción aprobada** o **Transacción rechazada**, junto con una sugerencia de los pasos a seguir en caso de que corresponda.
  </Tab>

  <Tab title="Consideraciones importantes">
    * ❌ No almacenar datos sensibles del cliente en tu base de datos.
    * ✅ La certificación se otorga únicamente si estos requisitos se cumplen en su totalidad en el entorno de *sandbox*.
    * 💻 Una vez validada la integración, se habilitarán las credenciales para el entorno productivo.
    * ⚠️ El incumplimiento de estos requisitos podrá resultar en la denegación de la certificación.
  </Tab>
</Tabs>

<HTMLBlock>{`
<!DOCTYPE html>
<html>
<body>

<p><a href="https://prontopaga-api.postman.co/workspace/My-Workspace~068d4d0b-905b-44ad-851c-9b73e84c3e46/request/43701435-e1ffb35d-4335-41c8-8d54-2af3a75b10a2?action=share&source=copy-link&creator=43701435" target="_blank">
  <img src="https://run.pstmn.io/button.svg" alt="Run in Postman" style="width: 160px;">
</a></p>

</body>
</html>
`}</HTMLBlock>
