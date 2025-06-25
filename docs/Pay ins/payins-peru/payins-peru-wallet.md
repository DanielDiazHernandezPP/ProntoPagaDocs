---
title: Wallet
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    To create a wallet payment in Peru, customer data must be captured and a
    request made through the ProntoPaga API with a bearer token and a secret
    signature, ensuring secure and authenticated transactions.
  keywords:
    - wallet
    - ' wallet payment'
    - ' payin'
    - ' peru'
    - ' guide'
    - ' integration'
    - ' prontopaga'
    - ' how to make a wallet payment'
  robots: index
next:
  description: ''
---
Crear un pago por wallet en Perú consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un bearer token y una firma secreta. De esta forma, las transacciones se autentican y se realizan de forma segura.

## ¿Cómo funciona?

El proceso de pago con wallet en Perú consta de cinco etapas principales:

<Image align="center" src="https://files.readme.io/933d0090646d5cc0354e287b4d84eccd245130527f44959c81db060d5744af76-peru_-_04.jpg" />

1. **Selección de método.** El cliente elige pagar con wallet (Yape) en tu sitio web o aplicación. 
2. **Solicitud.** ProntoPaga se comunica con la wallet y genera la solicitud de pago.
3. **Aprobación.** Se le solicita al cliente un código de aprobación. Puede ingresar a su aplicación a través de un botón de acceso rápido, obtener el código y luego ingresarlo para aprobar el pago.
4. **Validación.** ProntoPaga valida que el código sea correcto. En caso de serlo, se hace el pago y el dinero se mueve desde la wallet del cliente hacia la cuenta de tu comercio. 
5. **Confirmación.** El cliente es redirigido a tu sitio y se muestra el resultado de la transacción. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

## Integración de Yape

Es posible integrar el servicio de pago con Botón Yape de dos formas en ProntoPaga:

* Usando nuestro iFrame para el front-end.
* Vía 100% API, sin usar nuestro iFrame (tu comercio tendrá el manejo total del front-end del checkout).

## Crea un nuevo pago con iFrame

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `yape_payment` como método de pago en el body de la solicitud.

La solicitud se envía con tu bearer token, así como con tu firma secreta. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros. 

<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

<NotaWebhooks />

### Personalización del formulario

Puedes ajustar la apariencia de tu formulario con el parámetro `theme` cambiando el color de fondo o creando versiones modo claro y modo oscuro.

<Image align="center" width="300px" src="https://files.readme.io/51e88becc4a1e257996cb45407d291f16c63f89f2a34baee995ee4a95f82c6ef-yapepersonaliz.png" />

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "currency": "PEN",
  "country": "PE",
  "amount": 100,
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "12345678912",
  "paymentMethod": "yape_payment",
  "urlConfirmation": "Webhook",
  "urlFinal": "example.com/successful",
  "urlRejected": "example.com/declined",
  "order": "1234",
  "theme": [
    {
      "bgColor": "transparent",
      "mode": "light"
    }
  ],
  "sign": "Signature of the parameters"
}
```

### Pago en la wallet

El cliente podrá continuar el proceso siguiendo las instrucciones en pantalla. Se redireccionará al cliente al sitio web o aplicación de la wallet, en donde podrá iniciar sesión y hacer el pago.

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un enlace para procesar el pago, así como un identificador de pago del sistema.

### Confirmación de un pago

Una vez que el usuario haya completado el pago, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`. 

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los pay ins](https://docs.prontopaga.com/docs/payins-status).

## Crea un nuevo pago sin iFrame

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `yape_payment` como método de pago en el body de la solicitud.

La solicitud se envía con tu bearer token, así como con tu firma secreta. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros. 

<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

<NotaWebhooks />

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "currency": "PEN",
  "country": "PE",
  "amount": 100,
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "12345678912",
  "paymentMethod": "yape_payment",
  "urlConfirmation": "Webhook",
  "urlFinal": "example.com/successful",
  "urlRejected": "example.com/declined",
  "order": "1234",
  "sign": "Signature of the parameters"
}
```

### Procesa el pago

Para procesar el pago creado con el endpoint anterior (sin usar nuestro iFrame), deberás consultar [este endpoint](https://docs.prontopaga.com/reference/create-payment-peru-yape-api) y enviar el`uid` del pago recién creado como path paramether. Ese `uid` se recibe como respuesta en la solicitud de crear un pago.

La solicitud para procesar un pago se envía con tu bearer token. Además, debes incluir los datos necesarios del cliente para procesar el pago, como: teléfono del cliente y código OTP.

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "phoneNumber": "999999999",
  "otp": 123456
}
```

