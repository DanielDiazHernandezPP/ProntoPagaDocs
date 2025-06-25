---
title: Tarjeta
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    To create a card payment in Peru, customer data must be captured and a
    request made through the API with a bearer token and a secret signature,
    allowing options such as payment in installments, card reminder, and foreign
    card payments, all managed from the Console. The request must include
    customer data and return URLs, and the webhook will indicate the status of
    the payment.
  keywords:
    - card
    - ' card payment'
    - ' peru'
    - ' payin'
    - ' guide'
    - ' integration'
    - ' prontopaga'
    - ' how to make a card payment'
  robots: index
next:
  description: ''
---
Crear un pago con tarjeta en Perú consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un bearer token y una firma secreta. De esta forma, las transacciones se autentican y se realizan de forma segura.

## ¿Cómo funciona?

El proceso de pago con tarjeta en Perú consta de cinco etapas principales:

<Image align="center" src="https://files.readme.io/341224d75b1d4619ee7ff57c93c63a3c05300691f309dfd6b92f8e18e518af38-peru_-_01.jpg" />

1. **Selección de método.** El cliente elige pagar con tarjeta en tu sitio web o aplicación. 
2. **Ingreso de datos.** El cliente llena los datos requeridos en el formulario de pago con tarjeta, como: número de tarjeta, fecha de vencimiento, CVV, nombre y correo electrónico. Si tienes activadas las opciones, el cliente verá también la opción de pagar en cuotas y la de recordar tarjeta. 
3. **Validación de datos.** Se verifican los datos con el emisor de la tarjeta. 
4. **Autorización y Captura.** Se verifica que existan los fondos suficientes, y se mueven desde el banco del cliente hacia la cuenta de tu comercio. 
5. **Confirmación.** El cliente ve en pantalla el resultado de la transacción. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

## Especificaciones

El pago con tarjeta en Perú cuenta con características extras. Algunas de ellas las puedes activar o desactivar en la Consola, según lo requieras. A continuación se detallan.

### Pago en cuotas

El switch de pago con cuotas puede encenderse o apagarse desde la Consola. Al estar encendido, la opción de cuotas se mostrará en automático en el formulario. El número de cuotas son definidas por el emisor de la tarjeta, así como por el banco del usuario. 

<Image align="center" src="https://files.readme.io/deee08d0ef65a7124c0f6208436b93e0c3035b039ea3c069b930786377102a0f-cuotas.png" />

### Recordar tarjeta

Esta función también puede ser controlada desde la Consola. Si se habilita, al cliente le aparecerá un campo extra en su formulario de pago con la opción de recordar su tarjeta para futuras compras. Podrá asignarle un alias a cada tarjeta que decida guardar:

<Image align="center" src="https://files.readme.io/05694f34656428e9cabb3184d9f52bde33c4eb8d1628f5146329b52849ee3f0b-recordar.png" />

> 📘 Monedas
>
> Si el cliente guarda una tarjeta después de un pago en soles, esa tarjeta guardada solo se podrá utilizar para pagos futuros en soles. Si desea usarla en dólares, deberá guardarla nuevamente en dólares.

### Pago con tarjetas foráneas

Nuestro sistema cuenta con soporte de pagos con tarjetas foráneas. Se detectará en automático cuando se trata de una tarjeta de este tipo, con lo cual, el cliente verá dos campos extras en su formulario de pagos (ciudad y país de la tarjeta):

<Image align="center" src="https://files.readme.io/256cae68c54af6a16b733f1924a23b17aff6c9e55361164f4044d90bd550a12d-extranjera.png" />

## Crea un nuevo pago

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `pe_card_payment` como método de pago en el body de la solicitud.

La solicitud se envía con tu bearer token, así como con tu firma secreta. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros. 

<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

<NotaWebhooks />

A continuación puedes ver un ejemplo de request:

```json
{ 
  "currency": "PEN", 
  "country": "PE", 
  "amount": "10",
  "clientName" : "John Doe", 
  "clientEmail" : "johndoe@example.com", 
  "clientPhone" : "999999999", 
  "clientDocument" : "12345678912", 
  "paymentMethod" : "pe_card_payment", 
  "urlConfirmation" : "Webhook", 
  "urlFinal" : "example.com/successful", 
  "urlRejected" : "example.com/declined", 
  "order" : "1234", 
 	"sing" : "Signature of the parameters" 
}
```

Puedes ajustar la apariencia de tu formulario con el parámetro opcional `theme` cambiando el color de fondo o creando versiones modo claro y modo oscuro.

### Respuesta

Como respuesta a una solicitud de pago exitosa, recibirás un enlace para procesar el pago, así como un identificador de pago del sistema. 

#### Ejemplo de respuesta para pago exitoso:

```json
{ 
   "urlPay" : "Link to redirect or Iframe to insert",
   "uid" : "ID in our services",
   "reference": "Reference in our services" 
}
```

#### Ejemplo de respuesta de pago rechazado:

```json
{ 
   "uid": "ID in our services",
   "status": "rejected",
   "reference": "Reason for rejection" 
}
```

### Confirmación de un pago

