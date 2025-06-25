---
title: ¿Cómo firmar las transacciones?
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    To sign your transactions, sort the parameters alphabetically, concatenate
    them into a string and then sign that string using HMAC with SHA-256 and a
    secret key.
  keywords:
    - secretkey
    - ' secret key'
    - ' sign'
    - ' prontopaga'
  robots: index
next:
  description: ''
---
Para firmar tus transacciones, sigue estos pasos:

1. Clasifica los parámetros en orden alfabético ascendente, según el nombre del parámetro.
2. Una vez ordenados, los parámetros deben concatenarse en una cadena. Por ejemplo, si los parámetros son:

```json
 "$data":     
				{
            "amount": 45000,
            "clientDocument": "999999999",
            "clientEmail": "johndoe@example.com",
            "clientName": "John Doe",
            "clientPhone": "999999999",
            "country": "CL",
            "currency": "CLP",
            "order": 3000001,          
            "paymentMethod": "webpay_payment",
            "urlConfirmation": "Webhook",
            "urlFinal": "example.com/successful",
            "urlRejected": "example.com/declined"
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
