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
<details open>
  <summary><strong>🇵🇪 Perú - Métodos de pago</strong></summary>

  <table border="1" style="width: 100%; table-layout: fixed;">
    <tr>
      <td style="width: 50%; padding: 10px;">
        <h2>¿Cómo funciona?</h2>
        <p>Yape es una aplicación que permite realizar pagos y transferencias de dinero en Perú, utilizando solo el número de celular. Con Yape, los usuarios pueden hacer pagos en línea, recargar saldo en su cuenta o realizar compras en comercios afiliados. Para completar una transacción utilizando este método de pago, el cliente debe seleccionar la opción "Paga con Yape", tener una cuenta creada y aprobar la compra desde su aplicación.</p>
        <p>El proceso de pago con wallet en Perú consta de cinco etapas principales:</p>
        <ol>
          <li><strong>Selección de método:</strong> El cliente elige pagar con wallet (Yape) en tu sitio web o aplicación.</li>
          <li><strong>Solicitud:</strong> ProntoPaga se comunica con la wallet y genera la solicitud de pago.</li>
          <li><strong>Aprobación:</strong> Se le solicita al cliente un código de aprobación. Puede ingresar a su aplicación a través de un botón de acceso rápido, obtener el código y luego ingresarlo para aprobar el pago.</li>
          <li><strong>Validación:</strong> ProntoPaga valida que el código sea correcto. En caso de serlo, se hace el pago y el dinero se mueve desde la wallet del cliente hacia la cuenta de tu comercio.</li>
          <li><strong>Confirmación:</strong> El cliente es redirigido a tu sitio y se muestra el resultado de la transacción. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.</li>
        </ol>
      </td>
      <td style="width: 50%; padding: 10px;">
        <h2>Integración de Yape</h2>
        <p>Es posible integrar el servicio de pago con Botón Yape de dos formas en ProntoPaga:</p>
        <ul>
          <li>Usando nuestro iFrame para el front-end.</li>
          <li>Vía 100% API, sin usar nuestro iFrame (tu comercio tendrá el manejo total del front-end del checkout).</li>
        </ul>

        <h3>Crea un nuevo pago con iFrame</h3>
        <p>Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.</p>

        <h3>Body de la solicitud:</h3>
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
      </td>
    </tr>
  </table>
</details>
`}</HTMLBlock>