---
title: Cobertura por país
excerpt: Conoce la cobertura por país donde ProntoPaga opera.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
En este artículo, podrás revisar la cobertura que tenemos actualmente en los diversos países en los que operamos.

Puedes encontrar la cobertura en:

<Accordion title={<span style={{ fontSize: '20px', fontWeight: 'bold' }}>🇧🇷 Brasil</span>}>
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
          transition: 'all 0.4s ease'
        }}
        onMouseOver={(e) => (e.target.style.width = '100%')}
        onMouseOut={(e) => (e.target.style.width = '80%')}
      />
    </a>
  </div>
</Accordion>

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Accordion con Enlace</title>
    <style>
        .accordion {
            background-color: #f1f1f1;
            padding: 10px;
            font-size: 18px;
            cursor: pointer;
            border: none;
            text-align: left;
            outline: none;
            width: 100%;
            border-radius: 5px;
            margin: 5px 0;
        }
        .accordion:hover {
            background-color: #ddd;
        }

        .panel {
            padding: 0 18px;
            display: none;
            background-color: #f9f9f9;
            border: 1px solid #ddd;
            margin-top: 10px;
        }

        .image-container {
            text-align: center;
        }

        img {
            width: 80%;
            max-width: 1000px;
            cursor: pointer;
        }
    </style>
</head>
<body>

    <button class="accordion">🇧🇷 Brasil</button>
    <div class="panel">
        <p>A continuación, podrás ver listados los métodos con los que contamos en Brasil, tanto para PayIns como para PayOuts.</p>

        <div class="image-container">
            <a href="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" target="_blank">
                <img src="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" alt="Brasil Coverage">
            </a>
        </div>
    </div>

</body>
</html>
`}</HTMLBlock>

<br />

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Accordion con Enlace a Imagen</title>
    <style>
        .accordion {
            background-color: #f1f1f1;
            padding: 10px;
            font-size: 18px;
            cursor: pointer;
            border: none;
            text-align: left;
            outline: none;
            width: 100%;
            border-radius: 5px;
            margin: 5px 0;
        }

        .accordion:hover {
            background-color: #ddd;
        }

        .panel {
            padding: 0 18px;
            display: none;
            background-color: #f9f9f9;
            border: 1px solid #ddd;
            margin-top: 10px;
        }

        .image-container {
            text-align: center;
        }

        img {
            width: 80%;
            max-width: 1000px;
            transition: all 0.4s ease;
            cursor: pointer;
        }

        img:hover {
            width: 100%;
        }
    </style>
</head>
<body>

    <button class="accordion">🇧🇷 Brasil</button>
    <div class="panel">
        <p>A continuación, podrás ver listados los métodos con los que contamos en Brasil, tanto para PayIns como para PayOuts.</p>

        <div class="image-container">
            <a href="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" target="_blank">
                <img src="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" alt="Brasil Coverage" />
            </a>
        </div>
    </div>

    <script>
        var acc = document.getElementsByClassName("accordion");
        for (var i = 0; i < acc.length; i++) {
            acc[i].addEventListener("click", function() {
                this.classList.toggle("active");
                var panel = this.nextElementSibling;
                panel.style.display = panel.style.display === "block" ? "none" : "block";
            });
        }
    </script>

</body>
</html>
`}</HTMLBlock>