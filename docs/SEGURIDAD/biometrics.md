---
title: Biometría
excerpt: Implementa verificación por biometría de reconocimiento facial en tu comercio
deprecated: false
hidden: false
metadata:
  title: Biometría | ProntoPaga Docs
  description: Learn how to implement biometric verification for your merch.
  image: >-
    https://files.readme.io/4e2c4f2384753e0da4d92df3255aaa1ccd396cb0e8105eb2b4c3a90286cf19b9-Prontopaga_Logotipo_2.JPG
  keywords:
    - biometría
    - biometrics
    - biometría ProntoPaga
    - cómo crear una biometría en ProntoPaga
    - biometrics endpoint
  robots: index
---
Con el servicio de verificación por biometría, los clientes serán redireccionados a una web en donde deberán tomar fotografías de su documento de identidad, así como de su rostro. De esta forma, sus transacciones estarán aún más seguras.

***

## Crea una nueva biometría

Tu front-end será el encargado de recopilar los datos necesarios de tu cliente, mientras que tu back-end estará integrado con nuestra API, procesando la creación de la biometría.

De este modo, para crear una solicitud de nueva biometría, deberás usar <Anchor label="este endpoint" target="_blank" href="https://docs.prontopaga.com/reference/create-biometrics">este endpoint</Anchor>. La solicitud se envía con tu Bearer Token, así como con tu secretKey. Además, debes incluir los datos necesarios del cliente, como: nombre y apellido, correo electrónico, teléfono, país, fecha de nacimiento, entre otros.

<NotaFirma />

Para incluir la URL de retorno a la cual será redireccionado el cliente después de completar el proceso de la toma de fotografías, ponte en contacto con nuestro equipo de <Anchor label="Customer support" target="_blank" href="https://docs.prontopaga.com/page/necesitas-ayuda#/">Customer support</Anchor>.

***

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

### Respuesta

Como respuesta a una solicitud de biometría exitosa, recibirás un enlace para redirigir al usuario a la página en donde tomará las fotografías indicadas.

#### Ejemplo de respuesta exitosa:

```json
{
    "biometricVerification": {
        "uid": "a5d089a7-00a4-475a-8e12-1ce559976e6f",
        "status": "new",
        "reference": "789XYZ",
        "verificationUrl": "https://sandbox.prontopaga.com/v2/biometric/a5d089a7-00a4-475a-8e12-1ce559976e6f/verification",
        "decisions": [
         {
        "verification": {
            "id": "e5c11508-1512-42ec-bbec-0dfea9786e81",
            "providerVerificationId": "e5c11508-1512-42ec-bbec-0dfea9786e81",
            "verificationType": "document-selfie",
            "vendorData": "015a5b17-df41-72b5-b18d-6f0be6459a1e",
            "status": "started",
            "person": {
                "firstName": "John",
                "lastName": "Doe",
                "idNumber": "12345678"
            },
            "document": {
                "number": "12345678",
                "country": "PE",
                "type": "PP"
            },
            "finalDocument": {
                "number": null,
                "country": null,
                "type": null
            }
        ],
        "createdAt": "2025-10-30 17:56:17",
        "updatedAt": "2025-10-30 17:56:17"
    }
}
```

> 📘 **Parámetros de una respuesta**
>
> * Los parámetros del campo `finalDocument` pueden ser `null`.
> * El campo `decisions` puede ser un array vacío.

<br />

#### Ejemplo de respuesta fallida:

```json
{
  "errors": [
    {
      "property": "document.number",
      "value": "",
      "message": "El campo 'number' no puede estar vacío."
    },
    {
      "property": "document.number",
      "value": "",
      "message": "Este valor es demasiado corto. Debería tener 5 caracteres o más."
    }
  ]
}
```

Una vez que el usuario haya completado el proceso de la toma de fotografías, ProntoPaga lo redireccionará a la URL de retorno. Al mismo tiempo, devolverá los datos de la transacción al URL que hayas agregado anteriormente.

> ❗️ **Reenvío de nueva biometría**
>
> Si un cliente solicita una **nueva biometría** después de haber sido dado de baja, debe usar **el mismo número y tipo de documento** en los parámetros del campo `document` que empleó en su solicitud original.

***

## Detalles de una biometría

También puedes consultar los detalles de una biometría creada de forma exitosa anteriormente. Para hacerlo, debes de consultar <Anchor label="este endpoint" target="_blank" href="https://docs.prontopaga.com/reference/biometric-details#/">este endpoint</Anchor>, en donde deberás enviar el número `uid`en el path.

### Respuesta

Como respuesta a una solicitud de detalles de una biometría, recibirás la información con la que fue creada y registrada dicha biometría.

**Ejemplo de respuesta exitosa**:

```json
{
    "biometricVerification": {
        "uid": "a5d089a7-00a4-475a-8e12-1ce559976e6f",
        "status": "success",
        "reference": "04K8VEGC40897X2NM1JHQ8PXMF",
        "verificationUrl": "https://sandbox.prontopaga.com/v2/biometric/a5d089a7-00a4-475a-8e12-1ce559976e6f/verification",
        "decisions": [
         {
        "verification": {
            "id": "e5c11508-1512-42ec-bbec-0dfea9786e81",
            "providerVerificationId": "e5c11508-1512-42ec-bbec-0dfea9786e81",
            "verificationType": "document-selfie",
            "vendorData": "015a5b17-df41-72b5-b18d-6f0be6459a1e",
            "status": "started",
            "person": {
                "firstName": "John",
                "lastName": "Doe",
                "idNumber": "12345678"
            },
            "document": {
                "number": "12345678",
                "country": "PE",
                "type": "PP"
            },
            "finalDocument": {
                "number": null,
                "country": null,
                "type": null
            }
        ],
        "createdAt": "2025-10-30 17:56:17",
        "updatedAt": "2025-10-30 17:56:17"
    }
}
```

> 📘 **Parámetros de una respuesta**
>
> * Los parámetros del campo `finalDocument` pueden ser `null`.
> * El campo `decisions` puede ser un array vacío.

<br />

**Ejemplo de respuesta fallida**:

```json
{
  "message": "biometricNotFound",
  "code": 1
}
```

> 📘 **Ver el estado de una verificación biométrica**
>
> Otra forma de conocer el `status` de una biometría, es copiar y pegar el `verificationURL` obtenido en la respuesta del endpoint de **Crear una nueva solicitud de biometría**, una vez hayas terminado el proceso de la toma de fotografías.
>
> Al ingresar, se te mostrará el estatus actual de la verificación.

<br />

## Posibles resultados de una verificación biométrica

El parámetro `status` muestra el estado actual de una verificación de biometría. Los posibles resultados dentro de este parámetro son los siguientes:

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Resultado</b></th>
      <th><b>Descripción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td><code>new</code</td><td>Se requiere un reenvío de datos; el proceso se reinicia.</td></tr>
    <tr><td><code>pending</code</td><td>Estado por defecto. Asume que está pendiente o en progreso si no coincide con algún otro estado.</td></tr>
    <tr><td><code>pending</code</td><td>La revisión de la  verificación está en curso.</td></tr>
    <tr><td><code>rejected</code</td><td>La verificación fue rechazada debido a un fallo en los criterios.</td></tr>
    <tr><td><code>rejected</code</td><td>El tiempo para completar la verificación expiró sin completarse.</td></tr>
    <tr><td><code>rejected</code</td><td>El usuario abandonó el proceso antes de finalizar.</td></tr>
 		<tr><td><code>success</code</td><td>El proceso de verificación biométrica fue aprobado exitosamente.</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

<br />
