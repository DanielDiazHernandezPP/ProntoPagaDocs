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
    <title>Accordion con Modal</title>
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

        /* Modal */
        #modal {
            display: none;
        }

        #modal:checked + #myModal {
            display: block;
        }

        #myModal {
            display: none;
            position: fixed;
            z-index: 1;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgba(0, 0, 0, 0.5);
        }

        .modal-content {
            margin: 15% auto;
            background-color: #fff;
            padding: 20px;
            border: 1px solid #888;
            width: 80%;
            max-width: 1000px;
        }

        .close {
            color: #aaa;
            font-size: 28px;
            font-weight: bold;
            cursor: pointer;
            float: right;
        }

        .close:hover,
        .close:focus {
            color: black;
        }
    </style>
</head>
<body>

    <button class="accordion">🇧🇷 Brasil</button>
    <div class="panel">
        <p>A continuación, podrás ver listados los métodos con los que contamos en Brasil, tanto para PayIns como para PayOuts.</p>

        <div class="image-container">
            <label for="modal" style="cursor: pointer;">
                <img src="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" alt="Brasil Coverage" />
            </label>
        </div>
    </div>

    <!-- Checkbox control para el modal -->
    <input type="checkbox" id="modal" style="display: none;">
    <div id="myModal">
        <div class="modal-content">
            <label for="modal" class="close">&times;</label>
            <img src="https://files.readme.io/93a3a7f8c03fd798a0c78d35305272338b69d3d2e657d7bb54bf962eefdedd2a-Coverage_in_Brazil_2.png" alt="Brasil Coverage" style="width: 100%; height: auto;">
        </div>
    </div>

</body>
</html>
`}</HTMLBlock>