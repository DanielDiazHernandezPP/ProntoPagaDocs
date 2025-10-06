---
title: Primeros Pasos
excerpt: >-
  Conoce el procesamiento de transacciones y cómo realizar solicitudes en
  nuestra API.
deprecated: false
hidden: false
metadata:
  title: Primeros pasos | ProntoPaga Docs
  description: >-
    The ProntoPaga API integration guide provides instructions for obtaining and
    using API keys, and explains key concepts such as the differences between
    pay ins and pay outs.
  image: >-
    https://files.readme.io/ad25aca01818785fdd99aae8c492561bf7627ef64b57ef8248b071ca3a094eb9-Prontopaga_Logotipo.JPG
  keywords:
    - firts steps
    - how to start
    - prontopaga
    - integration
    - empezar en Prontopaga
  robots: index
---
En esta página podrás familiarizarte con conceptos clave para el procesamiento de transacciones, además de conocer cómo realizar tu primera solicitud en nuestra API.

***

## 1. Obtén tus credenciales

Antes de iniciar con la integración, deberás contar con tus credenciales, las cuales son:

* **Bearer Token.** Es el token de autorización en la cabecera de la llamada.
* **secretKey.** Los datos que se envían en el cuerpo de la llamada deben estar firmados con la "secretKey". De este modo, nuestra plataforma verifica que los datos pertenecen al comercio y que no fueron adulterados durante el envío a través de la red. Conoce cómo crear la firma de tus transacciones en [este artículo](https://docs.prontopaga.com/docs/sign-transactions).

Tanto el Bearer Token como el secretKey serán proporcionados a tu comercio por nuestra administración.

> ❗️ Credenciales
>
> Obtener tus credenciales es esencial, ya que cualquier solicitud que no incluya Bearer Token o secretKey devolverá un error, al no estar autenticada.

### 1.1. Credenciales de prueba

Si aún no cuentas con tus credenciales para el enviroment de sandbox y deseas comenzar a probar nuestra API, ponemos a tu disposición las siguientes credenciales:

* **Bearer Token (sandbox):** `caff446438560a48438e0b49e5a6a0870ac5624b9f9ce1577858595d1a8ba1ec`
* **secretKey (sandbox):** `01JNH2SBC5Z2CM1PWQXM2C1XK9`

Puedes usar estas credenciales momentáneamente para pruebas en dos sitios:

* **Referencia API online.** En la caja superior derecha podrás ingresar el Bearer Token, así como utilizar los ejemplos de bodys precargados, en donde deberás añadir la [firma](https://docs.prontopaga.com/docs/sign-transactions). Conoce todas las zonas de nuestra Referencia API online en [esta página](https://docs.prontopaga.com/reference/quick-guide-doc#api-reference).
* **Colección de Postman.** Contamos con una colección de Postman con ejemplos y con un script para automatizar la creación de la firma. Conoce más sobre la colección en [esta página](https://docs.prontopaga.com/reference/postman).

***

## 2. ¿Cómo hacer una solicitud?

Una vez que tengas tus credenciales, podrás hacer tu primera solicitud en nuestra API.

### 2.1. Hacer una solicitud en la Referencia API online

Sigue estos pasos para hacer tu primera solicitud en nuestra Referencia API online:

1. En [docs.prontopaga.com](https://docs.prontopaga.com/), dirígete a la pestaña superior **\<> API Reference**.
2. Selecciona el endpoint que deseas probar.
3. En la esquina superior derecha, agrega tu Bearer Token en la caja de **CREDENTIALS** (OAuth2).
4. Si la llamada es tipo POST, selecciona un ejemplo de body request en la caja superior derecha, debajo de donde ingresaste tu Bearer Token.
5. Si el body request requiere el parámetro `sign`, usa tu secretKey y sigue [estas instrucciones](https://docs.prontopaga.com/docs/sign-transactions) para construir la firma de tu transacción.
6. Haz clic en el botón **Try it!** para enviar la solicitud. Verás la respuesta justo debajo.

### 2.2. Hacer una solicitud en la Colección de Postman

Para hacer tu primera solicitud en nuestra Colección de Postman, sigue los pasos indicados en [esta página](https://docs.prontopaga.com/reference/postman). Ahí encontrarás instrucciones específicas para usar las credenciales genéricas de prueba, así como instrucciones para usar tus propias credenciales de prueba.

***

## 3. Conceptos clave

Estos son algunos conceptos del mundo de los pagos que podrían serte de utilidad durante tu integración con ProntoPaga.

### 3.1. ¿Qué es un método de pago?

Un método de pago es una forma específica en la que un cliente puede realizar un pago. Estos métodos varían según el país y la preferencia del usuario. Aquí tienes una breve descripción de los tipos más comunes:

* **Tarjetas de crédito/débito/prepago**: Uno de los métodos más utilizados a nivel mundial, en donde el cliente paga utilizando su tarjeta bancaria.
* **Transferencias bancarias**: Permiten al cliente transferir dinero directamente desde su cuenta bancaria.
* **Wallets (billeteras digitales):** Son servicios como PayPal o GooglePay, que permiten almacenar fondos y realizar pagos en línea de manera segura.
* **QR**: Este método permite escanear un código QR para realizar un pago de manera rápida, a través de distintos servicios.
* **Efectivo**: Algunas regiones permiten pagos en efectivo a través de intermediarios como tiendas de conveniencia.

### 3.2. ¿Qué es un método de retiro?

Un método de retiro es una forma específica en la que un cliente puede elegir hacer un retiro. Por ejemplo, cuando un cliente hace una apuesta en un sitio online, gana dinero, y desea retirar parte de sus ganancias. Estos métodos varían según el país y la preferencia del usuario. Aquí tienes una breve descripción de los tipos más comunes:

* **Transferencias bancarias**: Permiten al cliente elegir que su dinero sea transferido directamente a su cuenta bancaria.
* **Wallets (billeteras digitales):** Son servicios como PayPal o GooglePay, en los cuales se puede recibir dinero de forma segura.
* **Efectivo**: Algunas regiones permiten retiros en efectivo a través de intermediarios como tiendas de conveniencia.

### 3.3. PayIns y PayOuts

Anteriormente hablamos de pagos y retiros. Pero los términos de PayIns y PayOuts también suelen ser muy utilizados en el mundo de los pagos:

* **PayIn**: Es el proceso mediante el cual un cliente envía dinero a tu plataforma o negocio. Un ejemplo común, sería el pago que hace un cliente al comprar un producto o servicio en línea.
* **PayOut**: Se refiere al proceso de transferir dinero desde tu plataforma o negocio a tus clientes o proveedores. Un ejemplo de esto es el pago a un vendedor en un marketplace. Otro ejemplo sería el retiro de fondos por parte de un cliente.

***

## 4. Siguientes Pasos

¡Felicidades por finalizar los Primeros Pasos! Ahora que cuentas con las herramientas e información necesarias, te invitamos a explorar nuestra Referencia API para descubrir todas las funcionalidades que ofrecemos. Además, no olvides revisar nuestras guías por país, para conocer cómo integrar los diferentes métodos de pago y retiro, en tu mercado objetivo.
