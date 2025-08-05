---
title: pruebas Kat
deprecated: false
hidden: true
metadata:
  robots: index
---
## Pruebas para página de cobertura

<Accordion title="Argentina" icon="fa-info-circle">
  A continuación, podrás ver listados los métodos con los que contamos en Argentina, tanto para PayIns como para PayOuts.
</Accordion>

<Accordion title="🇦🇷 Argentina">
  A continuación, podrás ver listados los métodos con los que contamos en Argentina, tanto para PayIns como para PayOuts.
</Accordion>

<Accordion title="🇦🇷Argentina">
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

<Accordion title="🇧🇷 Brasil">
  A continuación, podrás ver listados los métodos con los que contamos en Argentina, tanto para PayIns como para PayOuts.

  <div style={{ textAlign: 'center', marginTop: '20px' }}>
    <img src="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" alt="Argentina Coverage" style={{ width: '100%', maxWidth: '800px', height: 'auto' }} />
  </div>
</Accordion>

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Imagen Clickeable y Ampliable</title>
  <style>
    /* Estilos generales */
    .accordion-content {
      padding: 20px;
      background-color: #f9f9f9;
      border-radius: 5px;
    }

    /* Contenedor de la imagen */
    .image-container {
      text-align: center;
      margin-top: 20px;
    }

    .image-container img {
      width: 100%;
      max-width: 500px;
      height: auto;
      cursor: pointer;
      transition: transform 0.3s ease;
    }

    /* Estilo para el modal de imagen ampliada */
    .modal {
      display: none; /* Ocultamos el modal por defecto */
      position: fixed;
      z-index: 1;
      left: 0;
      top: 0;
      width: 100%;
      h
`}</HTMLBlock>

<HTMLBlock>{`
<Shelf classname="platform_shelf">
  <YunoCard title="Web" href="/docs/full-checkout-sdk" />

  <YunoCard title="iOS" href="/docs/full-checkout-ios" />

  <YunoCard title="Android" href="/docs/full-checkout-android" />

  <YunoCard title="Flutter" href="/docs/full-sdk-flutter" />
</Shelf>
`}</HTMLBlock>

<br />

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Imagen Clickeable con HTML y CSS</title>
  <style>
    /* Estilos generales */
    .accordion-content {
      padding: 20px;
      background-color: #f9f9f9;
      border-radius: 5px;
    }

    /* Contenedor de la imagen */
    .image-container {
      text-align: center;
      margin-top: 20px;
    }

    .image-container a {
      display: inline-block;
      width: 100%;
      max-width: 500px;
      height: auto;
      text-decoration: none;
    }

    .image-container img {
      width: 100%;
      height: auto;
      transition: transform 0.3s, box-shadow 0.3s;
      cursor: pointer;
    }

    /* Efecto cuando se pasa el ratón (hover) sobre la imagen */
    .image-container a:hover img {
      transform: scale(1.05); /* Aumenta ligeramente la imagen */
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3); /* Agrega sombra */
    }

    /* Estilos para el texto adicional */
    .additional-content {
      display: none;
      text-align: center;
      margin-top: 20px;
    }

    /* Estilo para el texto cuando se hace clic (simulado por anidar en enlace) */
    .image-container a:focus + .additional-content,
    .image-container a:hover + .additional-content {
      display: block;
    }
  </style>
</head>
<body>

  <div class="accordion-content">
    <h2>Argentina</h2>
    Lorem ipsum dolor sit amet, **consectetur adipiscing elit.** Ut enim
    ad minim veniam, quis nostrud exercitation ullamco. Excepteur sint
    occaecat cupidatat non proident!

    <!-- Imagen clickeable, usando enlace -->
    <div class="image-container">
      <a href="#">
        <img 
          src="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" 
          alt="Argentina Coverage"
        />
      </a>
    </div>

    <!-- Contenido adicional que se muestra al hacer clic o pasar el ratón -->
    <div class="additional-content">
      <p>¡Haz clic en la imagen para mostrar u ocultar este texto adicional!</p>
    </div>
  </div>

</body>
</html>
`}</HTMLBlock>

<br />

# Opción 1

Se utiliza el mismo texto tanto para payins y payouts, ambos son casi iguales, solo se diferencian por lo siguiente:

1. El primer punto de la sección **Logotipos** (Agregar los logotipos de los diferentes métodos de pago y/o retiro...) y el segundo punto de la misma sección (Todos los nombres y logos de los métodos de pago y/o retiro...)
2. El segundo punto de la sección **Mensajes al usuario** (Montos mínimos y máximos permitidos para cada método de pago y/o retiro.)

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
    * 📥 Agregar los logotipos de los diferentes métodos de pago y/o retiro de ProntoPaga a tu *front-end*. Puedes [descargarlos aquí](https://drive.google.com/uc?export=download\&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr).
    * 🔎 Todos los nombres y logos de los métodos de pago y/o retiro habilitados deben mostrarse de forma clara, sin modificaciones visuales o estilísticas que puedan generar confusión o inducir a errores.
    * ✅ Se recomienda ordenarlos según su popularidad o frecuencia de uso, para mejorar la experiencia del usuario y optimizar la conversión.
  </Tab>

  <Tab title="Mensajes al usuario">
    * ✅ El *checkout* debe incluir mensajes claros y visibles que orienten al usuario durante todo el proceso.

    ❗ Es obligatorio mostrar:

    * ℹ️ Montos mínimos y máximos permitidos para cada método de pago y/o retiro.
    * ℹ️ Estados transaccionales con claridad: por ejemplo, **Transacción aprobada** o **Transacción rechazada**, junto con una sugerencia de los pasos a seguir en caso de que corresponda.
  </Tab>

  <Tab title="Consideraciones importantes">
    * ❌ No almacenar datos sensibles del cliente en tu base de datos.
    * ✅ La certificación se otorga únicamente si estos requisitos se cumplen en su totalidad en el entorno de *sandbox*.
    * 💻 Una vez validada la integración, se habilitarán las credenciales para el entorno productivo.
    * ⚠️ El incumplimiento de estos requisitos podrá resultar en la denegación de la certificación.
  </Tab>
</Tabs>

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