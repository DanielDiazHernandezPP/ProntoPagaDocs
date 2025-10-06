---
title: pruebas Kat
deprecated: false
hidden: true
metadata:
  robots: index
---
<br />

<Cards>
  <ImageCard imageSrc="https://fastly.picsum.photos/id/102/1200/600.jpg?hmac=QNclXkIUydKOl9ZYpra9E-8Z78ef-xI9KvZoBaUC8KI" imageAlt="Test data CL" title="Datos de prueba Chile" description="Conoce los datos de prueba disponibles para Chile." />

  <ImageCard imageSrc="https://fastly.picsum.photos/id/102/1200/600.jpg?hmac=QNclXkIUydKOl9ZYpra9E-8Z78ef-xI9KvZoBaUC8KI" imageAlt="Placeholder Image" title="Acepta pagos con tarjeta" description="Acepta pagos con tarjeta online de manera segura." />
</Cards>

***

<br />

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

**🌐 En web:**

<Cards columns={2}>
  <Card title="Si se tiene desactivado el servicio de validación pago de terceros">
    Se le pide al cliente ingresar su número de celular para solicitar el pago. Luego se le muestra en pantalla un instructivo para abrir su aplicación y aprobar el pago en la sección de **Aprobar compras**.
  </Card>

  <Card title="Si se tiene activado el servicio de validación pago de terceros">
    Se le pide al cliente confirmar su número de celular para solicitar el pago. Si los datos no coinciden, se le muestra un mensaje de error. Si los datos coinciden, se le manda la solicitud directamente a su aplicación de Yape (por notificación y correo). El cliente ingresa, ve en pantalla las solicitudes por aprobar, selecciona la indicada y hace clic en **Confirmar**.
  </Card>
</Cards>

**📱En mobile:**

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

<Image align="center" border={false} src="https://files.readme.io/0622c4c5eda1747285ef87390e320dcf9dd1aafa518601634ce7c7b729d91a94-prestashop.svg" />

<br />

<Image align="center" border={false} width="100px" src="https://files.readme.io/3a3e686276c9c7fab0dc0141e3d54acb3ac6df6da8927c9d542647122dc0d5f0-62e3cccfd889babae63d7512.png" />

<Image align="center" border={false} width="100px" src="https://files.readme.io/78df363cf2ad4475247110eeb90f01bb65d460ba35e64bb1fa3522786854e1c0-prestashop_2.png" />

<Image align="center" border={false} width="100px" src="https://files.readme.io/237677136a29c3f87dc497f78202b9a0bbb30de9254062377c9db0957c278b13-Woo_logo_color.png" />

<Image align="center" border={false} width="100px" src="https://files.readme.io/57d885272860137bab59027756f4d031a8b0179f2ce91142ba94b7f2753e075e-pngwing.com.png" />

<Image align="center" border={false} width="100px" src="https://files.readme.io/0d7d83bbdaf7f085a281bd6340701a1b2cc12698fe8a9109964131c4b82af03c-VTEX.png" />

<Image align="center" border={false} src="https://files.readme.io/dab29f87c4fd5dcf40c043bf9cb6ee7cdd6e26bd3d580ccb01010ae9e2b95fde-prestashop_alt_1.png" />

<Image align="center" border={false} src="https://files.readme.io/0a3c6ce890a44d81d6d832d26dffa484af540dd475751964867802967698b7ee-62e3cccfd889babae63d7512_1.png" />

<Image align="center" border={false} src="https://files.readme.io/b53455a90f631d51aa6cb66f51a5873c994374db04d4502f3fe5d2dc76f4e474-pngwing.com_1.png" />

<Image align="center" border={false} src="https://files.readme.io/8d699661f5c1917560db8fb08ec0d4aa366ab62ed9f8482d6902d34315265307-Logo_rebel_1.png" />

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

<Image border={false} src="https://files.readme.io/b0f30b97d8035a2f4387eaf8d715a913308b29e7a26c09df081e8ea99f4dc1a0-image.png" />

<Image align="center" border={false} src="https://files.readme.io/93987a75250f9f38e0196e691806fd8b7fd6b99ef4baf51e766bae2b392d1cf2-yape-app-logo-png_seeklogo-399697.png" />

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
