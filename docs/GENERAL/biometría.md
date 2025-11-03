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

<br />

### Body de la solicitud

A continuación puedes ver un ejemplo del body que se envía en la solicitud:

```json JSON
{
    "usageType": "kyc",
    "person": {
      "firstName": "Jhon",
      "lastName": "Doe",
      "phone": "123456789",
      "email": "jhondoe@example.com",
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

**Ejemplo de respuesta exitosa**:

```json
{
    "biometricVerification": {
        "uid": "a8d089a7-00a4-475a-8e12-1ce559976e6f",
        "status": "new",
        "reference": "01K8VEGC40897X2NM1JHQ8PXMF",
        "verificationUrl": "https://dev-test.prontopaga.com/v2/biometric/a8d089a7-00a4-475a-8e12-1ce559976e6f/verification",
        "decisions": [],
        "createdAt": "2025-10-30 17:56:17",
        "updatedAt": "2025-10-30 17:56:17"
    }
}
```

<br />
