---
title: Tests Varios
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Links descargables

<a href="https://drive.google.com/uc?export=download&id=1AIX6qYYGY1ALMy2ez3wzqtUxFUf2fp6r" download>Descarga los logos</a>

<a href="https://drive.google.com/uc?export=download&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr" download>Descarga los logos2</a>

<div class="enlace">
  [Descarga solo texto](https://drive.google.com/uc?export=download\&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr)
</div>

## Espacios en tablas

<div class="table-five-columns">
  **Tabla 1**

  | Escenario                        | Número           | Mes / año | CVV | Código de acción |
  | :------------------------------- | :--------------- | :-------- | :-- | :--------------- |
  | Venta exitosa – con cuotas       | 4551708161768059 | 03/2028   | 111 | 000              |
  | Venta exitosa – afiliación a REC | 4474118355632240 | 03/2028   | 000 | 000              |

  **Tabla 2**

  | Escenario                  | Número           | Mes / año | CVV | Código |
  | :------------------------- | :--------------- | :-------- | :-- | :----- |
  | Venta exitosa – con cuotas | 4551708161768059 | 03/2028   | 111 | 2      |
  | Venta exitosa – sin cuotas | 4474118355632240 | 03/2028   | 000 | 3      |
</div>

<br />

///

<h2>HOLA</h2>

> 📘 ASAA
>
> CAsa

<NotaFirma />

<br />

<Image align="center" src="https://files.readme.io/6e52a1e15051ba76b3802d4441bb26ef72f064dd19b315f052b69d39f626d45f-image_15.png" />

<br />

> 📘 ASAA
>
> CAsa

<br />

## Menú desplegable

<details>
  <summary><h2>Requisitos</h2></summary>

  <p>ID del cliente:</p>

  <ul>
    <li>DNI</li>
    <li>RUT</li>
  </ul>
</details>

\<!DOCTYPE html>

\<html lang="es">
\<head>
&#x20; \<meta charset="UTF-8">
&#x20; \<meta name="viewport" content="width=device-width, initial-scale=1.0">
&#x20; \<title>Detalles del Cliente\</title>
&#x20; \<style>
&#x20;   .content \{
&#x20;     display: none;
&#x20;     margin-top: 10px;
&#x20;     margin-left: 20px;
&#x20;   }

&#x20;   .button \{
&#x20;     font-size: 18px;
&#x20;     font-weight: bold;
&#x20;     background-color: #f1f1f1;
&#x20;     padding: 10px;
&#x20;     cursor: pointer;
&#x20;     border: 1px solid #ccc;
&#x20;     border-radius: 5px;
&#x20;     transition: background-color 0.3s ease;
&#x20;   }

&#x20;   .button:hover \{
&#x20;     background-color: #e0e0e0;
&#x20;   }

&#x20;   .open .content \{
&#x20;     display: block;
&#x20;   }
&#x20; \</style>
\</head>
\<body>
&#x20; \<div id="client-info" class="button" onclick="toggleContent()">
&#x20;   ID del cliente
&#x20; \</div>
&#x20; \<div class="content">
&#x20;   \<ul>
&#x20;     \<li>DNI\</li>
&#x20;     \<li>RUT\</li>
&#x20;   \</ul>
&#x20; \</div>

&#x20; \<script>
&#x20;   function toggleContent() \{
&#x20;     var content = document.querySelector('.content');
&#x20;     content.style.display = (content.style.display === 'block') ? 'none' : 'block';
&#x20;   }
&#x20; \</script>
\</body>
\</html>