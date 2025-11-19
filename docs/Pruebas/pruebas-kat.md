---
title: Pagos con QR - Perú
excerpt: >-
  Documentación completa sobre la implementación de pagos con códigos QR en
  Perú, incluyendo flujo completo con interfaz estándar y QR embebido con datos
  únicamente.
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  robots: index
---
<Tabs>
  <Tab title="QR con interfaz estándar (flujo completo)">
    ## QR con interfaz estándar (flujo completo)

    Para quienes buscan una integración práctica y eficiente, contamos con una interfaz completamente lista para usar, que genera y muestra automáticamente el código QR al usuario final. Esta solución ofrece una experiencia visual atractiva, además de permitir hacer el monitoreo en tiempo real del estado del pago, facilitando así una implementación rápida sin comprometer la calidad ni la experiencia del usuario.

    ---

    ### ¿Cómo funciona?

    Los pagos con QR son una forma de pago digital utilizada en Perú que permite realizar transacciones escaneando un código QR desde una aplicación de billetera digital en el celular. Para utilizar este método, el cliente debe seleccionar la opción "Paga con QR", tener una cuenta activa en una billetera digital compatible y aprobar la transacción desde su aplicación. Para conocer el listado de billeteras disponibles, puedes consultarlo [aquí](https://docs.prontopaga.com/docs/payins-peru-qr#listado-de-wallets).

    El proceso de pago con QR en Perú consta de cuatro etapas principales:

    <Image align="center" border={false} src="https://files.readme.io/b2e065728089a44d6cc0c2806bd8eb118b1f570b023d80dabb029066cf433682-peru_-_05.jpg" />

    1. **Selección de método:** El cliente elige pagar con QR en tu sitio web o aplicación.
    2. **Generación del QR:** ProntoPaga le entrega un QR único al cliente, el cual podrá escanear con la aplicación de la wallet con la que pagará.
    3. **Pago en aplicación:** El cliente abre la aplicación de su wallet, escanea el código QR y hace el pago. El dinero se mueve desde la wallet del cliente hacia la cuenta de tu comercio.
    4. **Confirmación:** El cliente recibe una confirmación de pago exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación del pago a través de los webhooks que hayas configurado.

    ---

    ### Crea un nuevo pago (flujo completo)

    Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

    De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `pe_qr_payment` como método de pago en el body de la solicitud.

    La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros.

    También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

    > **Nota sobre la firma:** La firma de los parámetros es única para cada transacción. Conoce cómo firmar en [este artículo](https://docs.prontopaga.com/docs/sign-transactions).

    > **Nota sobre webhooks:** Los webhooks te permiten recibir notificaciones automáticas sobre el estado de las transacciones. Conoce más información en [este artículo](https://docs.prontopaga.com/docs/webhooks).

    #### Body de la solicitud

    ```json
    {
      "currency": "PEN",
      "country": "PE",
      "amount": "100.90",
      "clientName": "John Doe",
      "clientEmail": "johndoe@example.com",
      "clientPhone": "999999999",
      "clientDocument": "12345678912",
      "paymentMethod": "pe_qr_3_payment",
      "urlConfirmation": "https://www.webhook.com",
      "urlFinal": "https://sandbox.prontopaga.com/successful",
      "urlRejected": "https://sandbox.prontopaga.com/declined",
      "order": "XYZ789",
      "sign": "Signature of the parameters"
    }
    ```
  </Tab>

  <Tab title="QR embebido (solo datos QR)">
    ## QR embebido (solo datos QR)

    Si únicamente requieres el código QR en formato base64, esta opción es perfecta para ti. Está pensada especialmente para quienes ya cuentan con una interfaz personalizada o un flujo de usuario propio, y solo necesitan incorporar la imagen del QR en el lugar que más les convenga. Es una solución ideal si ya tienes resuelto el front-end y buscas simplemente insertar el QR sin complicaciones adicionales.

    > 🚧 **Monto no precargado**
    > 
    > Esta modalidad no carga automáticamente el monto en la wallet, por lo tanto, el cliente debe ingresarlo de manera manual.

    ---

    ### Crea un nuevo pago (solo datos QR)

    En esta modalidad, al hacer una solicitud de pago y mandar dentro del `"theme"` el parámetro `"type": "qr"`, los comercios recibirán en la respuesta de la solicitud el código QR, el cual podrán presentar directamente en su página web o aplicación, dentro de una etiqueta IMG.

    De este modo, para crear una solicitud de nuevo pago con este formato, deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `pe_qr_payment` como método de pago en el body de la solicitud.

    La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros.

    También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

    > **Nota sobre la firma:** La firma de los parámetros es única para cada transacción. Conoce cómo firmar en [este artículo](https://docs.prontopaga.com/docs/sign-transactions).

    > **Nota sobre webhooks:** Los webhooks te permiten recibir notificaciones automáticas sobre el estado de las transacciones. Conoce más información en [este artículo](https://docs.prontopaga.com/docs/webhooks).

    #### Body de la solicitud

    ```json
    {
      "currency": "PEN",
      "country": "PE",
      "amount": "100.90",
      "clientName": "John Doe",
      "clientEmail": "johndoe@example.com",
      "clientPhone": "999999999",
      "clientDocument": "12345678912",
      "paymentMethod": "pe_qr_3_payment",
      "urlConfirmation": "https://www.webhook.com",
      "urlFinal": "https://sandbox.prontopaga.com/successful",
      "urlRejected": "https://sandbox.prontopaga.com/declined",
      "order": "XYZ789",
      "theme": "{\"type\":\"qr\"}",
      "sign": "Signature of the parameters"
    }
    ```
  </Tab>
</Tabs>