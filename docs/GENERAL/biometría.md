---
title: Biometría
excerpt: Implementa verificación por biometría de reconocimiento facial en tu comercio.
deprecated: false
hidden: true
metadata:
  robots: index
---
Con el servicio de verificación por biometría, los clientes serán redireccionados a una web en donde deberán tomar fotografías de su documento de identidad, así como de su rostro. De esta forma, sus transacciones estarán aún más seguras.

***

<br />

## Crea una nueva biometría

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente, mientras que tu back-end estará integrado con nuestra API, procesando la creación de la biometría.

De este modo, para crear una solicitud de nueva biometría, deberás usar <Anchor label="este endpoint" target="_blank">este endpoint</Anchor>. La solicitud se envía con tu Bearer token, así como con tu SecretKey. Además, debes incluir los datos necesarios del cliente, como: nombre y apellido, correo electrónico, teléfono, país, fecha de nacimiento, entre otros.

<NotaFirma />

Para incluir la URL de retorno a la cual será redireccionado el cliente después de completar el proceso de la toma de fotografías, ponte en contacto con nuestro equipo de <Anchor label="Customer support" target="_blank" href="https://docs.prontopaga.com/page/necesitas-ayuda#/">Customer support</Anchor>

***

<br />

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json JSON
{
    "usageType": "kyc",
    "person": {
      "firstName": "John",
      "lastName": "Doe",
      "phone": "123456789",
      "email": "johndoe@example.com",
      "dateOfBirth": "1999-01-01",
      "gender": "M",
      "maritalStatus": "single"
    },
    "document": {
      "number": "1234567",
      "documentType": "PP",
      "country": "PE"
    }
}
```

<br />

### Respuesta

Como respuesta a una solicitud de biometría exitosa, recibirás un enlace para redirigir al usuario a la página en donde tomará las fotografías indicadas.

#### Ejemplo de respuesta exitosa:

```json
{
    "biometricVerification": {
        "uid": ID in our services,
        "status": new,
        "reference": <Biometrics reference>, // This reference is ours and unique, it is used to verify the biometrics in the ProntoPaga system.,
        "verificationUrl": <Biometrics link, the user should be redirected to this link to complete the process.>, 
        "decisions": [],
        "createdAt": Creation date,
        "updatedAt": Date of last update
    }
}
```

#### Ejemplo de respuesta fallida:

```json
{
  "error": {
    "documentNumber": "(string) documentNumber, cannot be null."
  }
}
```

<br />

### Confirmación de una biometría

Una vez que el usuario haya completado el proceso de la toma de fotografías, ProntoPaga lo redireccionará a la URL de retorno. Al mismo tiempo, devolverá los datos de la transacción al URL que hayas agregado anteriormente.

De este modo, para confirmar si una biometría fue exitosa, debes verificar que en tu webhook el valor del campo `status` sea `success`.

***

## Detalles de una biometría

También puedes consultar los detalles de una biometría creada de forma exitosa anteriormente. Para hacerlo, debes de consultar [este endpoint], en donde deberás enviar el número `uid`en el path.

### Respuesta

Como respuesta a una solicitud de detalles de una biometría, recibirás la información con la que fue creada y registrada dicha biometría.

**Ejemplo de respuesta exitosa**:

```json
{
    "biometricVerification": {
        "uid": ID in our services,
        "status": Biometric status,
        "reference": Biometrics reference,
        "verificationUrl": <Biometrics link, the user should be redirected to this link to complete the process.>, 
        "decisions": [],
        "createdAt": Creation date,
        "updatedAt": Date of last update
    }
}
```

**Ejemplo de respuesta fallida**:

```json
{
  "message": "Token could not be found."
}
```