> 🚧 Número de teléfono
>
> Tu comercio ya tiene registrado el número de teléfono del usuario (tu cliente) al crear el pago. Por lo que en este paso, recomendamos que el campo de teléfono **no sea editable en tu front-end.** Por lo tanto, el número de teléfono que se envíe en el request de este endpoint debe ser el mismo que el usado al crear el pago.

### Respuesta

Como respuesta a una solicitud de procesamiento de pago exitosa recibirás el `uid`, el estatus del pago, así como el tipo de acción (en este caso, API).

En caso de ocurrir un error, nuestro sistema te enviaré el código y mensaje de error, el cual podrás mostrar en tu front-end.

> 🚧 Tipos de rechazo y datos de prueba
>
> Consulta los posibles tipos de rechazo para este método, su código y detalle en [esta página](https://docs.prontopaga.com/docs/payins-rejections#yape---primarios). Además, consulta los datos de prueba con diferentes escenarios [aquí.](https://docs.prontopaga.com/docs/test-data-cards-peru#bot%C3%B3n-yape)

### Recomendaciones generales para tu front-end

Si estás integrando pagos con Yape sin nuestro iFrame, estas son algunas recomendaciones generales que te damos para construir el front-end de tu checkout:

* Que el logo de Yape aparezca hasta arriba.
* Que haya un texto describiendo brevemente lo que el cliente debe hacer.
* Que la zona para ingresar el celular esté separada en espacio para el código de país y espacio para el número de teléfono. 
* Que en la parte en donde se debe ingresar el OTP, el número de teléfono no sea editable (es decir, que sea el mismo que se mandó durante la creación del pago).
* Que el OTP valide que solo se puedan ingresar números, y que solo sean dígitos del 1 al 9, si se ajustan celdas una a una. También se puede crear una sola celda que valide que sean 6 dígitos numéricos máximo.
* Que exista un mensaje debajo del OTP, diciendo que pueden encontrar ese código en el menú de su aplicación de Yape. Para dispositivos móviles, agregar un deeplink de Yape al lado o debajo del OTP, con el mensaje "Abre tu Yape". Este deeplink redirecciona automáticamente al usuario a la sección de "Código de aprobación" de su aplicación de Yape. La URL del deeplink es: `https://www.yape.com.pe/app/checkout/approval_code`.
* Que el botón de pago diga "Yapear" en vez de "Pagar", para mayor personalización, así como el monto exacto.

Puedes ver un ejemplo de las anteriores recomendaciones aplicadas en esta imagen:

<Image align="center" width="300px" src="https://files.readme.io/933b1e6be8cf3243b46a018e64cf2c8f87c2ad05a2873fcfc4cc9579b6eed6b7-yapesintelef.jpg" />

## Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, también puedes hacer pruebas con [nuestros demos](https://demo.insospa.com/transactions/deposit).

## Antes de finalizar tu integración

Estos son algunos puntos importantes a tomar en cuenta, antes de finalizar tu integración con nosotros:

* No almacenar datos sensibles del cliente en tu base de datos.
* Enviar todos los datos requeridos en el body request del [endpoint de creación de pago](https://docs.prontopaga.com/reference/create-payment).
* Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu front-end. Puedes [descargarlos aquí](https://drive.google.com/uc?export=download\&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr).
