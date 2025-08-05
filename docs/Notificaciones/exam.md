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
\<Tabs>
&#x20; \<Tab title="Botón Yape v1">
Crear un pago por wallet en Perú consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un Bearer Token y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.

\*\*\*



\## ¿Cómo funciona?

Yape es una aplicación que permite realizar pagos y transferencias de dinero en Perú, utilizando solo el número de celular. Con Yape, los usuarios pueden hacer pagos en línea, recargar saldo en su cuenta o realizar compras en comercios afiliados. Para completar una transacción utilizando este método de pago, el cliente debe seleccionar la opción "Paga con Yape", tener una cuenta creada y aprobar la compra desde su aplicación.

El proceso de pago con wallet en Perú consta de cinco etapas principales:

\<Image align="center" src="https\://files.readme.io/933d0090646d5cc0354e287b4d84eccd245130527f44959c81db060d5744af76-peru\_-\_04.jpg" />

1\. \*\*Selección de método.\*\* El cliente elige pagar con wallet (Yape) en tu sitio web o aplicación.
2\. \*\*Solicitud.\*\* ProntoPaga se comunica con la wallet y genera la solicitud de pago.
3\. \*\*Aprobación.\*\* Se le solicita al cliente un código de aprobación. Puede ingresar a su aplicación a través de un botón de acceso rápido, obtener el código y luego ingresarlo para aprobar el pago.
4\. \*\*Validación.\*\* ProntoPaga valida que el código sea correcto. En caso de serlo, se hace el pago y el dinero se mueve desde la wallet del cliente hacia la cuenta de tu comercio.
5\. \*\*Confirmación.\*\* El cliente es redirigido a tu sitio y se muestra el resultado de la transacción. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

\*\*\*



\## Integración de Yape

Es posible integrar el servicio de pago con Botón Yape de dos formas en ProntoPaga:

\* Usando nuestro iFrame para el front-end.
\* Vía 100% API, sin usar nuestro iFrame (tu comercio tendrá el manejo total del front-end del checkout).

\*\*\*



