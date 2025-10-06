---
title: ¿Cómo firmar las transacciones?
excerpt: >-
  Conoce el proceso para firmar las transacciones realizadas a través de nuestra
  API
deprecated: false
hidden: false
metadata:
  title: Cómo firmar las transacciones | ProntoPaga Docs
  description: >-
    To sign your transactions, sort the parameters alphabetically, concatenate
    them into a string and then sign that string using HMAC with SHA-256 and a
    secret key.
  image: >-
    https://files.readme.io/0173d1f1eccb72899d88ce1e014cb96a0e46ec380fafb8dd9fd9760c0310ef94-Prontopaga_Logotipo.JPG
  keywords:
    - secretkey
    - secret key
    - sign
    - prontopaga
    - firmar transacciones
    - firmar
  robots: index
next:
  description: ''
---
Para firmar tus transacciones, sigue estos pasos:

1. Clasifica los parámetros en orden alfabético ascendente, según el nombre del parámetro.
2. Una vez ordenados, los parámetros deben concatenarse en una cadena. Por ejemplo, si los parámetros son

```json
{
  "amount": "25500",
  "clientDocument": "11111111-1",
  "clientEmail": "johndoe@example.com",
  "clientName": "John Doe",
  "clientPhone": "999999999",
  "country": "CL",
  "currency": "CLP",
  "order": "XYZ789",          
  "paymentMethod": "webpay_payment",
  "urlConfirmation": "https://www.webhook.com",
  "urlFinal": "https://sandbox.prontopaga.com/successful",
  "urlRejected": "https://sandbox.prontopaga.com/declined"
}
```

> 📘 Parámetros
>
> Todos los parámetros deben estar en la firma, excepto el parámetro "sign" (que es en donde va la firma).

Entonces, la cadena ordenada para la firma deberá tener este aspecto:

```
// String to sign.
        $keys = array_keys($data);
        sort($keys);
        $toSign = '';
        foreach ($keys as $key) {
            $toSign .= $key . $data[$key];
        }
```

3. Finalmente, la cadena concatenada debe ser firmada con la función hmac usando el sha256 y tu secretKey como clave:

```
 // Obtaining the signature.
        $sign = hash_hmac('sha256', $toSign, $secretKey);
```