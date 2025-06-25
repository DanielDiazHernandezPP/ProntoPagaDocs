---
title: PIX+ (Open Finance)
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    To create a payment in Brazil with PIX+, customer data must be captured and
    a request made through the API with a bearer token and a secret signature.
    Selection of a banking institution is also required.
  keywords:
    - open finance
    - ' pix'
    - ' pix plus'
    - ' brazil'
    - ' payment'
    - ' payin'
    - ' integration'
    - ' guide'
    - ' prontopaga'
  robots: index
next:
  description: ''
---
## PIX+ v1

Crear un pago en Brasil con PIX+ consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un bearer token y una firma secreta. De esta forma, las transacciones se autentican y se realizan de forma segura.

Además, todas tus transacciones cuentan con la herramienta automatizada Decision Manager (DM) del motor de gestión de riesgos y prevención de fraude de **Cybersource (A Visa Solution)**.

## ¿Cómo funciona?

El proceso de pago con PIX+ (Open Finance) consta de seis etapas principales:

<Image align="center" src="https://files.readme.io/5991e52161cfe59eff8a4a23a46b957a9e8494f8ab11e6f4e2460217d72bb434-Pipx-02.png" />

1. **Selección de método.** El cliente elige pagar con PIX+ (Open Finance) en tu sitio web o aplicación. 
2. **Listado de bancos.** Se le muestra un listado de bancos al cliente, en donde podrá seleccionar el que desee usar para hacer el pago. 
3. **Redirección al banco** Al seleccionar un banco, el cliente es redirigido a la aplicación del banco en su teléfono móvil.
4. **Pago en aplicación.** El cliente accede a la aplicación indicada y realiza el pago siguiendo las instrucciones en pantalla. 
5. **Captura.** El dinero se mueve desde el banco del cliente hacia la cuenta de tu comercio. 
6. **Confirmación.** El cliente recibe una confirmación de pago exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación del pago a través de los webhooks que hayas configurado.

### Crea un nuevo pago

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `belvo_payment` como método de pago en el body de la solicitud.

La solicitud se envía con tu bearer token, así como con tu firma secreta. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros. 

<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

<NotaWebhooks />

#### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "currency": "BRL",
  "country": "BR",
  "amount": 1000,
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "11111111111",
  "paymentMethod": "belvo_payment",
  "urlConfirmation": "Webhook",
  "urlFinal": "example.com/successful",
  "urlRejected": "example.com/declined",
  "order": "1234",
  "sing": "Signature of the parameters"
}
```

#### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un enlace para procesar el pago, así como un identificador de pago del sistema.

#### Confirmación de un pago

Una vez que el usuario haya completado el proceso de pago en el formulario, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`. 

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los pay ins](https://docs.prontopaga.com/docs/payins-status).

### Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, también puedes hacer pruebas con [nuestros demos](https://demo.insospa.com/transactions/deposit).

### Antes de finalizar tu integración

Estos son algunos puntos importantes a tomar en cuenta, antes de finalizar tu integración con nosotros:

* No almacenar datos sensibles del cliente en tu base de datos.
* Enviar todos los datos requeridos en el body request del [endpoint de creación de pago](https://docs.prontopaga.com/reference/create-payment).
* Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu front-end. Puedes [descargarlos aquí](https://prontopagalatam-my.sharepoint.com/:f:/g/personal/ana_escalante_prontopaga_com/EvoLzSVLQBtBtvUlXKCUPtkByzlMhjY7LLux9Dc6Dvmlzw?e=fMKXW0).

## PIX+ v2

Crear un pago en Brasil con PIX+ v2 consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un bearer token y una firma secreta. De esta forma, las transacciones se autentican y se realizan de forma segura. Además, implica seleccionar y enviar la institución bancaria de pago del cliente.

### 1. Crea un nuevo pago

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment-brazil-pixplusv2) y colocar `belvo_payment` como método de pago en el body de la solicitud.

La solicitud se envía con tu bearer token, así como con tu firma secreta. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros. 

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

#### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "currency": "BRL",
  "country": "BR",
  "amount": 1000,
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "12345678911",
  "paymentMethod": "belvo_payment",
  "urlConfirmation": "Webhook",
  "urlFinal": "example.com/successful",
  "urlRejected": "example.com/declined",
  "order": "1234",
  "sign": "Signature of the parameters"
}
```

#### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás una lista de instituciones bancarias, así como un identificador de pago del sistema.

### 2. Seleccionar institución

Una vez que el cliente selecciona el banco, deben enviar el id de la institución y el UID del pago en el endpoint de [Selección de institución de pago Brasil Pix+ v2](https://docs.prontopaga.com/reference/institution-brazil-pixplus-v2).

#### Respuesta

Como respuesta, recibirá una URL de pago en la institución bancaria, así como un identificador de pago en el sistema.

#### Confirmación de un pago

Una vez que el usuario haya completado el proceso de pago en el formulario, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`. 

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los pay ins](https://docs.prontopaga.com/docs/payins-status).

### Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, también puedes hacer pruebas con [nuestros demos](https://demo.insospa.com/transactions/deposit).

### Antes de finalizar tu integración

Estos son algunos puntos importantes a tomar en cuenta, antes de finalizar tu integración con nosotros:

* No almacenar datos sensibles del cliente en tu base de datos.
* Enviar todos los datos requeridos en el body request del [endpoint de creación de pago](https://docs.prontopaga.com/reference/create-payment-brazil-pixplusv2).
* Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu front-end. Puedes [descargarlos aquí](https://drive.google.com/uc?export=download\&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr).