\## Crea un nuevo pago con iFrame

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar \[este endpoint]\(https\://docs.prontopaga.com/reference/create-payment) y colocar \`yape\_payment\` como método de pago en el body de la solicitud.

La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros.

\<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

\<NotaWebhooks />



\### Personalización del formulario

Puedes ajustar la apariencia de tu formulario con el parámetro \`theme\` cambiando el color de fondo o creando versiones modo claro y modo oscuro.

\<Image align="center" width="200px" src="https\://files.readme.io/51e88becc4a1e257996cb45407d291f16c63f89f2a34baee995ee4a95f82c6ef-yapepersonaliz.png" />



\### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

\`\`\`json
\{
&#x20; "currency": "PEN",
&#x20; "country": "PE",
&#x20; "amount": "100.90",
&#x20; "clientName": "John Doe",
&#x20; "clientEmail": "johndoe\@example.com",
&#x20; "clientPhone": "999999999",
&#x20; "clientDocument": "12345678912",
&#x20; "paymentMethod": "yape\_payment",
&#x20; "urlConfirmation": "https\://www\.webhook.com",
&#x20; "urlFinal": "https\://sandbox.prontopaga.com/successful",
&#x20; "urlRejected": "https\://sandbox.prontopaga.com/declined",
&#x20; "order": "XYZ789",
&#x20; "theme": "\[\{\\"bgColor\\": \\"transparent\\", \\"mode\\": \\"dark\\"}]",
&#x20; "sign": "Signature of the parameters"
}
\`\`\`

\> 🚧 Límite transaccional
\>
\> Recuerda que el límite máximo por transacción y por día es de 2000 soles. Esto significa que, si un cliente realiza hoy una compra por ese monto, no podrá hacer otra transacción hasta mañana.



\### Pago en la wallet

El cliente podrá continuar el proceso siguiendo las instrucciones en pantalla. Se redireccionará al cliente al sitio web o aplicación de la wallet, en donde podrá iniciar sesión y hacer el pago.



\### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un enlace para procesar el pago, así como un identificador de pago del sistema.



\### Confirmación de un pago

Una vez que el usuario haya completado el pago, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en \`urlConfirmation\`.

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo \`status\` sea \`success\`.

Conoce todos los estados posibles de un pago en el siguiente enlace: \[Estados de los PayIns]\(https\://docs.prontopaga.com/docs/payins-status).

\*\*\*



\## Crea un nuevo pago sin iFrame

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar \[este endpoint]\(https\://docs.prontopaga.com/reference/create-payment) y colocar \`yape\_payment\` como método de pago en el body de la solicitud.

La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros.

\<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

\<NotaWebhooks />



\### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

\`\`\`json
\{
&#x20; "currency": "PEN",
&#x20; "country": "PE",
&#x20; "amount": "100.90",
&#x20; "clientName": "John Doe",
&#x20; "clientEmail": "johndoe\@example.com",
&#x20; "clientPhone": "999999999",
&#x20; "clientDocument": "12345678912",
&#x20; "paymentMethod": "yape\_payment",
&#x20; "urlConfirmation": "https\://www\.webhook.com",
&#x20; "urlFinal": "https\://sandbox.prontopaga.com/successful",
&#x20; "urlRejected": "https\://sandbox.prontopaga.com/declined",
&#x20; "order": "XYZ789",
&#x20; "sign": "Signature of the parameters"
}
\`\`\`



\### Procesa el pago

Para procesar el pago creado con el endpoint anterior (sin usar nuestro iFrame), deberás consultar \[este endpoint]\(https\://docs.prontopaga.com/reference/create-payment-peru-yape-api) y enviar el\`uid\` del pago recién creado como path paramether. Ese \`uid\` se recibe como respuesta en la solicitud de crear un pago.

La solicitud para procesar un pago se envía con tu Bearer Token. Además, debes incluir los datos necesarios del cliente para procesar el pago, como: teléfono del cliente y código OTP.



\### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

\`\`\`json
\{
&#x20; "phoneNumber": "999999999",
&#x20; "otp": 123456
}
\`\`\`

\> 🚧 Número de teléfono
\>
\> Tu comercio ya tiene registrado el número de teléfono del usuario (tu cliente) al crear el pago. Por lo que en este paso, recomendamos que el campo de teléfono \*\*no sea editable en tu front-end.\*\* Por lo tanto, el número de teléfono que se envíe en el request de este endpoint debe ser el mismo que el usado al crear el pago.



\### Respuesta

Como respuesta a una solicitud de procesamiento de pago exitosa recibirás el \`uid\`, el estatus del pago, así como el tipo de acción (en este caso, API).

En caso de ocurrir un error, nuestro sistema te enviaré el código y mensaje de error, el cual podrás mostrar en tu front-end.

\> 🚧 Tipos de rechazo y datos de prueba
\>
\> Consulta los posibles tipos de rechazo para este método, su código y detalle en \[esta página]\(https\://docs.prontopaga.com/docs/payins-rejections#yape---primarios). Además, consulta los datos de prueba con diferentes escenarios \[aquí.]\(https\://docs.prontopaga.com/docs/test-data-cards-peru#bot%C3%B3n-yape)



\### Recomendaciones generales para tu front-end

Si estás integrando pagos con Yape sin nuestro iFrame, estas son algunas recomendaciones generales que te damos para construir el front-end de tu checkout:

\* Que el logo de Yape aparezca hasta arriba.
\* Que haya un texto describiendo brevemente lo que el cliente debe hacer.
\* Que la zona para ingresar el celular esté separada en espacio para el código de país y espacio para el número de teléfono.
\* Que en la parte en donde se debe ingresar el OTP, el número de teléfono no sea editable (es decir, que sea el mismo que se mandó durante la creación del pago).
\* Que el OTP valide que solo se puedan ingresar números, y que solo sean dígitos del 1 al 9, si se ajustan celdas una a una. También se puede crear una sola celda que valide que sean 6 dígitos numéricos máximo.
\* Que exista un mensaje debajo del OTP, diciendo que pueden encontrar ese código en el menú de su aplicación de Yape. Para dispositivos móviles, agregar un deeplink de Yape al lado o debajo del OTP, con el mensaje "Abre tu Yape". Este deeplink redirecciona automáticamente al usuario a la sección de "Código de aprobación" de su aplicación de Yape. La URL del deeplink es: \`https\://www\.yape.com.pe/app/checkout/approval\_code\`.
\* Que el botón de pago diga "Yapear" en vez de "Pagar", para mayor personalización, así como el monto exacto.

Puedes ver un ejemplo de las anteriores recomendaciones aplicadas en esta imagen:

\<Image align="center" width="300px" src="https\://files.readme.io/933b1e6be8cf3243b46a018e64cf2c8f87c2ad05a2873fcfc4cc9579b6eed6b7-yapesintelef.jpg" />

\*\*\*  \</Tab>

&#x20; \<Tab title="Second Tab">
&#x20;   Here's content that's only inside the second Tab.
&#x20; \</Tab>

&#x20; \<Tab title="Third Tab">
&#x20;   Here's content that's only inside the third Tab.
&#x20; \</Tab>
\</Tabs>