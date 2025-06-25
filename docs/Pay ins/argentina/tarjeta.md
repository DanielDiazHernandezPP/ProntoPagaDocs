---
title: Tarjeta
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
Crear un pago con tarjeta en Argentina consiste en capturar los datos necesarios del cliente para el pago y hacer una solicitud a través de nuestra API con un Bearer Token y una secretKey. De esta forma, las transacciones se autentican y se realizan de forma segura.

Los pagos con tarjeta cuentan con la herramienta automatizada Decision Manager (DM) del motor de gestión de riesgos y prevención de fraude de Cybersource (A Visa Solution), junto con el sistema 3DS, el cual activa los desafíos (*challenges*) correspondientes para validar o rechazar transacciones.

## ¿Cómo funciona?

El proceso de pago con tarjeta en Argentina consta de cinco etapas principales:

1. **Selección de método.** El cliente elige pagar con tarjeta en tu sitio web o aplicación. 
2. **Ingreso de datos.** El cliente llena los datos requeridos en el formulario de pago con tarjeta, como: número de tarjeta, fecha de vencimiento, CVV, nombre y correo electrónico.  
3. **Validación de datos.** Se verifican los datos con el emisor de la tarjeta. 
4. **Autorización y Captura.** Se verifica que existan los fondos suficientes, y se mueven desde el banco del cliente hacia la cuenta de tu comercio. 
5. **Confirmación.** El cliente ve en pantalla el resultado de la transacción. A su vez, tu comercio recibe la confirmación a través de los webhooks que hayas configurado.

## Crea un nuevo pago

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente para procesar el pago, mientras que tu back-end estará integrado con nuestra API, procesando el pago.

De este modo, para crear una solicitud de nuevo pago deberás usar [este endpoint](https://docs.prontopaga.com/reference/create-payment) y colocar `latam_chk_card_payment` como método de pago en el body de la solicitud.

La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente para hacer el pago, como: nombre, correo electrónico, teléfono, país, moneda, monto, entre otros. 

<NotaFirma />

También deberás incluir la URL de retorno en caso de que la transacción sea exitosa, así como una URL en caso de que el pago sea rechazado.

<NotaWebhooks />

A continuación puedes ver un ejemplo de request:

```json
{ 
  "currency": "ARS", 
  "country": "AR", 
  "amount": "200",
  "clientName" : "John Doe", 
  "clientEmail" : "johndoe@example.com", 
  "clientPhone" : "999999999", 
  "clientDocument" : "12345678912", 
  "paymentMethod" : "latam_chk_card_payment", 
  "urlConfirmation" : "https://www.webhook.com", 
  "urlFinal" : "example.com/successful", 
  "urlRejected" : "example.com/declined", 
  "order" : "1234",
  "sign" : "Signature of the parameters" 
}
```

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
  "amount":200, 
  "method":"AR Tarjeta", 
  "reference":"1687348107370523",
  "clientEmail" : "johndoe@example.com",
  "clientDocument" : "999999999",         
  "order":"30023", 
  "currency":"ARS", 
  "country":"AR", 
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

A continuación se muestran varios posibles casos de rechazo, junto con su descripción. 

| Título                          | Descripción                                                                                 |
| :------------------------------ | :------------------------------------------------------------------------------------------ |
| FONDOS\_INSUFICIENTES           | Saldo insuficiente para realizar la transacción.                                            |
| RECHAZADO\_POR\_BANCO           | Tu banco rechazó la transacción. Contáctate con ellos para más información.                 |
| TRANSACCION\_RECHAZADA          | Tu banco rechazó la transacción. Intenta con otra tarjeta o contacta a tu banco.            |
| CODIGO\_DE\_SEGURIDAD\_INVALIDO | El código CVV ingresado no es correcto. Verifica e inténtalo nuevamente.                    |
| DATOS\_DE\_TARJETA\_INVALIDOS   | Los datos de la tarjeta ingresados son incorrectos. Verifica e inténtalo nuevamente.        |
| NUMERO\_DE\_TARJETA\_INVALIDO   | El número de tarjeta ingresado es incorrecto. Verifica e inténtalo nuevamente.              |
| TARJETA\_REPORTADA              | La tarjeta ha sido reportada como robada. Contacta a tu banco para más información.         |
| ERROR                           | Se ha producido un error en la transacción. Inténtalo nuevamente o usa otro método de pago. |

## Prueba tu integración

Contamos con un [catálogo de datos de prueba](https://docs.prontopaga.com/docs/test-data) que puedes usar para comprobar que tu integración está lista, así como para ver el flujo de pago que seguirá tu cliente. Además, también puedes hacer pruebas con [nuestros demos](https://demo.insospa.com/transactions/deposit).

## Antes de finalizar tu integración

Estos son algunos puntos importantes a tomar en cuenta, antes de finalizar tu integración con nosotros:

* No almacenar datos sensibles del cliente en tu base de datos.
* Enviar todos los datos requeridos en el body request del [endpoint de creación de pago](https://docs.prontopaga.com/reference/create-payment).
* Agregar los logotipos de los diferentes métodos de pago de ProntoPaga a tu front-end. Puedes [descargarlos aquí](https://drive.google.com/uc?export=download\&id=1lIu2zZ572E0Oxm0mexQ4x8fmma7kcLQr).
