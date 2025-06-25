---
title: Biometría
excerpt: Implementa verificación por biometría de reconocimiento facial en tu comercio
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    The biometric verification service allows customers to take photos of their
    ID and face to secure their transactions, integrating the front-end and
    back-end with an API to create and confirm biometrics through specific
    endpoints.
  keywords:
    - biometric
    - ' biometrics'
    - ' facial recognition'
    - ' face'
    - ' id'
    - ' api'
    - ' prontopaga api'
    - ' endpoints'
    - ' create a new biometric'
    - ' create biometrics'
  robots: index
next:
  description: ''
---
Con el servicio de verificación por biometría, los clientes serán redireccionados a una web en donde deberán tomar fotografías de su documento de identidad, así como de su rostro. De esta forma, sus transacciones estarán aún más seguras.

## Crea una nueva biometría

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente, mientras que tu back-end estará integrado con nuestra API, procesando la creación de la biometría.

De este modo, para crear una solicitud de nueva biometría, deberás usar [este endpoint](https://docs.prontopaga.com/v1.2/reference/create-biometrics). La solicitud se envía con tu bearer token, así como con tu firma secreta. Además, debes incluir los datos necesarios del cliente, como: nombre y apellido, correo electrónico, teléfono, país, fecha de nacimiento, entre otros. 

<NotaFirma />

También deberás incluir la URL de retorno a la cual será redireccionado el cliente después de completar el proceso de la toma de fotografías.

<NotaWebhooks />

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json
{
  "email": "jhondoe@example.com",
  "firstName": "Jhon",
  "lastName": "Doe",
  "documentNumber": "12345678912",
  "dateOfBirth": "1990-05-30",
  "phone": "999999999",
  "country": "CL",
  "reference": "Local",
  "redirectUrl": "example.com/successful",
  "confirmationUrl": "Webhook",
  "sign": "Signature of the parameters"
}
```

### Respuesta

Como respuesta a una solicitud de biometría exitosa, recibirás un enlace para redirigir al usuario a la página en donde tomará las fotografías indicadas.

**Ejemplo de respuesta exitosa**:

```json
{
  “status”: <Request status>, // Status table at the end of the document. 
  “verified”: <true | false>, 
  “verificationUrl”: <Biometrics link, the user should be redirected to this link to complete the process.>, 
  “reference”: <Biometrics reference>, // This reference is ours and unique, it is used to verify the biometrics in the ProntoPaga system.  
}  
```

**Ejemplo de respuesta fallida**:

```json
{
  "error": {
    "documentNumber": "(string) documentNumber, cannot be null."
  }
}
```

### Confirmación de una biometría

Una vez que el usuario haya completado el proceso de la toma de fotografías, ProntoPaga lo redireccionará a la URL de retorno. Al mismo tiempo, devolverá los datos de la transacción al webhook que hayas agregado.

De este modo, para confirmar si una biometría fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

## Detalles de una biometría

También puedes consultar los detalles de una biometría creada de forma exitosa anteriormente. Para hacerlo, debes de consultar [este endpoint](https://docs.prontopaga.com/v1.2/reference/biometrics-details), en donde deberás enviar el número `reference`en el path. 

### Respuesta

Como respuesta a una solicitud de detalles de una biometría, recibirás la información con la que fue creada y registrada dicha biometría.

**Ejemplo de respuesta exitosa**:

```json
{ 
  “status”: <Biometrics status>, 
  “note”: <Note/message on the status of biometrics>, 
  “reference”: <Biometrics reference>, 
  “documentNumber”: <Customer document number>, 
  “firstName”: <Customer name>, 
  “lastName”: <Customer lastname>, 
  “email”: <Customer email> 
} 
```

**Ejemplo de respuesta fallida**:

```json
{
  "message": "Token could not be found."
}
```