Una vez que el usuario haya completado el proceso de pago en el formulario, ProntoPaga le mostrará una ventana con el resultado final de su transacción. Al mismo tiempo, devolverá los datos de la transacción a la URL que especificaste en `urlConfirmation`. 

Para confirmar si una transacción fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

Conoce todos los estados posibles de un pago en el siguiente enlace: [Estados de los pay ins](https://docs.prontopaga.com/docs/payins-status).

Ejemplo de **webhook para un pago exitoso**:

```json
{ 
  "uid":"01HZ7HFEJZ0GN2TYNDDXC456F", 
  "status":"success", 
  "amount":10, 
  "method":"PE Tarjeta", 
  "reference":"1687348107370523",
  "clientEmail" : "johndoe@example.com",
  "clientDocument" : "999999999",         
  "order":"30023", 
  "currency":"PEN", 
  "country":"PE", 
  "method_type":"TDD", 
  "method_detail":"6623 VD", 
  "hash":"25aGF34G33HG34H41111",
  "note":null, 
  "sign":"e6f27650e5e7703949b0f2be41dde1aeab84145595c4183271e0a42f1500aa"
} 
```

### Detalles de un pago

Si así lo deseas, puedes consultar [este endpoint](https://docs.prontopaga.com/reference/payment-details) para conocer los detalles del pago. De ser exitosa la consulta, obtendrás una respuesta similar a la siguiente:

```json
{ 
  "uid": [string] // Transaction Identifier 
  "status": [string] // Transaction status 
  "amount": [integer] // Transaction amount 
  "method": [string] // Payment method used 
  "reference": [string] // Reference of the transaction 
  "clientEmail": [string] // Client's email address 
  "clientDocument": [string] // Customer's ID number 
  "order": [string] // Payment identifier to be associated with 
  "currency": [string] // ISO currency code 
  "country": [string] // International Country Format 
  "method_type": [string] // Method type 
  "method_detail": [string] // Method details 
  "hash": [string] // Security hash parameter 
  "sign": [string] // Signature of the parameters
}
```

### Motivos de rechazo

A continuación se muestran varios posibles casos de rechazo junto con su código y descripción. Además, incluimos posibles datos de prueba para utilizar en cada caso:

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Código
      </th>

      <th>
        Descripción
      </th>

      <th>
        Datos de prueba para casos denegados
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        101
      </td>

      <td>
        Tarjeta vencida
      </td>

      <td>
        4024007126919058\
        03/19\
        111
      </td>
    </tr>

    <tr>
      <td>
        102
      </td>

      <td>
        Operación no permitida para esta tarjeta
      </td>

      <td>
        4916122919724598\
        03/28\
        111
      </td>
    </tr>

    <tr>
      <td>
        113
      </td>

      <td>
        Monto no permitido
      </td>

      <td>
        4242424242424242\
        03/28\
        111
      </td>
    </tr>

    <tr>
      <td>
        116
      </td>

      <td>
        Fondos insuficientes
      </td>

      <td>
        4041650444437904\
        03/28\
        111
      </td>
    </tr>

    <tr>
      <td>
        118
      </td>

      <td>
        Tarjeta inválida
      </td>

      <td>
        4111111111111111\
        03/28\
        111
      </td>
    </tr>

    <tr>
      <td>
        129
      </td>

      <td>
        Tarjeta no operativa
      </td>

      <td>
        4534410925317008\
        03/28\
        111
      </td>
    </tr>

    <tr>
      <td>
        208
      </td>

      <td>
        Tarjeta perdida
      </td>

      <td>
        4557885040264791\
        03/28\
        111
      </td>
    </tr>

    <tr>
      <td>
        209
      </td>

      <td>
        Tarjeta robada
      </td>

      <td>
        4557883870910971\
        03/28\
        111
      </td>
    </tr>

    <tr>
      <td>
        666
      </td>

      <td>
        Problemas de comunicación
      </td>

      <td>
        4285975261967724\
        03/28\
        111
      </td>
    </tr>

    <tr>
      <td>
        670
      </td>

      <td>
        Transacción denegada por posible fraude
      </td>

      <td>
        4551707477308329\
        03/28\
        111
      </td>
    </tr>

    <tr>
      <td>
        679
      </td>

      <td>
        Error de autenticación
      </td>

      <td>
        4732453453776393\
        03/28\
        111
      </td>
    </tr>

    <tr>
      <td>
        191
      </td>

      <td>
        Contactar emisor
      </td>

      <td>
        4539676788512233\
        03/28\
        111
      </td>
    </tr>
  </tbody>
</Table>

## Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, también puedes hacer pruebas con [nuestros demos](https://demo.insospa.com/transactions/deposit).

## Antes de finalizar tu integración

Estos son algunos puntos importantes a tomar en cuenta, antes de finalizar tu integración con nosotros:

* No almacenar datos sensibles del cliente en tu base de datos.
* Enviar todos los datos requeridos en el body request del [endpoint de creación de pago](https://docs.prontopaga.com/reference/create-payment).
* Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu front-end. Puedes [descargarlos aquí](https://drive.google.com/uc?export=download\&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr).
