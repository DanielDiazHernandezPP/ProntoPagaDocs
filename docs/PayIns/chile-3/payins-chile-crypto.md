---
title: Criptomonedas
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: Integrate cryptocurrency payments in Chile
  description: >-
    Learn how to accept cryptocurrency payments in Chile using Coinbase with the
    Prontopaga API. This guide covers integration steps, payment flow, test
    data, and webhook confirmation.
  image: >-
    https://files.readme.io/a2c4c94a6bc755f737ba5b8e85318f2d030f1eb2496d49179b52812f38f92d7c-Prontopaga_logotipo.png
  keywords:
    - cryptocurrency payments Chile
    - Coinbase API integration
    - crypto payins Chile
    - Prontopaga coinbase payment
    - accept crypto Chile
    - pagos con criptomonedas Chile
    - integrar pagos criptomonedas
  robots: index
next:
  description: ''
---
Crear un pago en Chile con Coinbase consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un bearer token y una firma secreta. De esta forma, las transacciones se autentican y se realizan de forma segura.

## Crea un nuevo pago

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `coinbase_payment` como método de pago en el body de la solicitud.

La solicitud se envía con tu bearer token, así como con tu firma secreta. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros. 

<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

<NotaWebhooks />

### Pago en Coinbase

El cliente podrá continuar el proceso siguiendo las instrucciones en pantalla. Se redireccionará al cliente al sitio web o aplicación de Coinbase, en donde podrá iniciar sesión y hacer el pago.

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un enlace para procesar el pago, así como un identificador de pago del sistema.

### Confirmación de un pago

Una vez que el usuario haya completado el proceso de pago en el formulario, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`. 

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los pay ins](https://docs.prontopaga.com/docs/payins-status).

## Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, también puedes hacer pruebas con [nuestros demos](https://demo.insospa.com/transactions/deposit).

## Antes de finalizar tu integración

Estos son algunos puntos importantes a tomar en cuenta, antes de finalizar tu integración con nosotros:

* No almacenar datos sensibles del cliente en tu base de datos.
* Enviar todos los datos requeridos en el body request del [endpoint de creación de pago](https://docs.prontopaga.com/reference/create-payment).
* Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu front-end. Puedes [descargarlos aquí](https://prontopagalatam-my.sharepoint.com/:f:/g/personal/ana_escalante_prontopaga_com/EvoLzSVLQBtBtvUlXKCUPtkByzlMhjY7LLux9Dc6Dvmlzw?e=fMKXW0).