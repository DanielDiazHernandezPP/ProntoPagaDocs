---
title: pruebas Kat
deprecated: false
hidden: true
metadata:
  robots: index
---
## Certifica tu integración

La certificación de la integración en sandbox es un paso obligatorio para todos los comercios antes de recibir credenciales de producción. Su propósito es asegurar que la integración cumpla con los estándares técnicos, funcionales y de seguridad requeridos por ProntoPaga.

Este documento establece los requisitos mínimos que deben cumplirse sin excepción para que la certificación sea aprobada.

### Requisitos de Certificación

A continuación, encontrarás los distintos requisitos necesarios para completar tu certificación:

<Tabs>
  <Tab title="Identificador del Cliente">
    * ❌ El DNI o RUT del cliente no debe ser modificable en ningún punto del flujo de pago.
    * ✅ Es recomendable que este dato no se muestre en el checkout. Puede estar disponible solo en la sección de perfil del usuario autenticado.
    * ⚠️ Esta medida tiene como objetivo prevenir fraudes y evitar que se realicen transacciones en nombre de terceros o menores de edad.
  </Tab>

  <Tab title="Métodos de Pago">
    * 🔎 Todos los nombres y logos de los métodos de pago habilitados deben mostrarse de forma clara, sin modificaciones visuales o estilísticas que puedan generar confusión o inducir a errores.
    * ✅ Se recomienda ordenarlos según su popularidad o frecuencia de uso, para mejorar la experiencia del usuario y optimizar la conversión.
  </Tab>

  <Tab title=" Información Guiada y Mensajes al Usuario">
    * ✅ El checkout debe incluir mensajes claros y visibles que orienten al usuario durante todo el proceso.

    ❗ Es obligatorio mostrar:

    * ℹ️ Montos mínimos y máximos permitidos para cada método de pago.
    * ℹ️ Estados transaccionales con claridad: por ejemplo, **Transacción aprobada** o **Transacción rechazada**, junto con una sugerencia de los pasos a seguir en caso de que corresponda.
  </Tab>
</Tabs>