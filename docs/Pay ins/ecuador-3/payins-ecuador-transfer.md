---
title: Transferencia (Paga con Tu Banco)
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    To create a payment in Ecuador via bank transfer, customer data must be
    captured and a request made through the API with a bearer token and a secret
    signature. The process includes collecting data on the front-end, processing
    the payment on the back-end, and confirming the transaction via webhooks,
    with testing options available to verify the integration.
  keywords:
    - transfer
    - ' bank'
    - ' bank transfer'
    - ' wire transfer'
    - ' payin'
    - ' bank payment'
    - ' guide'
    - ' integration'
    - ' ecuador'
    - ' prontopaga'
    - ' how to make a wire transfer'
  robots: index
next:
  description: ''
---
Crear un pago en Ecuador por medio de transferencia bancaria consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un bearer token y una firma secreta. De esta forma, las transacciones se autentican y se realizan de forma segura.

Además, todas tus transacciones cuentan con la herramienta automatizada Decision Manager (DM) del motor de gestión de riesgos y prevención de fraude de **Cybersource (A Visa Solution)**.

## ¿Cómo funciona?

El proceso de pago con transferencia en Ecuador consta de cuatro etapas principales:

<Image align="center" src="https://files.readme.io/1928bc5ac79a084a9b25b4050ef0d51c71bd6f063ed7cd89e36bac84b509a3a0-Ecuador_-_02.jpg" />

<br />

1. **Selección de método.** El cliente elige pagar con transferencia en tu sitio web o aplicación. 
2. **Selección de banco.** Se le muestra un listado de bancos al cliente, en donde podrá seleccionar el suyo 
3. **Redirección.** El cliente es redirigido al portal de su banco, en donde deberá iniciar sesión y seguir las instrucciones en pantalla para hacer la transferencia. El dinero se mueve desde el banco del cliente hacia la cuenta de tu comercio.
4. **Confirmación.** El cliente es redirigido a tu sitio y se muestra el resultado de la transacción. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

## Crea un nuevo pago

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `PagaConTuBanco` como método de pago en el body de la solicitud.

<NotaFirma />

La solicitud se envía con tu bearer token, así como con tu firma secreta. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros. 

<NotaWebhooks />

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "currency": "USD",
  "country": "EC",
  "amount": 10,
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "12345678912",
  "paymentMethod": "PagaConTuBanco",
  "urlConfirmation": "Webhook",
  "urlFinal": "example.com/successful",
  "urlRejected": "example.com/declined",
  "order": "1234",
  "sing": "Signature of the parameters"
}
```

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un enlace para procesar el pago, así como un identificador de pago del sistema.

### Pago en el banco

El cliente podrá continuar el proceso siguiendo las instrucciones en pantalla. Se redireccionará al cliente al sitio web de la institución bancaria que haya seleccionado para pagar, en donde podrá iniciar sesión y hacer la transferencia.

### Confirmación de un pago

Una vez que el usuario haya completado el proceso de pago en su banco, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`. 

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los pay ins](https://docs.prontopaga.com/docs/payins-status).

## Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, también puedes hacer pruebas con [nuestros demos](https://demo.insospa.com/transactions/deposit).

## Antes de finalizar tu integración

Estos son algunos puntos importantes a tomar en cuenta, antes de finalizar tu integración con nosotros:

* No almacenar datos sensibles del cliente en tu base de datos.
* Enviar todos los datos requeridos en el body request del [endpoint de creación de pago](https://docs.prontopaga.com/reference/create-payment).
* Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu front-end. Puedes [descargarlos aquí](https://drive.google.com/uc?export=download\&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr).
