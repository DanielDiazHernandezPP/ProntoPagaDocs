---
title: Efectivo
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    To create a cash payment in Peru, customer data must be captured and a
    request made through the API with a bearer token and a secret signature,
    ensuring secure transactions; the response will include a link to the
    payment slip and a payment identifier.
  keywords:
    - cash
    - ' cash payment'
    - ' payin'
    - ' peru'
    - ' guide'
    - ' integration'
    - ' prontopaga'
    - ' how to make a cash payment'
  robots: index
next:
  description: ''
---
Crear un pago en efectivo en Perú consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un Bearer Token y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.

## ¿Cómo funciona?

Los pagos en efectivo son un método utilizado en Perú para compras en línea, sin necesidad de tarjeta o cuenta bancaria. Los pagos se realizan mediante un código de pago único (CIP), que el cliente puede usar para pagar en establecimientos afiliados, como bancos, agentes autorizados y tiendas de conveniencia. Para utilizar este método, el cliente debe seleccionar la opción "Paga con PagoEfectivo", generar el CIP, presentarlo (impreso o en su celular) en un punto autorizado y realizar el pago.

El proceso de pago con efectivo en Perú consta de seis etapas principales:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4064ebeacb9246b61a55911d539385ffd7af7b7d2d1d5ceb7f90bd44f9df32a7-peru_-_02.jpg",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


1. **Ingreso de datos.** Después de seleccionar los productos o servicios a comprar, el cliente ingresa sus datos personales en un formulario. 
2. **Selección de método.** El cliente elige pagar con efectivo en tu sitio web o aplicación. 
3. **Hoja de pago.** ProntoPaga le entrega una hoja de pago personalizada al cliente, con un código de pago único, así como la información de los puntos físicos en donde puede realizar el pago. 
4. **Pago en punto físico o app del banco.** El cliente se dirige a uno de los puntos físicos con su hoja de pago y su identificación, y hace el depósito del efectivo. También puede pagar a través de la sección de "pago de servicios" de la aplicación de su banco. 
5. **Validación de datos.** ProntoPaga valida la infomación del pago. 
6. **Confirmación.** El cliente recibe una confirmación de pago exitoso en su correo electrónico. A su vez, tu comercio recibe la confirmación del pago a través de los webhooks que hayas configurado.

## Crea un nuevo pago

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `pagoefectivo_payment` como método de pago en el body de la solicitud.

La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros. 

<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

<NotaWebhooks />

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{ 
  "currency": "PEN", 
  "country": "PE", 
  "amount": "10",
  "clientName" : "John Doe", 
  "clientEmail" : "johndoe@example.com", 
  "clientPhone" : "999999999", 
  "clientDocument" : "12345678912", 
  "paymentMethod" : "pagoefectivo_payment", 
  "urlConfirmation" : "Webhook", 
  "urlFinal" : "example.com/successful", 
  "urlRejected" : "example.com/declined", 
  "order" : "1234", 
  "sing" : "Signature of the parameters" 
}
```

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un enlace con la hoja de pago, así como un identificador de pago del sistema.

### Hoja de pago

El cliente verá en pantalla y recibirá en su correo electrónico la hoja de pago, que contendrá:

- Monto a pagar
- Código de pago
- Instituciones en las que puede hacer el pago 
- Instrucciones para hacer el pago 

### Confirmación de un pago

Una vez que el usuario haya realizado el pago en efectivo, ProntoPaga le notificará el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`. 

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los pay ins](https://docs.prontopaga.com/docs/payins-status).

## Demos

Contamos con demos que simulan la experiencia de pago del cliente, en donde podrás hacer pruebas. [Conócelos aquí](https://demo.insospa.com/transactions/deposit).

## Antes de finalizar tu integración

Estos son algunos puntos importantes a tomar en cuenta, antes de finalizar tu integración con nosotros:

- No almacenar datos sensibles del cliente en tu base de datos.
- Enviar todos los datos requeridos en el body request del [endpoint de creación de pago](https://docs.prontopaga.com/reference/create-payment).
- Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu front-end. Puedes [descargarlos aquí](https://drive.google.com/uc?export=download&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr).