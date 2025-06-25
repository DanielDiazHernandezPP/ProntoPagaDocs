---
title: Primeros Pasos
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    The ProntoPaga API integration guide provides instructions for obtaining and
    using API keys, and explains key concepts such as the differences between
    pay ins and pay outs.
  keywords:
    - firts steps
    - ' how to start'
    - ' prontopaga'
    - ' integration'
  robots: index
next:
  description: ''
---
¡Bienvenido a la integración del API de pagos **ProntoPaga**! Esta guía está diseñada para ayudarte a realizar tu primera solicitud y familiarizarte con los conceptos clave del procesamiento de pagos.

## 📋 Requisitos Previos

Antes de sumergirnos en la integración, debes contar con tus claves API.

> ❗️ Importante:
> 
> Esta sección es esencial, porque si no completas los primeros pasos, ¡no podrás comunicarte con nuestra API en tu proyecto!

### Obtenga sus claves de API

Los consumos a nuestro servicio web se autorizan utilizando nuestro token de autenticación en la cabecera de la llamada. Authorization de tipo “Bearer Token”. Este token te lo proporciona ProntoPaga antes de iniciar tu integración.

- Además, los datos que se envían deben estar siempre firmados con una "SecretKey", nuestra plataforma verifica que los datos enviados pertenecen al comerciante y no fueron adulterados durante el envío a través de la red. Conoce cómo firmar tus transacciones en [este artículo](https://docs.prontopaga.com/docs/sign-transactions).
- Cualquier solicitud que no incluya una clave API devolverá un error. 
- Tanto el TokenApi como el SecretKey serán proporcionados a tu comercio por nuestra administración.

## Glosario esencial

Antes de continuar, es importante revisar algunos conceptos esenciales del mundo de pagos para la integración con ProntoPaga.

### 💳 ¿Qué es un Método de Pago?

Un método de pago es una forma específica en la que un cliente puede realizar un pago. Estos métodos varían según el país y la preferencia del usuario. Aquí tienes una breve descripción de los tipos más comunes:

- **Tarjetas de crédito/débito**: Uno de los métodos más utilizados a nivel mundial, donde el cliente paga utilizando su tarjeta bancaria.
- **Transferencias bancarias**: Permiten al cliente transferir dinero directamente desde su cuenta bancaria.
- **Billeteras digitales:** Servicios como PayPal o Google Pay que permiten almacenar fondos y realizar pagos en línea de manera segura.
- **Pagos en efectivo**: Algunas regiones permiten pagos en efectivo a través de intermediarios como tiendas de conveniencia.

<br />

### 🔄 Pay ins y Pay outs

En el mundo de los pagos, es importante entender la diferencia entre pay ins y pay outs:

- **Pay in**: Es el proceso mediante el cual un cliente envía dinero a tu plataforma o negocio. Ejemplos comunes son los pagos que los usuarios realizan cuando compran un producto o servicio en línea.
- **Pay out**: Se refiere al proceso de transferir dinero desde tu plataforma o negocio a los clientes o proveedores. Un ejemplo de esto es el pago a un vendedor en un marketplace o el retiro de fondos por parte de un usuario.

<br />

## ➡️ Siguientes Pasos

¡Felicidades por iniciar este camino! Ahora que tienes lo básico, te invitamos a explorar nuestra referencia completa de la API para descubrir todas las funcionalidades que ofrecemos. Además, no olvides revisar nuestras guías por país para ver cómo integrar los diferentes métodos de pago en tu mercado objetivo.