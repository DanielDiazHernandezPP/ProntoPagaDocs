---
title: pruebas Kat
deprecated: false
hidden: true
metadata:
  robots: index
---
## Plugins

## 🔌 Nuestros plugins

Los plugins que ya están listos para ser integrados hoy en tu comercio son:

<Cards columns={3}>
  <Card href="https://docs.prontopaga.com/docs/bot%C3%B3n-yape#/" target="_blank">
    <img src="https://files.readme.io/c48e4837a11586eda43c828678b9ff33375a59ba5ba65606c789ffe4246abe00-Prestashop.png" alt="PrestaShop" style={{ width: '90px', height: '40px', marginBottom: '0px' }} />

    <h3>PrestaShop</h3>
    Consulta su Guía de instalación y configuración aquí.
  </Card>

  <Card href="https://docs.prontopaga.com/docs/bot%C3%B3n-yape#/" target="_blank">
    <img src="https://files.readme.io/0d7d83bbdaf7f085a281bd6340701a1b2cc12698fe8a9109964131c4b82af03c-VTEX.png" alt="VTEX" style={{ width: '90px', height: '40px', marginBottom: '0px' }} />

    <h3>VTEX</h3>
    Consulta su Guía de instalación y configuración aquí.
  </Card>

  <Card href="https://docs.prontopaga.com/docs/yape-one-shot#/" target="_blank">
    <img src="https://files.readme.io/57d885272860137bab59027756f4d031a8b0179f2ce91142ba94b7f2753e075e-pngwing.com.png" alt="Botón Yape: One Shot" style={{ width: '90px', height: '40px', marginBottom: '0px' }} />

    <h3>WooCommerce</h3>
    Consulta su Guía de instalación y configuración aquí.
  </Card>
</Cards>

<Image align="center" src="https://files.readme.io/57d885272860137bab59027756f4d031a8b0179f2ce91142ba94b7f2753e075e-pngwing.com.png" />

<Image align="center" src="https://files.readme.io/0d7d83bbdaf7f085a281bd6340701a1b2cc12698fe8a9109964131c4b82af03c-VTEX.png" />

<br />

<Image align="center" src="https://files.readme.io/c48e4837a11586eda43c828678b9ff33375a59ba5ba65606c789ffe4246abe00-Prestashop.png" />

<br />

<br />

<br />

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
    <!-- Enlace clickeable a la imagen en su tamaño completo -->
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

La certificación de la integración en *sandbox* es un paso obligatorio que todos los comercios deben realizar antes de recibir sus credenciales de producción. Su propósito es asegurar que la integración cumpla con los estándares técnicos, funcionales y de seguridad requeridos por ProntoPaga. Dentro de esta sección, se establecen los requisitos que deben cumplirse sin excepción para que la certificación sea aprobada.

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

La certificación de la integración en *sandbox* es un paso obligatorio que todos los comercios deben realizar antes de recibir sus credenciales de producción. Su propósito es asegurar que la integración cumpla con los estándares técnicos, funcionales y de seguridad requeridos por ProntoPaga. Dentro de esta sección, se establecen los requisitos que deben cumplirse sin excepción para que la certificación sea aprobada.

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