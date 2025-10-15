---
title: Tipos de rechazos (PayOuts)
excerpt: Explora los distintos tipos de rechazos para los PayOuts, divididos por país.
deprecated: false
hidden: false
metadata:
  title: Tipos de rechazos (PayOuts) | ProntoPaga Docs
  description: >-
    The document describes common types of payout rejections in Brazil, Chile,
    Ecuador, and Peru, including customer blocks, transaction limits, and
    payment system-specific errors. 
  image: >-
    https://files.readme.io/1d8dd9ae76841fe399a75c800b1196bd9b0f17a4e83ebdd496b4d640d7f97c74-Prontopaga_logotipo.png
  keywords:
    - rejections Prontopaga
    - payouts rejections
    - types of rejections prontopaga
    - rechazos prontopaga
    - pago rechazado prontopaga
    - pago denegado
    - payout cancelled
    - rejected
  robots: index
next:
  description: ''
---
A continuación se describen todos los posibles tipos de rechazos para PayOuts. El número corresponde al número que se devuelve en el campo `errorCode` del rechazo.

***

## Generales (todos los países) 🌎

A continuación se muestran varios posibles casos de rechazo, junto con su descripción.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Código de error</b></th>
      <th><b>Mensaje de rechazo</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>1</td><td>El cliente se encuentra bloqueado</td></tr>
    <tr><td>2</td><td>Excede límite %s, quedan disponibles %s para el día, %s para la semana, %s para el mes. Retiro máximo por transacción %s</td></tr>
    <tr><td>3</td><td>El saldo a retirar excede el balance disponible en esta moneda</td></tr>
    <tr><td>4</td><td>Cuenta ingresada no existe</td></tr>
    <tr><td>21</td><td>Moneda ingresada es inválida</td></tr>
    <tr><td>22</td><td>Cuenta invalida, bloqueada o cerrada</td></tr>
    <tr><td>23</td><td>	La información suministrada es insuficiente o inválida</td></tr>
    <tr><td>24</td><td>El número de cuenta del destinatario no corresponde a los datos del usuario ingresado</td></tr>
    <tr><td>25</td><td>ID inválido</td></tr>
    <tr><td>26</td><td>Transaction amount limit exceeds</td></tr>
    <tr><td>27</td><td>No se aceptan documentos de identidad correspondientes a empresas. Por favor, ingresa uno válido de persona natural para continuar</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

***

## Chile 🇨🇱

Estos son los tipos de retiros rechazados en Chile.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Código de error</b></th>
      <th><b>Mensaje de rechazo</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>5</td><td>El número de cuenta del destinatario no corresponde al Rut ingresado</td></tr>
    <tr><td>6</td><td>Banco seleccionado no corresponde</td></tr>
    <tr><td>7</td><td>Cuenta con restricción de abono</td></tr>
    <tr><td>8</td><td>Banco de destino en mantención</td></tr>
    <tr><td>9</td><td>	Rut Incorrecto</td></tr>
    <tr><td>10</td><td>Cuenta Rut Con Dígito Verificador</td></tr>
  </tbody>
</table>
`}</HTMLBlock>

***

## Ecuador 🇪🇨

Estos son los tipos de retiros rechazados en Ecuador.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Código de error</b></th>
      <th><b>Mensaje de rechazo</b></th>
      <th><b>Descripción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>Limite de comercio</td><td>Exceeds daily limit, 5,000,000.00 CLP available for the day, 10,000,000.00 CLP available for the week, 30,000,000.00 CLP available for the month. Maximum deposit per transaction 6,000,000.00 CLP</td><td>La cantidad límite del comercio, ya sea por día, semana o mes, fue excedida.</td></tr>
    <tr><td>Pago pendiente</td><td>There is already a pending payment for that phone number</td><td>El número de teléfono ya cuenta con un pago pendiente.</td></tr>
    <tr><td>Pago fallido</td><td>Failed payment: There is already a pending payment transaction</td><td>El pago falló y se generó una transacción pendiente.</td></tr>  
    <tr><td>16</td><td>El número de teléfono no es válido en la cabina telefónica</td><td>El número telefónico enviado no es válido para el servicio de Payphone (no está registrado en el servicio).</td></tr>  
    <tr><td>17</td><td>Error interno, validaciones fallidas</td><td>Ocurrió un error interno debido a una falla durante el proceso de validación.</td></tr>  
    <tr><td>18</td><td>	Problem with bank account details, please try again</td><td>Ocurrió un problema con algunos detalles de la cuenta bancaria. Por favor, intente nuevamente.</td></tr>  
    <tr><td>100</td><td>Error de autenticación</td><td>Hay un error de autenticación. Por favor, intente nuevamente.</td></tr>  
    <tr><td>101</td><td>Error de autenticación</td><td>Hay un error de autenticación. Por favor, intente nuevamente.</td></tr>  
    <tr><td>104</td><td>Error de autenticación</td><td>Hay un error de autenticación. Por favor, intente nuevamente.</td></tr>  
    <tr><td>110</td><td>Datos incompletos</td><td>Los datos ingresados no están completos. Por favor, ingréselos e intente nuevamente.</td></tr>  
    <tr><td>120</td><td>Referencia no encontrada</td><td>La referencia solicitada no fue encontrada.</td></tr>  
    <tr><td>121</td><td>Referencia no asociada a esta pasarela</td><td>La referencia solicitada no está asociada a esta pasarela de retiros.</td></tr>  
    <tr><td>122</td><td>Pago expirado</td><td>El pago ha caducado.</td></tr>  
    <tr><td>123</td><td>Pago pendiente</td><td>El pago se encuentra en estado pendiente.</td></tr>  
    <tr><td>200</td><td>Pago Completado</td><td>El pago fue completado exitosamente.</td></tr>  
    <tr><td>300</td><td>No se puede resolver</td><td>Ocurrió un error inesperado. Por favor, intente nuevamente</td></tr>  
  </tbody>
</table>
`}</HTMLBlock>

***

## Perú 🇵🇪

Estos son los tipos de retiros rechazados en Perú.

<HTMLBlock>{`
<table>
  <thead>
    <tr style="background-color:#ff1f55; color:white; text-align:left;">
      <th><b>Código de error</b></th>
      <th><b>Mensaje de rechazo</b></th>
      <th><b>Descripción</b></th>
    </tr>
  </thead>
  <tbody>
    <tr><td>7</td><td>Internal error, failed validations</td><td>Ocurrió un error interno y las validaciones fallaron. Por favor, reintente nuevamente.</td></tr>
    <tr><td>11</td><td>InstanPayouts not available, please try again</td><td>El servicio de PayOuts instantáneos no está disponible por el momento, por lo que se debe intentar nuevamente.</td></tr>
    <tr><td>12</td><td>Destination bank not available</td><td>En una solicitud de PayOuts instantáneo, el banco de destino no está disponible.</td></tr>  
    <tr><td>13</td><td>Internal error, please try again</td><td>Ocurrió un error interno inesperado. Por favor reintente nuevamente.</td></tr>  
    <tr><td>20</td><td>Wallet not found for this phone number</td><td>El número de teléfono enviado no está asociado con la wallet que se seleccionó para hacer el PayOut.</td></tr>  
  </tbody>
</table>
`}</HTMLBlock>

<br />
