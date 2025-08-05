---
title: exam
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
<HTMLBlock>{`
<details>
  <summary><strong>💳 Crear un pago por wallet en Perú</strong></summary>
  <p>Crear un pago por wallet en Perú consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un Bearer Token y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.</p>
</details>

<details>
  <summary><strong>📱 ¿Cómo funciona?</strong></summary>
  <p>Yape es una aplicación que permite realizar pagos y transferencias de dinero en Perú, utilizando solo el número de celular. Con Yape, los usuarios pueden hacer pagos en línea, recargar saldo en su cuenta o realizar compras en comercios afiliados. Para completar una transacción utilizando este método de pago, el cliente debe seleccionar la opción "Paga con Yape", tener una cuenta creada y aprobar la compra desde su aplicación.</p>
  <p>El proceso de pago con wallet en Perú consta de cinco etapas principales:</p>
  <ol>
    <li><strong>Selección de método.</strong> El cliente elige pagar con wallet (Yape) en tu sitio web o aplicación.</li>
    <li><strong>Solicitud.</strong> ProntoPaga se comunica con la wallet y genera la solicitud de pago.</li>
    <li><strong>Aprobación.</strong> Se le solicita al cliente un código de aprobación. Puede ingresar a su aplicación a través de un botón de acceso rápido, obtener el código y luego ingresarlo para aprobar el pago.</li>
    <li><strong>Validación.</strong> ProntoPaga valida que el código sea correcto. En caso de serlo, se hace el pago y el dinero se mueve desde la wallet del cliente hacia la cuenta de tu comercio.</li>
    <li><strong>Confirmación.</strong> El cliente es redirigido a tu sitio y se muestra el resultado de la transacción. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.</li>
  </ol>
  <img src="https://files.readme.io/933d0090646d5cc0354e287b4d84eccd245130527f44959c81db060d5744af76-peru_-_04.jpg" alt="Proceso de Yape" style="max-width: 100%; height: auto;" />
</details>

<details>
  <summary><strong>🔧 Integración de Yape</strong></summary>
  <p>Es posible integrar el servicio de pago con Botón Yape de dos formas en ProntoPaga:</p>
  <ul>
    <li>Usando nuestro iFrame para el front-end.</li>
    <li>Vía 100% API, sin usar nuestro iFrame (tu comercio tendrá el manejo total del front-end del checkout).</li>
  </ul>
</details>

<details>
  <summary><strong>🖥️ Crea un nuevo pago con iFrame</strong></summary>
  <p>Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.</p>
  <p>De este modo, para crear una solicitud de nuevo pago deberás usar <a href="https://docs.prontopaga.com/reference/create-payment">este endpoint</a> y colocar \`yape_payment\` como método de pago en el body de la solicitud.</p>
  <p><strong>Body de la solicitud</strong></p>
  <pre><code>
{
  "currency": "PEN",
  "country": "PE",
  "amount": "100.90",
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "12345678912",
  "paymentMethod": "yape_payment",
  "urlConfirmation": "https://www.webhook.com",
  "urlFinal": "https://sandbox.prontopaga.com/successful",
  "urlRejected": "https://sandbox.prontopaga.com/declined",
  "order": "XYZ789",
  "theme": "[{\"bgColor\": \"transparent\", \"mode\": \"dark\"}]",
  "sign": "Signature of the parameters"
}
  </code></pre>
</details>

<details>
  <summary><strong>🔑 Crea un nuevo pago sin iFrame</strong></summary>
  <p>Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.</p>
  <p>De este modo, para crear una solicitud de nuevo pago deberás usar <a href="https://docs.prontopaga.com/reference/create-payment">este endpoint</a> y colocar \`yape_payment\` como método de pago en el body de la solicitud.</p>
  <pre><code>
{
  "currency": "PEN",
  "country": "PE",
  "amount": "100.90",
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "12345678912",
  "paymentMethod": "yape_payment",
  "urlConfirmation": "https://www.webhook.com",
  "urlFinal": "https://sandbox.prontopaga.com/successful",
  "urlRejected": "https://sandbox.prontopaga.com/declined",
  "order": "XYZ789",
  "sign": "Signature of the parameters"
}
  </code></pre>
</details>

<details>
  <summary><strong>📊 Procesa el pago</strong></summary>
  <p>Para procesar el pago creado con el endpoint anterior (sin usar nuestro iFrame), deberás consultar <a href="https://docs.prontopaga.com/reference/create-payment-peru-yape-api">este endpoint</a> y enviar el \`uid\` del pago recién creado como path parameter. Ese \`uid\` se recibe como respuesta en la solicitud de crear un pago.</p>
  <p><strong>Body de la solicitud</strong></p>
  <pre><code>
{
  "phoneNumber": "999999999",
  "otp": 123456
}
  </code></pre>
</details>

<details>
  <summary><strong>🔍 Confirmación de un pago</strong></summary>
  <p>Una vez que el usuario haya completado el pago, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en \`urlConfirmation\`.</p>
  <p>Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo \`status\` sea \`success\`.</p>
  <p>Conoce todos los estados posibles de un pago en el siguiente enlace: <a href="https://docs.prontopaga.com/docs/payins-status">Estados de los PayIns</a>.</p>
</details>
`}</HTMLBlock>