---
title: Cambios PayIns MACH sin redirección
deprecated: false
hidden: true
metadata:
  robots: index
---
## ¿Por qué se muestran aquí los cambios?

Debido a que aún no está disponible para que lo puedan integrar los comercios, los cambios relacionados al proyecto se compilan aquí. ReadMe no permite guardar cambios no publicados, lo que podría generar que los comercios pregunten por nuevas integraciones aún no disponibles.

***

## Cambios en la documentación

Los cambios realizados para este desarrollo serán:

1. Nueva nota en el punto 2  de la sección: https://docs.prontopaga.com/docs/payins-chile-qr#/

> 📘 **Personalizar tu QR único**
>
> Con el parámetro opcional `qr_only` recibirás el base 64 del código QR para poder personalizarlo. Conoce el endpoint aquí.

2. Ejemplo de body en la API Reference: https://docs.prontopaga.com/reference/create-payment#/

```json Chile QR/Wallet (MACH without redirection)
{
  "currency": "CLP",
  "country": "CL",
  "amount": "25500",
  "clientName": "John Doe",
  "clientEmail": "johndoe@example.com",
  "clientPhone": "999999999",
  "clientDocument": "11111111-1",
  "paymentMethod": "mach_payment",
  "qr_only": "true",
  "urlConfirmation": "https://www.webhook.com",
  "urlFinal": "https://sandbox.prontopaga.com/successful",
  "urlRejected": "https://sandbox.prontopaga.com/declined",
  "order": "XYZ789",
  "sign": "Signature of the parameters"
}
```

3. Ejemplo de respuesta exitosa en la API Reference

```json Chile QR/Wallet (MACH without redirection)
{
    "qr": {
        "code": "00020101021226880014br.gov.bcb.pix2566qrcode-h.pixu4c.com.br/v2/cob/0197f0cc-0958-7773-ab30-11c0d5f9fd3e5204000053039865802BR5909Okto",
        "codeBase64": "MDAwMjAxMDEwMjEyMjY4ODAwMTRici5nb3YuYmNiLnBpeDI1NjZxcmNvZGUtaC5waXh1NGMuY29tLmJyL3YyL2NvYi8wMTk3ZjBjYy0wOTU4LTc3NzMtYWIzMC0xMWMwZDVmOWZkM2U1MjA0MDAwMDUzMDM5ODY1ODAyQlI1OTA5T2t0bw=="
    },
    "uid": "01K04CJYE81FS3607X1WCDH477",
    "reference": "17524940782403"
}
```

4. Ejemplo de respuesta fallida en la API Reference

```json Chile QR/Wallet (MACH without redirection)
{
    "error": {
        "orderValidate": "order, already exists."
    }
}
```

5. <br />
