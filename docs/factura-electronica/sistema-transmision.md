# MANUAL FUNCIONAL DEL SISTEMA DE TRANSMISIÓN

## Ministerio de Hacienda


## Control de Versiones

```
Versión Fecha
1.0 02 / 2023
1.1 11 - 05 - 2023
```
## Control de Cambios

```
Detalle Versión Detalle de Cambios
Versión 1.0 Versión inicial del documento.
```
```
Versión 1. 1
```
```
Actualización de nombres de campo según normativa, se amplía explicación
para aplicación del Catálogo “Tributos”, adición de anexo venta a cuenta de
terceros.
```

## Contenido


- I. Sistema de Transmisión de Documentos Tributarios Electrónicos (Sistema de Transmisión DTE)
- II. Modelo de Recepción Utilizado en los DTE
- III. Firma Electrónica
- IV. Versión interpretada y legible del DTE
- V. Estructuras de los Documentos Tributarios Electrónicos
- VI. Eventos de Invalidación y Contingencia para el Sistema de Transmisión DTE
- VII. Secciones de estructuras para los Eventos de Invalidación y Contingencia
- VIII. Evento de invalidación
- IX. Evento de contingencia.
- X. Pruebas de Transmisión Satisfactorias Mínimas para el Sistema de Transmisión DTE
- XI. Detalle de la estructura Número de Control.
- XII. Tratamiento de campo "Cargos/Abonos que no afectan la base imponible”
- XIII. Aplicación del Catálogo “Tributos”
- XIV. Uso de la Sección Documentos Relacionados.
- XV. Uso de Sección Otros Documentos Asociados.
- XVI. Venta cuenta de terceros
- Bonificación, Rebajas y otros” en los DTE. XVII. Aplicación de los campos “Descuento, Bonificación, Rebajas por ítem” y “Monto Global de Descuento,
- XVIII.Invalidación de documentos
- XIX. Ingreso de información en campos relativos al pago
- XX. Ingreso de información para los ítems del Comprobante de Donación
- XXI. Redondeos y Holguras
- XXII. Versiones Legibles
- 1. Factura Electrónica
- 2. Comprobante de Crédito Fiscal Electrónico V3
- 3. Nota de Remisión Electrónica v3
- 4. Nota de Crédito Electrónica V3
- 5. Nota de Débito Electrónica v3
- 6. Comprobante de Retención Electrónico v1.
- 7. Comprobante de Liquidación v1
- 8. Documento Contable de Liquidación Electrónico v1
- 9. Factura de Exportación Electrónica v1
- 10. Factura Sujeto Excluido Electrónica v1
- 11. Comprobante de Donación Electrónico v1
- XXIII. Ejemplo Archivo DTE
- XXIV. Glosario
- XXV. Abreviaturas


## Introducción

Con la entrada en vigencia de la Normativa de Cumplimiento de los Documentos Tributarios Electrónicos se identificó
la necesidad de actualizar la documentación técnica disponible para los contribuyentes, por tanto este manual junto
a la Normativa sustituye a los documentos “Manual de Estructuras Cat. y Versión Legible Sistema de Transmisión” y
“Manual de eventos de Invalidación y Contingencia para el Sistema de Transmisión DTE”.

Este manual proporciona a los contribuyentes que utilicen el Sistema de Transmisión de DTE ampliaciones de
aspectos relevantes tales como el modelo de Facturación Electrónica, la firma electrónica, uso del catálogo
“Tributos”, utilización de los eventos de invalidación y contingencia, reglas de redondeo y holguras.

Asimismo se desarrollan ejemplos aplicados para el ingreso de información en secciones y campos de los DTE que
por su naturaleza se ha considerado importante brindar un detalle puntual sobre su uso, estos campos y secciones
son: “Número de Control”; “Cargos/Abonos que no afectan la base imponible”; “Descuento, Bonificación, Rebajas
por ítem o línea de operación” y “Monto Global de Descuento, Bonificación, Rebajas y otros”; ingreso de información
en campos relativos al pago; detalle de los ítems para el Comprobante de Donación; sección “Documentos
Relacionados”; y sección “Otros Documentos Asociados”

Representando una herramienta de apoyo al contribuyente para la configuración y desarrollo del Sistema de
Transmisión de DTE y lograr el objetivo de obtener la autorización como Emisor de DTE.


## Objetivo General

Proporcionar a los contribuyentes una herramienta que facilite la implementación del Sistema de Transmisión de
DTE en su organización, explicando las características generales del sistema y el planteamiento de ejemplos
aplicados al ingreso de información en la generación de DTE.

## Objetivos Específicos

- Describir las características generales del Sistema de Transmisión de DTE, el Modelo de la Facturación
    Electrónica y el firmado de los documentos electrónicos.
- Desarrollar ejemplos aplicados para el tratamiento de los campos " Cargos/Abonos que no afectan la base
    imponible”, “Descuento, Bonificación, Rebajas por ítem o línea de operación” y “Monto Global de
    Descuento, Bonificación, Rebajas y otros” en los DTE.”, secciones Documentos Relacionados, Otros
    Documentos Asociados y Formas de Pago y aplicación del catálogo de tributos por tipo de documento
- Presentar el funcionamiento de los Eventos de Invalidación y Contingencia aplicados para cada tipo de DTE.
- Ejemplificar el funcionamiento del redondeo y la holgura definida por la Administración Tributaria dentro
    de los DTE.


## I. Sistema de Transmisión de Documentos Tributarios Electrónicos (Sistema de Transmisión DTE)

Este sistema puede ser implementado por todos los contribuyentes, independiente a su categoría, nivel de
operaciones y fecha de inicio de emisión de DTE según el Programa de Implementación de los DTE; esta opción
implica que el sistema de facturación interno de los contribuyentes debe cumplir con los requisitos determinados
por la Administración Tributaria para la emisión de los documentos fiscales y además debe ser capaz de conectarse
con el Sistema de la DGII para transmitir dichos documentos hacia esta Administración.

## II. Modelo de Recepción Utilizado en los DTE

El modelo de recepción es previo a la entrega al receptor, en este modelo el emisor en su sistema interno de
facturación, genera el documento en formato electrónico compatible (JSON) incorporándole su firma electrónica;
posteriormente deberá enviarlo a la Administración Tributaria, quien aplicará los procesos de verificación de
cumplimiento de la estructura de datos, en caso que el documento electrónico cumpla con las validaciones, dicha
Administración le otorgará el “sello de recepción”, que le brinda la calidad de Documento Tributario Electrónico
(DTE). Si el documento electrónico no cumple con la estructura de datos establecida, será rechazado y se devolverá
un mensaje al emisor detallando los campos que no pasaron las verificaciones para su corrección y nuevo envío.

Una vez que el documento electrónico ha obtenido el sello de recepción, el Ministerio de Hacienda resguardará la
información contendida en el DTE, y proporcionará un servicio donde cualquier usuario podrá consultar el estado
de su DTE, por medio del código de generación.

```
Diagrama de Recepción
```

## III. Firma Electrónica

Se refiere, a todo proceso electrónico que indica la aceptación de un documento. En El Salvador las firmas
electrónicas pueden aplicarse a los documentos del tipo fiscal contemplados en el Código Tributario y que son los
siguientes: Comprobante de Crédito Fiscal Electrónico, Nota de Crédito Electrónica, Nota de Débito Electrónica, Nota
de Remisión Electrónica, Comprobante de Retención Electrónico, Factura Electrónica, Comprobante de Liquidación
Electrónico, Documento Contable de Liquidación Electrónico, Factura de Exportación Electrónica, Factura de Sujeto
Excluido Electrónica y Comprobante de Donación Electrónico.

## IV. Versión interpretada y legible del DTE

Está conformada por la figura del documento electrónico transmitido, en formato idóneo para ser visualizado por
medios digitales. Los medios de entrega serán acordados entre las partes, posibilitándose el uso de correo
electrónico, mensajería instantánea, una web service dispuesta por el proveedor para descarga de los DTE,
bluetooth, entre otros medios digitales y en casos excepcionales la impresión del mismo.

El diseño de la Versión Legible e interpretada del DTE queda a opción del contribuyente en concordancia a su giro,
pudiendo incorporar sus logos, marcas y slogans en los espacios y posición que estime.

## V. Estructuras de los Documentos Tributarios Electrónicos..............................................................................

Las Estructuras de los Documentos Tributarios Electrónicos son descripciones del contenido y de las especificaciones
que deben cumplirse según el documento tributario que se esté generando; de conformidad a lo establecido por la
Administración Tributaria. El detalle de las estructuras se encuentra contenido en la Normativa de Cumplimiento de
los Documentos Tributarios Electrónicos.

Actualmente se han definido las estructuras para los siguientes Documentos Tributarios Electrónicos:

```
1 Factura Electrónica 7 Comprobante de Liquidación Electrónico
2 Comprobante de Crédito Fiscal Electrónico 8 Documento Contable de Liquidación Electrónico
3 Nota de Remisión Electrónico 9 Factura de Exportación Electrónico
4 Nota de Crédito Electrónico 10 Factura de Sujeto Excluido Electrónica
5 Nota de Débito Electrónico 11 Comprobante de Donación Electrónico
6 Comprobante de Retención Electrónico
```
Cada estructura está dividida en campos y secciones.

Los campos de los documentos son la información (datos) que la Administración Tributaria requiere para generar,
transmitir y recibir un DTE; es importante mencionar que cada tipo de documento contiene sus campos con
información específica.

Las secciones son agrupaciones de campos con información relacionada, en que se han dividido las estructuras de
los documentos tributarios, estas secciones son:


**1. Sección “Identificación”:** Sección obligatoria incluida en todas las estructuras, donde se detallan las
    generales del documento que se está generando.
**2. Sección “Emisor” (Exportador/ Agente de retención/ Comisionista/ Agente perceptor):** Sección
    obligatoria incluida en todos los documentos tributarios, donde se describen los datos del emisor del
    documento. Es importante destacar que esta sección puede llamarse de otras formas dependiendo del
    documento que se esté generando, de la siguiente forma: Exportador para la FEXE, Agente de retención
    para el CRE, Comisionista para el CLE y Agente perceptor para el DCLE.
**3. Sección “Receptor” (Sujeto de retención/ Mandante/ Afiliado):** en esta sección se describen los datos
    generales del que está recibiendo el documento tributario. Puede variar su nombre dependiendo del
    documento realizado de la siguiente forma: Sujeto de retención para el CRE, Mandante para el CLE, Afiliado
    para el DCLE, Sujeto Excluido para el FSEE y Donante para el CDE.
**4. Sección “Otros documentos asociados”:** Esta sección es opcional para algunos documentos tributarios, y
    permite anexar información relevante de la operación; esta información puede ser del emisor (contratos,
    resoluciones, etc.), del receptor (contratos, resoluciones, autorizaciones, etc.), del médico (identificación,
    nombre, procedimiento, etc.) y del medio de transporte (identificación, conductor, entre otros).
**5. Sección “Venta a cuenta de terceros”:** Utilizada para describir la información del tercero al que se le está
    realizando la venta, incluida en casi todos los documentos tributarios, exceptuando el CRE, DCLE, CLE, FSEE
    y CDE.
**6. Sección “Cuerpo del documento”:** Sección obligatoria para todos los documentos tributarios, en esta
    sección se detalla la información propia de cada documento tributario.
**7. Sección “Resumen”:** Contiene un resumen general de la información contenida en el cuerpo del
    documento, es obligatoria y se encuentra en todos los documentos tributarios, excepto en el DCLE.
**8. Sección “Extensión”:** En esta sección se detallan los generales de los responsables por parte del emisor y/o
    receptor, si se cumplen los montos legales establecidos por operación y tipo de documento. (no aplica en
    FEXE, FSEE y CDE).
**9. Sección “Apéndice”:** Esta sección es opcional y se encuentra a disposición para incluir cualquier otra
    información dentro de los documentos.
**10. Sello de Recepción:** Al final de cada estructura se encuentra el “Sello de Recepción”, está no es una sección
    ni un campo de los documentos tributarios, únicamente es un recordatorio de que el Ministerio de
    Hacienda enviará un código encriptado llamado “Sello de Recepción” por cada documento tributario
    correctamente transmitido; mismo que deberá ser incluido en la versión legible de los DTE.


## VI. Eventos de Invalidación y Contingencia para el Sistema de Transmisión DTE

Durante la generación, transmisión y recepción de documentos electrónicos, se prevé que pueden ocurrir errores
que se identifiquen después de otorgado el sello de recepción; asimismo, que pudieran ocurrir imprevistos que
impiden la transmisión de estos documentos de manera normal hacia la Administración Tributaria.

El evento de invalidación es una solución factible, que permite al contribuyente corregir errores dados en los
Documentos Tributarios Electrónicos, y el Evento de Contingencia permite al contribuyente continuar generando los
documentos electrónicos, cuando existan casos de fuerza mayor, que impidan realizar la transmisión de éstos a la
Administración Tributaria de manera normal para la obtención de su respectivo sello de recepción.

Los eventos establecidos por esta Administración son estructuras que deben ser transmitidas en formato Json; pero
no se consideran un Documento Tributario Electrónico (DTE), son el medio por el cual el contribuyente informará a
la Administración Tributaria que ocurrió un error o que durante un periodo de tiempo no fue posible realizar la
transmisión de manera normal.

Desde el punto vista de la emisión de Documentos Tributarios Electrónicos, un evento se refiere al mensaje de datos
firmado electrónicamente que contiene información que se relaciona con un documento tributario electrónico
emitido previamente, que afecta o modifica dicho documento electrónico.

Para poder hacer uso de los eventos, el contribuyente deberá realizar previamente la configuración respectiva en su
sistema de facturación interno de acuerdo a los requerimientos de las estructuras proporcionadas y las condiciones
establecidas por la Administración Tributaria. Una vez se hayan realizado las adecuaciones necesarias al sistema,
deberá realizar el proceso de pruebas mínimas para cada uno de los eventos con respuesta exitosa, es decir que se
les otorgó el sello de recepción.

Las pruebas de dichos eventos serán consideradas al momento de autorizar a los contribuyentes como emisores de
documentos tributarios electrónicos. Ver Sección de este documento “Pruebas de Transmisión Satisfactorias
Mínimas para el Sistema de Transmisión DTE”.

## VII. Secciones de estructuras para los Eventos de Invalidación y Contingencia

La Administración Tributaria ha definido una estructura específica para la transmisión de los eventos

Para poder invalidar el DTE el emisor deberá enviar por medio del Sistema de transmisión DTE, la estructura Json del
evento diseñada por la Administración Tributara, que consta de 4 secciones que se describen a continuación:

**1. Identificación:** Esta sección contiene la información que identifica plenamente al evento tipo de evento
    como único en el universo de documentos electrónicos generados por el emisor, proporciona los campos
    necesarios para el correspondiente tratamiento del evento en relación a los demás sistemas de la DGII.
**2. Emisor del evento de invalidación:** Esta sección cuenta con los campos necesarios que permitan identificar
    al emisor y el tipo de establecimiento donde se está realizando el evento.
**3. Información del documento a invalidar o en contingencia**


```
Evento de Invalidación: Hace referencia a los datos que identifican al Documento Tributario Electrónico
que se desea invalidar (el cual ya ha obtenido el sello de recepción), e información básica que identifique al
receptor. Dicha información descrita en esta sección debe tener correspondencia entre los datos que
identifican al Documento Tributario Electrónico (DTE) y las generales del receptor que se describe en el
documento a invalidar.
```
```
Evento de Contingencia: Hace referencia a los datos que identifican al documento electrónico que se ha
generado fuera de línea, proporcionando los datos de tipo de documento y código de generación, que
permitirán una relación en el momento que se envíen los documentos electrónicos a la Administración
Tributaria para que puedan ser recepcionados. Estos se informarán a manera de lista hasta un máximo de
5,000 documentos por cada evento.
```
**4. Motivo**

```
Evento de invalidación: En esta sección se deberá ingresar el motivo de invalidación del DTE, e identificar
los responsables de efectuar y solicitar la invalidación; para una mejor comprensión de esta sección es
necesario ampliar la información sobre el uso del campo “tipo de invalidación” en el cual deberá ingresar
por medio de un código (según catálogo 024 Tipo de Invalidación), el motivo por el cual se invalidará el
documento, teniendo para elección las tres opciones siguientes:
```
1. Error en la Información del Documento Tributario Electrónico a invalidar.
2. Rescindir de la operación realizada.
3. Otro.

```
Por regla general, si el campo tipo de invalidación está lleno con la opción 1 o 3, será requerido que antes
de enviar el evento de invalidación del DTE, se tenga generado, transmitido y con sello de recepción el
documento que reemplaza al documento invalidado, debido a que la estructura del evento de invalidación
solicita introducir tanto el “código de generación del documento a invalidar” como el “código de generación
del documento que reemplaza al documento invalidado”. Ambos campos se encuentran la sección
“Identificación del Documento a Invalidar”. Esta condición no aplicará para los casos que el documento a
invalidar sea Nota de Crédito o Comprobante de Liquidación.
```
```
Evento de Contingencia: En esta sección se deberá ingresar los datos que identifiquen el motivo y el periodo
en que ocurrió el motivo de fuerza mayor que imposibilitó la transmisión en línea de los documentos
electrónicos a la Administración Tributaria.
```
## VIII. Evento de invalidación..............................................................................................................................

El evento de invalidación es un mensaje de datos firmado electrónicamente que se relaciona con un Documento
Tributario Electrónico, que se genera en ocasión de la invalidación del mismo.

Cuando ocurren errores que ocasionen la necesidad de invalidar el documento, el contribuyente emisor deberá
realizar un evento de invalidación dentro de los plazos establecidos por la Administración Tributaria por tipo de
documento.

Los DTE únicamente deberán invalidarse por razones justificadas, se consideran entre estas las siguientes:


- Error en la identificación del cliente.
- Error en el producto o servicio facturado.
- Error en la fecha de la operación.
- Error en el precio de los bienes o servicios (aplica únicamente para Factura y Factura de Exportación).
- Por devolución de los bienes.
- Cuando se rescinda totalmente la operación.

Para realizar el proceso de invalidación, debe enviarse el evento haciendo uso de la estructura establecida por la
Administración Tributario.

Es importante aclarar que este evento no elimina ni borra del sistema el DTE, sólo se asigna el estado “INVALIDADO”
al DTE que se le aplicó el evento de invalidación, dicho documento estará disponible con este estado en el momento
que se realice la consulta pública de los DTE. Invalidar un documento, no lo desaparece de la base de datos interna
de DGII.

El evento de invalidación también es sometido a verificación del cumplimiento de la estructura de datos establecida
por la Administración Tributaria.

**Proceso para transmitir el evento de invalidación**

El emisor debe generar el evento de invalidación en formato Json, ingresando el DTE que requiera ser invalidado (un
evento por cada documento que se requiera invalidar), en dicho evento debe indicarse el motivo de invalidación del
DTE según la codificación establecida en catálogo “CAT- 024 Tipo de Invalidación”, una vez esté completa la
información conforme a la estructura establecida, el emisor enviará el archivo de datos en formato Json desde su
plataforma al Sistema de transmisión DTE, por medio de modelo de recepción previo y tipo de transmisión normal,
la Administración Tributaria recibe esta información y se realiza el proceso de verificación del cumplimiento de la
estructura de datos, de no cumplir con dicha estructura, se rechazará el evento de la invalidación remitiendo un
mensaje de datos que indica el error identificado en el evento para su corrección.

El emisor deberá solventar el o los errores identificados, para transmitir nuevamente el evento de invalidación, y
una vez corregidos todos los errores indicados, la Administración Tributaria otorgará el sello de recepción. En el
momento que se otorgue el sello de recepción al evento de invalidación, se colocará estado de invalidado al DTE
que se ha informado mediante dicho evento.

El estado de los DTE invalidados podrá ser consultado a través del portal oficial del MH, por medio del código de
generación.

**Plazos para transmitir el evento de invalidación.**

```
Documento Tributario Electrónico Plazo para transmitir el evento de invalidación electrónico
```
```
Comprobante de Crédito Fiscal Electrónico.
Nota de Crédito Electrónica.
Nota de Débito Electrónica.
Nota de Remisión Electrónica.
Comprobante de Retención Electrónico.
Comprobante de Liquidación Electrónico.
```
```
Podrá realizarse dentro de un plazo máximo de un
día siguiente del otorgamiento del sello de
recepción del documento.
Ejemplo: Si el DTE obtuvo sello de recepción a las
7:30:00 (de la mañana) el contribuyente emisor
tendrá hasta las 23:59:59 del día siguiente para
```

```
Documento Tributario Electrónico Plazo para transmitir el evento de invalidación
electrónico
Documentos Contable de Liquidación Electrónico.
Factura Sujeto Excluido Electrónico
Comprobante de Donación
```
```
poder enviar el evento de invalidación para dicho
DTE.
```
```
Factura Electrónica.
Factura de Exportación Electrónica.
```
```
Podrá realizarse dentro del plazo de tres
meses contados a partir del otorgamiento del sello
de recepción del documento.
Ejemplo: Si el DTE obtuvo el sello de recepción el 11
de noviembre 2021 a las 7:30:00 (de la mañana) el
contribuyente emisor tendrá hasta el 11 de febrero
2022 a las 23:59:59 para poder enviar el evento de
invalidación para dicho DTE.
```
No se otorgará sello de recepción al evento de invalidación transmitido fuera de los plazos establecidos, por lo que
el DTE aún conservará su validez original.

**Condiciones especiales.**

1. Cuando la invalidación del DTE sea por razones formales, y que por lo tanto procede la emisión de un nuevo
    documento, deberá emitirse primero el documento que sustituya al que se está invalidando, para ingresar
    el código de generación del documento que reemplazará la operación en la estructura del evento de
    invalidación que se transmitirá. Esta condición no tendrá efecto cuando el documento a invalidar sea Nota
    de Crédito o Comprobante de Liquidación.
2. Cuando el motivo de la invalidación sea rescindir la operación deberá ingresar únicamente el código de
    generación del DTE a invalidar.

```
Ejemplo 1: Se emite factura electrónica con código de generación FF54E9DB-79C3-42CE-B432-
EC522C97EFB9 con error en el nombre del receptor el cual ya ha obtenido sello de recepción, por lo que es
necesario emitir factura electrónica con nombre correcto.
```
```
El emisor deberá primero emitir la nueva factura electrónica con el nombre correcto que tendrá un nuevo
código de generación (AD54E9BB-79A3-42AE-B432-EC522C97EFB7) y su respectivo sello de recepción,
posteriormente deberá generar el evento de invalidación describiendo en la sección “Identificación del
Documento a Invalidar” la información del DTE a invalidar, que incluye entre otros el “Código de generación
del DTE a invalidar” (Factura incorrecta FF54E9DB-79C3-42CE-B432-EC522C97EFB9). Asimismo, deberá
ingresar el “Código de generación del documento que corrige la operación” (segunda factura emitida y
recepcionada correctamente AD54E9BB-79A3-42AE-B432-EC522C97EFB7).
```

```
Ejemplo 2: Se emite factura electrónica por la venta de 2 sillas, por diferentes razones, el comprador decide
regresar el producto solicitando la devolución del valor pagado, por tanto, no procede la emisión de un
nuevo documento.
```
```
En este caso el tipo de invalidación a aplicar será rescindir la operación, para lo que el emisor deberá describir
la información de la factura electrónica incorrecta que se solicita en la sección “identificación del documento
a invalidar” y en el campo Código de generación del documento que reemplaza al documento a invalidar
deberá ingresar la palabra null.
```
```
Para anular facturas los campos “Tipo de documento de identificación (Receptor)”, “Número de documento
de Identificación (Receptor)” y “Nombre, denominación o razón social del contribuyente (Receptor”,
deberán completarse como “null” cuando los campos de la factura también se encuentren completados
como “null”.
```
```
En el evento de invalidación son de carácter obligatorio los siguientes campos:
```
1. “Nombre del responsable de invalidar el documento (Emisor)”,
2. “Tipo de documento de identificación del responsable de Invalidar el documento (Emisor)”
3. “Número de documento de Identificación del responsable de Invalidar el documento (Emisor)”
4. “Nombre de quien solicita invalidación el documento”
5. “Tipo de documento de identificación de quien solicita Invalidar el documento”
6. “Número de documento de Identificación de quien solicita Invalidar el documento”.

**Estructura para transmisión del evento de invalidación**

El detalle de la estructura para la transmisión del evento de invalidación se encuentra en la Normativa de
Cumplimiento de los DTE.

## IX. Evento de contingencia.

La contingencia se puede definir como un caso fortuito o fuerza mayor que le impide al facturador electrónico,
transmitir de forma inmediata los documentos electrónicos a la Administración Tributaria.

Evento de Contingencia es un mensaje de datos firmado electrónicamente que se relaciona con uno o varios
Documento Electrónico, que se generan en ocasión de casos que impiden realizar la transmisión de los DTE.

Cuando por motivo de fuerza mayor, el emisor no pueda realizar la transmisión de los documentos electrónicos a la
Administración Tributaria, este podrá generar los documentos electrónicos con sus propios procesos de
contingencia. Los contribuyentes son los encargados de diseñar y ejecutar en sus sistemas las condiciones que les
permitan generar los documentos electrónicos, es decir, deben prever todos los medios técnicos y administrativos
adecuados, así como los mecanismos alternativos que les garanticen el funcionamiento de sus servidores y equipos
en el proceso de la emisión y resguardo de los documentos electrónicos, para que una vez superada la situación que
les impida realizar la transmisión, estos puedan transmitir el evento de contingencia incorporando el detalle de todos
los documentos generados durante el periodo en el que ocurrió la situación de fuerza mayor que le impidió
transmitir dichos documentos a la Administración Tributaria de manera normal.


**Modelo de recepción para los DTE en generados contingencia.**

Para recepcionar los documentos que sean generados en contingencia, se ha diseñado el modelo de recepción
diferida, el cual consiste en que el emisor genera en su sistema interno de facturación, el documento electrónico en
formato JSON incorporándole su firma electrónica y entregará al receptor dicho documento por cualquier medio
electrónico. Es decir, que entregará al receptor el documento electrónico sin contar con el sello de recepción
(únicamente utilizado en contingencia).

Posteriormente superada la contingencia (reestablecida la conexión) deberá transmitir el evento de contingencia
donde informa la situación de contingencia y los documentos entregados sin sello de recepción; por último, el
contribuyente emisor debe transmitir a la Administración Tributaria dichos documentos generados en contingencia,
para que esta pueda correr los procesos establecidos en referencia a la verificación del cumplimiento de la estructura
de datos, una vez se reciba la información y esta cumpla con la estructura de datos establecida, la Administración
Tributaria otorgará el “sello de recepción”, brindando a cada uno de los documentos electrónicos la calidad de
Documento Tributarios Electrónico (DTE).

Si el documento electrónico no cumple con la estructura de datos establecida, será rechazado y se devolverá con un
mensaje al emisor detallando los campos que no cumplen con la información solicitada, para su corrección y nuevo
envío.

Una vez que el documento electrónico ha obtenido el sello de recepción, el Ministerio de Hacienda resguardará la
información contendida en el DTE, y proporcionará un servicio donde cualquier usuario podrá consultar el estado
del DTE, por medio del código de generación o el sello de recepción.

```
Diagrama de Recepción Diferido.
```

**Proceso para generar DTE “en contingencia”**

Se podrán emitir en contingencia los siguientes documentos electrónicos:

1. Factura Electrónica.
2. Comprobante de Crédito Fiscal Electrónico.
3. Nota de Remisión Electrónica.
4. Nota de Crédito Electrónica.
5. Nota de Debito Electrónica.
6. Factura de Exportación Electrónica.
7. Factura de Sujeto Excluido Electrónica.

Cuando se haga imposible la transmisión de estos documentos, el contribuyente podrá seguir operando con su
sistema de respaldo para operar fuera de línea, la estructura que se utilizará para poder generar estos documentos
en contingencia, será la misma estructura establecida por la DGII para realizar transmisión normal por tipo de
documento, con algunas particularidades del llenado de ciertos campos los cuales se detallan a continuación:

**Modelo de Facturación:** Debe ingresar la opción 2 “Modelo de Facturación Diferido"

**Tipo de Transmisión:** Debe ingresar la opción 2 "Transmisión por Contingencia"

**Tipo de Contingencia:** Debe ingresar un código que identifique el tipo de contingencia, de acuerdo a catálogo CAT-
005 Tipo de Contingencia.

**Motivo de Contingencia:** Deberá explicar el motivo de contingencia cuando en campo "tipo de contingencia" se
ingrese la opción 5 - Otro motivo (si se requiere podrá ampliar el motivo de contingencia cuando tipo de contingencia
sea diferente a 5).

**Proceso para transmitir documentos electrónicos en contingencia**

Los contribuyentes están obligados a transmitir a la Administración Tributaria los documentos generados en
contingencia.

Para poder transmitir estos documentos electrónicos generados en contingencia, la Administración Tributaria ha
establecido el proceso de transmisión una vez que se supere la situación imprevista que le imposibilitó la
transmisión, lo cual se describe a continuación:

**MOMENTO 1**

Ocurrencia de fuerza mayor que impida al contribuyente emisor la transmisión del DTE, en los siguientes casos:

```
a) Falla en conexiones del sistema del emisor
```
```
b) Falla en el suministro del servicio de Internet por el proveedor del emisor
```
```
c) Falla en el suministro del servicio de energía eléctrica por el proveedor del emisor que le impidan realizar
la transmisión de los documentos electrónicos
```

```
d) No disponibilidad de sistema del MH para realizar la recepción
```
El contribuyente podrá identificar que está en contingencia cuando al momento de enviar un DTE, el Sistema de
transmisión DTE no responda después 5 segundos, o si al momento de enviar un DTE, el servicio del emisor falla y
no procesa la respuesta del servicio de recepción. Cuando tengan ocurrencia estos hechos se deberá aplicar uno a
uno los pasos establecidos en la “Política de reintentos” la cual se detalla en la “Guía de Integración Tecnológica”.
Una vez aplicada esta política de reintentos y no se logra la transmisión ni la recepción de los DTE el contribuyente
deberá operar en contingencia.

El contribuyente emisor continuará generando y firmando el archivo Json del documento electrónico dando
cumplimiento con los requisitos de la estructura establecida por la Administración Tributaria para cada tipo de
documento tributario electrónico y con el llenado de los campos específicos. Debido a que estos documentos no
pueden ser transmitidos a la Administración Tributaria de manera normal, sino que posteriormente de haber
superado la situación que impidió realizar la transmisión en línea, el emisor deberá en el momento de la generación
del documento electrónico, ingresar en el campo “Modelo de facturación” la opción “2 modelo de facturación
Diferido”, en el campo “tipo de transmisión” la opción 2 (transmisión por contingencia) y además en el campo “tipo
de contingencia” ingresar el motivo de la contingencia con base al catálogo establecido.

**MOMENTO 2**

**Envío de evento de contingencia por el contribuyente emisor.**

Una vez superada la causa de fuerza mayor que dio origen a los documentos electrónicos en contingencia, el
contribuyente emisor deberá de generar, firmar y transmitir un **“Evento de Contingencia”.** Para transmitir el evento
antes mencionado el emisor de documentos tributarios electrónicos tendrá un plazo máximo de 24 horas para
transmitir el evento, contadas a partir del cese de la situación de fuerza mayor que provocó la contingencia.

Mediante el evento de contingencia se deben informar los códigos de generación de todos los documentos
electrónicos que fueron generados mientras ocurrió la situación de fuerza mayor, detallando los datos que
identifican al documento electrónico en la estructura establecida por la Administración Tributaria en la sección
detalle de documentos electrónicos en contingencia, donde podrá describir desde 1 hasta un máximo de 5,
documentos electrónicos generados en contingencia.

El envío de este evento de contingencia es un requisito previo para poder transmitir el lote de los citados
documentos electrónicos, para que puedan ser procesados por la Administración Tributaria; el emisor transmitirá el
evento por medio de un archivo JSON conforme a la estructura definida, dicho archivo se deberá transmitir a través
del Sistema de transmisión DTE con modelo de recepción previo y tipo de transmisión normal.

Una vez que el contribuyente emisor transmita el evento de contingencia, la Administración Tributaria lo recibirá y
realizará el proceso de verificación del cumplimiento de la estructura de datos establecida por la Administración
Tributaria y una vez habiendo superado los mismos, dará respuesta a través de un sello de recepción al evento
transmitido.

Cuando el evento de contingencia no cumpla con la estructura de datos establecida se rechazará, se regresará por
medio del Sistema de transmisión DTE al emisor, indicando el error identificado para su corrección en un plazo
máximo de 24 horas después de que el evento haya sido rechazado. El emisor deberá solventar, para transmitir


nuevamente el evento de contingencia, y una vez corregidos todos los errores indicados, la Administración Tributaria
colocará el sello de recepción para posteriormente almacenar este evento para su conservación en la base de datos
de DGII.

**MOMENTO 3**

**Transmisión de documentos electrónicos en contingencia.**

Una vez el **“Evento de Contingencia”** haya obtenido el sello de recepción por parte de la Administración Tributaria,
el contribuyente emisor deberá transmitir un archivo Json firmado electrónicamente que compile el lote de
los documentos electrónicos generados en contingencia que fueron informados previamente en el evento (Es decir
que no podrán incluir en este lote, documentos que no hayan sido informados en contingencia o que se realizaron
en transmisión normal sin inconvenientes para su transmisión).

El lote de los documentos electrónicos generados en contingencia una vez transmitidos se procesará documento por
documento, a los cuales se les aplicará un proceso de verificación del cumplimiento de la estructura de datos
establecida por la Administración Tributaria por tipo de documento tributario electrónico.

Se tendrá un plazo máximo de 72 horas contadas a partir del otorgamiento del sello de recepción del evento de
contingencia para poder enviar el lote de todos los documentos electrónicos que fueron informados en dicho evento,
para que una vez transmitidos, a estos, les sea aplicado el proceso de verificación del cumplimiento de la estructura
de datos establecida por la Administración Tributaria y una vez superados estos requisitos puedan obtener el sello
de recepción correspondiente a cada uno de los documentos transmitidos e informados previamente en el evento
de superada la contingencia.

**Notas importantes:**

- Si el contribuyente no realiza la transmisión del evento de contingencia o no realiza la transmisión de los
    DTE reportados en el evento dentro del plazo establecido en la resolución de autorización respectiva, deberá
    informar y justificar por escrito a la DGII, las razones del incumplimiento y solicitar autorización de prórroga
    del plazo establecido, a efecto que se permita la correspondiente transmisión del evento y de los citados
    documentos.
- En las fechas previas a la implementación del Plan de Incorporación, los contribuyentes están sujetos a las
    condiciones bajo las cuales se les ha otorgado la respectiva autorización.
- Queda facultada la Administración Tributaria para revocar la autorización otorgada para emitir DTE cuando
    verifique que el contribuyente no resguarda la seguridad, cumplimiento y exactitud de los impuestos
    causados, de acuerdo a las disposiciones legales pertinentes y a lo establecido en la respectiva autorización.
- En el evento de contingencia los siguientes campos son de carácter obligatorio: “Nombre del responsable
    del establecimiento”, “Tipo de documento de identificación”, “Número de documento de identificación del
    responsable”.

**Estructura para transmisión de evento de contingencia**


- El detalle de la estructura para la transmisión del evento de contingencia se encuentra en la Normativa de
    Cumplimiento de los DTE.

## X. Pruebas de Transmisión Satisfactorias Mínimas para el Sistema de Transmisión DTE...................................

```
N° Tipo de Documento Electrónico
Sistema de
Transmisión
1 Factura 90
2 Comprobante de Crédito Fiscal 75
3 Nota de Remisión 50
4 Nota de Crédito 50
5 Nota de Débito 25
6 Comprobante de Retención 50
7 Comprobante de Liquidación 75
8 Documento^ Contable^ de^ Liquidación^50
9 Factura de Exportación 90
10 Factura de Sujeto Excluido 25
11 Comprobante de Donación 25
```
```
N° Tipo de Evento
Sistema de
Transmisión
1 Evento^ de^ Invalidación^5
2 Evento^ de^ Contingencia^5
```
PARTE 2


## XI. Detalle de la estructura Número de Control.

**Número de Control**

**Detalle de la estructura Número de Control:**

El Número de Control estará dividido en 4 Secciones las cuales son:

**Primero Sección:** Esta Sección inicia con las letras "DTE" que hace referencia a los Documentos Tributarios

Electrónicos. (Las siglas DTE deben escribirse en mayúsculas).

**Segunda Sección:** Código de Tipo de Documento, en esta Sección se detallará el código numérico del tipo de

documento a emitir según catálogo "CAT-002 Tipo de Documento" para Factura será 01, (y así

respectivamente según el código asignado al documento a emitir).

**Tercera Sección:** Esta Sección contiene 8 dígitos Alfanuméricos los cuales representan el código de Casa

Matriz, sucursal o Agencia, Bodega y/o Predio o Patio (4 dígitos Alfanumérico) seguido del código de punto

venta (4 dígitos alfanumérico).

**Cuarta Sección:** Esta Sección contienen 15 dígitos numéricos los cuales serán secuenciales y se reiniciarán

cada año.

Por lo tanto, el Número de Control está compuesto por 31 caracteres contando los guiones.

Para efecto de ejemplo se presenta el siguiente número de Control donde es de aclarar, que por periodo de

transición la tercera sección actualmente estaría compuesta por 8 caracteres numéricos.

Este número de control no debe de repetirse en un año calendario.

**Ejemplos de numero de control según tipo de documentos a emitir.**

DTE- 01 - 12345678 - 000000000000001 para Factura Electrónica

DTE- 03 - 12345678 - 000000000000001 para Comprobante de Crédito Fiscal Electrónico

DTE- 05 - 12345678 - 000000000000001 para Nota de Crédito Electrónica


## XII. Tratamiento de campo "Cargos/Abonos que no afectan la base imponible”

Este campo está contemplado en las estructuras de Factura Electrónica, Comprobante de Crédito Fiscal Electrónico
y Factura de Exportación Electrónica; este campo tiene un uso particular, como su nombre lo indica estos valores no
están sujetos a impuestos y serán sumados o restados según corresponda, hasta el campo “Total a Pagar”.

Estos valores se ingresarán en el cuerpo del documento como un ítem más o línea de operación y podrán repetirse
“n” veces. Es importante aclarar que en este campo se podrá ingresar valores positivos y negativos, se ingresarán
valores positivos cuando se desee realizar un cargo al cliente el cual será sumado al total a pagar y se ingresará en
valores negativos cuando se desee realizar alguna devolución o saldo a favor del cliente el cual restara el Total a
Pagar.

Cuando se adicionen ítems con esta particularidad deberá tomar en cuenta las indicaciones de llenado en la
estructura de estos documentos en la sección cuerpo según sea el tipo de documento que se está generando, tal
como se describen a continuación:

```
Indicaciones
" Cargos/Abonos que no afectan la base imponible”.
Sección cuerpo Dato/Valor Requerido
```
```
N° de ítem
ítems que corresponda en secuencia con el anterior
descrito
Tipo de ítem Según catálogo: bien, servicio, ambos
Cantidad 1
Código null o código
Tributo sujeto a cálculo de IVA. null
Unidad de Medida 99
Descripción: ingresar descripción del cargo o pago
Precio Unitario $0.00
Descuento, Bonificación, Rebajas por ítem $0.00
Ventas No Sujetas $0.00
Ventas Exentas $0.00
Ventas Gravadas/ (ventas afectas para FEXE) $0.00
Código del Tributo Null
Precio sugerido de venta $0.00
Cargos/Abonos que no afectan la base imponible Valor positivo o negativo correspondiente ($)
```
**NOTA:** Para el caso de factura de exportación no aplican los campos ventas no sujetas y ventas exentas.

El valor consolidado o sumatoria de todos los ítems para los que se ingresen valores en campo “Cargos/Abonos que
no afectan la base imponible” se debe reflejar en el campo “Total Cargos/Abonos que no afectan la base imponible”
en el resumen del documento.


## XIII. Aplicación del Catálogo “Tributos”

El catálogo de tributos está dividido en tres secciones las cuales se describen a continuación:

**Sección 1: Tributos aplicados por ítem reflejados en el resumen del DTE.**

```
Código Nombre del Tributo DTE al que aplica
20 Impuesto al Valor Agregado 13% CCFE, NRE, NCE, NDE, CLE
C3 Impuesto al Valor Agregado (exportaciones) 0% FEXE Y CLE
59 Turismo: por alojamiento (5%) FE, CCFE, NRE, NCE, NDE, CLE
71 Turismo: salida del país por vía aérea $7.00 FE, CCFE, NRE, NCE, NDE, CLE
D1 FOVIAL ($0.20 Ctvs. por galón) FE, CCFE, NRE, NCE, NDE, CLE
C8 COTRANS ($0.10 Ctvs. por galón) FE, CCFE, NRE, NCE, NDE, CLE
D5 Otras tasas casos especiales FE, CCFE, NRE, NCE, NDE, CLE
D4 Otros impuestos casos especiales. Uso interno del M.H.
```
Para estos tributos tienen aplicación los documentos tributarios: Factura Electrónica, Comprobante de Crédito Fiscal
Electrónico, Nota de Remisión Electrónica, Nota de Crédito Electrónica, Nota de Débito Electrónica, y Comprobante
de Liquidación Electrónico y Factura de Exportación Electrónica.

Se ingresará el código de tributo que corresponda dentro de cada ítem, en el campo “código de tributo”, se podrá
aplicar varios códigos de tributo diferentes contenidos en esta sección, separados por comas, estos tributos se verán
reflejados en la sección resumen del documento en los campos Resumen código de tributo, Nombre del tributo y
valor de tributo de la siguiente manera:

- RESUMEN CÓDIGO DE TRIBUTO: Se ingresará de manera consolidada (una sola vez) cada tipo de tributo por
    medio del código que haya aplicado por ítem.
- NOMBRE DEL TRIBUTO: Se ingresará de manera consolidada (una sola vez) la descripción correspondiente
    por cada tipo de tributo detallado mediante código en campo "Resumen Código de Tributo".
- VALOR DE TRIBUTO: Debe contener la sumatoria consolidada de los montos de tributos calculados por
    ítems, de forma separada por tipo de tributo.

**Ejemplo de consolidación de tributos:**

Se genera un CCFE con 10 ítem que suman 50 galones de combustible y ventas gravadas por $200.00 (en cada uno
de los ítems se ingresan en campo “Código de Tributo” [“20”, “D1”, “C8”] (impuesto al Valor Agregado 13% (20),
FOVIAL (D1) y COTRANS s (C8)). Se deberá presentar de manera consolidada en la sección resumen una sola vez el
código, el nombre y el valor correspondiente a los tributos aplicados de la siguiente forma:


```
Resumen Código de Tributo Nombre del Tributo Valor de Tributo
20 Impuesto al Valor Agregado 13% $26.00
D1 FOVIAL ($0.20 Ctvs. por galón) $10.00
C8 COTRANS ($0.10 Ctvs. por galón) $5.00
```
**Notas:** Para el caso específico del tributo “C3-Impuesto al Valor Agregado (exportaciones) 0%” tendrá aplicación
únicamente para Factura de Exportación Electrónica y cuando lo requiera también se aplicará en el Comprobante
de Liquidación Electrónico. (en ambos casos deberá detallarse, aunque su valor sea $0.0)

**Sección 2: Tributos aplicados por ítem reflejados en el cuerpo del documento**

```
Código Nombre del Tributo
A8 Impuesto Especial al Combustible (0%, 0.5%, 1%)
```
(^57) impuesto industria de Cemento
**90** Impuesto especial a la primera matrícula
**D4** Otros impuestos casos especiales
**D5** Otras tasas casos especiales
**A6**
Impuesto ad- Valorem, armas de fuego, municiones explosivas y
artículos similares
Para estos tributos tienen aplicación los documentos tributarios: Factura Electrónica, Comprobante de Crédito Fiscal
Electrónico, Nota de Crédito Electrónica, Nota de Débito Electrónica y Nota de Remisión Electrónica.
Se deberá detallar como un ítem independiente dentro del cuerpo del documento, considerando que los valores
aquí descritos corresponden a valores calculados en concepto de aplicación de los tributos descritos en la tabla
anterior. Para este caso se deberá tomar en cuenta las indicaciones de llenado de los campos contenidos en la
sección cuerpo de la estructura según tipo de documento tributario electrónico de la manera siguiente:
**CAMPOS FE CCFE NCE, NDE y NRE
N° de ítem** Ítem que corresponda en secuencia con el anterior descrito
Ítem que corresponda en
secuencia con el anterior
descrito
Ítem que corresponda en
secuencia con el anterior
descrito
**Tipo de ítem** 4 (Otros tributos por ítem) 4 (Otros tributos por ítem) 4 (Otros tributos por ítem)
**Cantidad** 1 1 1
**Código** Null o código interno que maneje al contribuyente. maneje al contribuyente.Null o código interno que maneje al contribuyente.Null o código interno que
**Tributo sujeto a cálculo
de IVA**
uno de los códigos de tributo
contenidos en la sección 2 del
catálogo 015 "tributos"
uno de los códigos de
tributo contenidos en la
sección 2 del catálogo 015
"tributos"
uno de los códigos de tributo
contenidos en la sección 2 del
catálogo 015 "tributos"
**Unidad de Medida** 99 99 99
**Descripción** Ingresar descripción Ingresar descripción Ingresar descripción
**Precio Unitario**^ incluyendo IVAValor calculado del tributo Vsin IVAalor calculado del tributo IVAValor calculado del tributo sin
**Descuento, Bonificación,
Rebajas por ítem** $0.00^ $0.00^ $0.00^


```
Ventas No Sujetas $0.00 $0.00 $0.00
Ventas Exentas $0.00 $0.00 $0.00
```
```
Ventas Gravadas^ (resultado de precio por cantidad)Valor del impuesto calculado
```
```
Valor del impuesto
calculado (resultado de
precio por cantidad)
```
```
Valor del impuesto calculado
(resultado de precio por
cantidad)
Código del Tributo Null 20 - IVA 20 - IVA
Precio sugerido de venta $0.00 $0.00 N/A
Cargos/Abonos que no
afectan la base imponible $0.00^ $0.00^ N/A^
```
**Ejemplo:**

Se realiza venta de 100 bolsas de cemento a $8.00 c/u con CCFE.
En este caso deberá detallarse dos ítems, uno con el detalle de la venta y otro con el detalle del impuesto; en el ítem
1 detallará los datos que identifiquen al bien en la sección cuerpo dejando el campo “Tributo sujeto a cálculo de
IVA.” con null y el campo “código de tributo” con el código 20 que corresponde a IVA 13%.

En el segundo ítem deberá ingresar el valor que corresponde a impuesto a industria de Cemento considerando las
indicaciones de llenado en la sección cuerpo, tal como que se describen para el uso de tributos aplicados por ítem
reflejados en el cuerpo del documento (en campo “Tipo de ítem” la opción 4-Otros tributos por ítem), en campo
“Tributo sujeto a cálculo de IVA.” el código 57 que corresponde a tributo impuesto industria de cemento y en campo
“código de tributo” deberá ingresar el código 20 que corresponde a IVA 13%).

En la sección cuerpo del CCF se deberá ingresar tal como se describe en la siguiente tabla:

De esta manera el total de ventas gravadas para este CCFE sería de $832.00.

**Consideraciones para los tributos contenidos con el mismo código en la sección 1 y 2**

Los códigos de tributo D4 y D5 se encuentran en la sección 1 y 2 pero con distinta aplicación, a esta razón es
importante aclarar lo siguiente:

- El código de D4 se encuentra en la sección 1 y 2 del catálogo de tributos y es de uso interno del M.H.
- Si código D5 se detallan en el campo “Código de tributo” este debe reflejar su valor consolidado en la
    sección resumen en los campos “Resumen Código de Tributo”, “Nombre del tributo” y “valor del tributo”.

```
Cuerpo del Documento
```
```
N° De
ítem
```
```
Tipo
de
Ítem
```
```
Número de
documento
relacionado
Cantidad Código
```
```
Tributo
sujeto a
cálculo de
IVA.
```
```
Unidad de
Medida Descripción^
Precio
Unitario
```
```
Descuento,
Bonificación
Rebajas por
ítem
```
```
Ventas No
Sujetas
Ventas
Exentas
Ventas
Gravadas
```
```
Código
del
Tributo
```
```
Precio
sugerido
de venta
```
```
Cargos/Abonos
que no afectan la
base imponible
```
```
1 1 null 100 null null 59
```
```
Super
cemento
fuerte
```
```
$8.00 $ 0.0 $ 0.0 $ 0.0 $ 800.00 20 $ 0.0 $ 0.0
```
```
2 4 null 1 null 57 99
```
```
Impuesto
industria
de
Cemento
```
```
$32.00 $ 0.0 $ 0.0 $ 0.0 $ 32.00 20 $ 0.0 $ 0.0
```

- Si código D5 se ingresan en el campo “Tributo sujeto a cálculo de IVA” este hace referencia a que se detallará
    en el ítem es un impuesto que está sujeto a IVA y debe ser reflejado en el campo ventas gravadas y seguir
    las indicaciones de llenado de campos establecidas en este anexo para los tributos de la sección 2.

**Sección 3: impuestos aplicados por ítem de uso informativo reflejados el resumen del documento.**

```
Código Nombre del Tributo
```
```
C5 Impuesto ad- valorem por diferencial de precios de bebidas alcohólicas (8%)
C6 Impuesto ad- valorem por diferencial de precios al tabaco cigarrillos (39%)
C7 Impuesto ad- valorem por diferencial de precios al tabaco cigarros (100%)
```
(^19) Fabricante de Bebidas Gaseosas, Isotónicas, Deportivas, Fortificantes, Energizante o Estimulante
(^28) Importador de Bebidas Gaseosas, Isotónicas, Deportivas, Fortificantes, Energizante o Estimulante
(^31) Detallistas o Expendedores de Bebidas Alcohólicas
(^32) Fabricante de Cerveza
(^33) Importador de Cerveza
(^34) Fabricante de Productos de Tabaco
(^35) Importador de Productos de Tabaco
(^36) Fabricante de Armas de Fuego, Municiones y Artículos similares
(^37) Importador de Arma de Fuego Munición y Artículos similares
(^38) Fabricante de Explosivos
(^39) Importador de Explosivos
(^42) Fabricante de Productos Pirotécnicos
(^43) Importador de Productos Pirotécnicos
(^44) Productor de Tabaco
(^50) Distribuidor de Bebidas Gaseosas, Isotónicas, Deportivas, Fortificantes, Energizante o Estimulante
(^51) Bebidas Alcohólicas
(^52) Cerveza
(^53) Productos del Tabaco
(^54) Bebidas Carbonatadas o Gaseosas Simples o Endulzadas
(^55) Otros Específicos
(^58) Alcohol
(^77) Importador de Jugos, Néctares, Bebidas con Jugo y Refrescos
(^78) Distribuidor de Jugos, Néctares, Bebidas con Jugo y Refrescos
(^79) Sobre Llamadas Telefónicas Provenientes del Ext.
(^85) Detallista de Jugos, Néctares, Bebidas con Jugo y Refrescos
(^86) Fabricante de Preparaciones Concentradas o en Polvo para la Elaboración de Bebidas
(^91) Fabricante de Jugos, Néctares, Bebidas con Jugo y Refrescos
(^92) Importador de Preparaciones Concentradas o en Polvo para la Elaboración de Bebidas
**A1** (^) Específicos y Ad-valorem
**A5** (^) Bebidas Gaseosas, Isotónicas, Deportivas, Fortificantes, Energizantes o Estimulantes
**A7** (^) Alcohol Etílico
**A9** (^) Sacos Sintéticos


Para estos tributos tienen aplicación los documentos tributarios: Factura Electrónica y Comprobante de Crédito
Fiscal Electrónico.

Se ingresará el código de tributo que corresponda dentro de cada ítem, en el campo “código de tributo”, la aplicación
de estos tributos solo será para uso informativo, es decir no se detallarán en representación gráfica ni tendrán efecto
en los valores del documento.

Se reflejarán a nivel informativo en la sección resumen en los campos:

- **RESUMEN CÓDIGO DE TRIBUTO:** donde se visualizará una sola vez cada tipo de tributo por medio del código
    que haya aplicado por ítem.
- **NOMBRE DEL TRIBUTO:** donde se visualizará una sola vez cada tipo de tributo por medio de la descripción
    que corresponda al código detallado en campo RESUMEN CÓDIGO DE TRIBUTO.
- **VALOR DE TRIBUTO:** Debe contener la sumatoria consolidada de los montos de tributos calculados por
    ítems, de forma separada por tipo de tributo.

**Ejemplo: Ejemplo de consolidación de tributos**

Se genera un CCFE con 10 ítem que suman ventas gravadas por $200.00, en todos los ítem se ha aplicado los tributos
impuesto al Valor Agregado 13% (20) e Impuesto ad- valoren por diferencial de precios de Bebidas Alcohólicas 8%
(C5), en campo “código de tributo“ [“20”,”C5”]; en supuesto que exista una diferencia entre precios de $80.00, se
deberá presentar de manera consolidada una sola vez el código, el nombre y el valor correspondiente a los tributos
aplicados en la sección resumen.

```
Resumen Código de Tributo Nombre del Tributo Valor de Tributo
20 Impuesto al Valor Agregado 13% $26.00
C5 Impuesto ad- Valorem por dif. (8%) $6.40
```
El “total a pagar” de esta operación sería $226.00 (no se considera los $6.40 debido a que solo es de uso informativo).

## XIV. Uso de la Sección Documentos Relacionados.

Para los Documentos Tributarios Electrónicos en cuya estructura contenga sección de documentos relacionados se
podrán hacer referencia a documentos que se hayan emitido con anterioridad que den origen a la generación de un
documento posterior. Haciendo uso de esta sección podrá realizar la relación de un máximo de 50 documentos que
entre sí, podrían sumar hasta un máximo de 2000 ítems o líneas.

**Documentos electrónicos a los que aplica esta sección**

La sección de relacionados se encuentra contemplada para los siguientes documentos tributarios electrónicos:

1. Factura Electrónica
2. Comprobante de Crédito Fiscal Electrónico
3. Nota de Remisión Electrónica
4. Nota de Crédito Electrónica


5. Nota de Debito Electrónica

El uso de esta sección será obligatorio para Nota de Crédito Electrónica y Nota de Débito Electrónica. Para los casos
de Factura Electrónica, Comprobante de Crédito Fiscal Electrónico y Nota de Remisión Electrónica será requerido
por tipo de operación, es decir, que cuando la operación no lo requiera (cuando el documento a generar no sea a
causa de otro documento tributario electrónico previo) deberá completar la sección con la palabra null.

Estos hasta 50 documentos que pueden relacionarse en otro DTE deben ser del mismo tipo es decir, si se relaciona
Comprobantes de Crédito Fiscal a una Nota de Crédito Electrónica, no pueden en este misma Nota de Crédito
Electrónica relacionar Comprobantes de Crédito Fiscal y Comprobantes de Retención. En relación a estos
parámetros establecidos es necesario describir algunas condiciones con el fin de aclarar dudas sobre el uso de esta
sección, que información debe completar y como se relacionará en el cuerpo del documento.

**Campos de la sección Documentos Relacionados**

La sección consta de 4 campos, en los que podrá describir datos generales de los documentos que se están
relacionando, pudiendo encontrarse estos emitidos en forma física o electrónica.

1. **Tipo de Documento Tributario Relacionado:** Deberá indicar el código del documento relacionado según el
    catálogo; dicho código deberá ingresarse respetando las condiciones descritas en la estructura de cada uno del
    documento antes mencionados.
2. **Tipo de Generación del Documento Tributario Relacionado:** Deberá indicar si el documento que va a
    relacionar, fue generado de manera física ingresando el código 1 o de manera electrónica con el código 2.
3. **Número de documento relacionado** : Se ingresará el código de generación si el documento relacionado ha sido
    emitido de forma electrónica y deberá ingresar el número de correlativo si el documento ha sido emitido de
    forma física. Podrá ingresar documentos en físico y electrónicos en un mismo documento siempre y cuando
    sean del mismo tipo.
4. **Fecha de Generación del Documento Relacionado:** deberá indicar la fecha en que fue generado el documento
    que se esté relacionando.

**Uso de sección relacionados**

Para poder relacionar los DTE en FE, CCFE, NRE o los ajustes en NCE y NDE deberá describir en la sección documentos
relacionados la información que identifica al documento que se está informando/ajustando y en el cuerpo del DTE
que se está generando, se detallará los ítems que correspondan a cada uno de los documentos que se van a
relacionar.

Ejemplo:

Se requiere ajustar con Nota de Crédito Electrónica los siguientes 3 CCF:

**CCF 1: S221001345 (físico) FECHA 13/02/2022**

```
Cuerpo del Documento
```
**N° de ítem Cantidad Unidad de Medida Descripción** (^) **UnitarioPrecio
Descuento,
Bonificación,
Rebajas por
ítem
Ventas No
Sujetas
Ventas
Exentas
Ventas
Gravadas**
1 10 Unidades Camisas/Negro $ 10.00 $ 0.00 $ 0.00 $ 0.00 $ 100.00


```
2 15 Unidades Centros $ 5.00 $ 0.00 $ 0.00 $ 0.00 $ 75.00
3 25 Unidades Jeans $ 20.00 $ 0.00 $ 0.00 $ 0.00 $ 500.00
4 5 Unidades Cinturón $ 20.00 $ 0.00 $ 0.00 $ 0.00 $ 100.00
```
### CCFE 2: FF54E9DB-79C3-42CE-B432-EC552C97EFB9 FECHA 14/02/2022

### CCFE 3: FF54E9DB-79C3-42CE-B432-EC552C97EF33 FECHA 15/02/2022

```
Se realizará ajuste por devolución de productos para el CCF1 por devolución de una camisa negra y dos jeans, para
el CCFE 2 se aplicará el 10% de descuento en todos los productos el cual por error no fue aplicado en el CCFE, y a
CCFE 3 se corrige precio de carteras de $25.00 a $22.00.
```
```
Con Nota de Crédito Electrónica, este ajuste se puede realizar en una sola NCE de la siguiente manera:
```
```
Primero, en la sección Documentos Relacionados de la NCE debo detallar los datos para cada uno de los CCF a
ajustar de la siguiente manera:
```
```
Sección documentos relacionados Nota de Crédito Electrónica
```
```
Sección Documentos Relacionados
```
```
Tipo de Documento
Tributario
Relacionado
```
```
Tipo de
Generación del
Documento
Tributario
relacionado
```
```
Número de documento relacionado Fecha de Generación del Documento Relacionado
```
```
03 1 S221001345 13/02/2022
03 2 FF54E9DB-79C3-42CE-B432-EC552C97EFB9 14/02/2022
03 2 FF54E9DB-79C3-42CE-B432-EC552C97EF33^ 15/02/2022
```
```
Cuerpo del Documento
```
**N° De
ítem**

```
Tipo
de
Ítem
```
```
Número de
documento
relacionado
Cantidad Código
```
```
Tributo
sujeto a
cálculo de
IVA.
```
```
Unidad
de
Medida
Descripción Precio Unitario
```
```
Descuento,
Bonificación
Rebajas por
ítem
```
```
Ventas No
Sujetas
Ventas
Exentas
Ventas
Gravadas
```
```
Código
del
Tributo
```
```
Precio
sugerido
de venta
```
```
Cargos/Abonos
que no afectan la
base imponible
1 1 Null 10 Null Null 59 Camisas/negro $ 10.00 $ 0.00 $ 0.00 $ 0.00 $100.00 20 $ 0.00 $ 0.00
2 1 Null 15 Null Null 59 Centros $ 5.00 $ 0.00 $ 0.00 $ 0.00 $75.00 20 $ 0.00 $ 0.00
3 1 Null 25 Null Null 59 Jeans $20.00 $ 0.00 $ 0.00 $ 0.00 $500.00 20 $ 0.00 $ 0.00
4 1 Null 5 Null Null 59 Cinturón $20.00 $ 0.00 $ 0.00 $ 0.00 $100.00 20 $ 0.00 $ 0.00
```
```
Cuerpo del Documento
```
```
N° De
ítem
```
```
Tipo
de
Ítem
```
```
Número de
documento
relacionado
```
```
Cantidad Código
```
```
Tributo
sujeto a
cálculo de
IVA.
```
```
Unidad
de
Medida
```
```
Descripción Precio Unitario
```
```
Descuento,
Bonificación
Rebajas por
ítem
```
```
Ventas No
Sujetas
Ventas
Exentas
Ventas
Gravadas
```
```
Código
del
Tributo
```
```
Precio
sugerido
de venta
```
```
Cargos/Abonos
que no afectan la
base imponible
1 1 Null 5 Null Null 59 Camisas/negro $ 10.00 $ 0.00 $ 0.00 $ 0.00 $ 5 0.00 20 $ 0.00 $ 0.00
2 1 Null 15 Null Null 59 Centros $ 5.00 $ 0.00 $ 0.00 $ 0.00 $75.00 20 $ 0.00 $ 0.00
3 1 Null 25 Null Null 59 Jeans $ 1 0.00 $ 0.00 $ 0.00 $ 0.00 $ 250 .00 20 $ 0.00 $ 0.00
4 1 Null 5 Null Null 59 Cinturón $20.00 $ 0.00 $ 0.00 $ 0.00 $100.00 20 $ 0.00 $ 0.00
5 1 Null 10 Null Null 59 Cartera $25.00 $ 0.00 $ 0.00 $ 0.00 $250.0 0 20 $ 0.00 $ 0.00
```

Posteriormente en la sección cuerpo de la nota de crédito se hará ajuste del ítem 1 y 3 del **CCF 1** (S221001345), luego
se detallará el **ajuste** a todos los ítems del **CCFE 2** (FF54E9DB-79C3-42CE-B432-EC552C97EFB9) y el ajuste para el
ítem 5 del **CCFE 3** (FF54E9DB-79C3-42CE-B432-EC552C97EF33).

En los ítems 1 y 2 del cuerpo de la Nota de Crédito se deberá detallar los ítems a ajustar del CCF1, en los ítems del 3
al 7 los ítems a ajustar del CCFE 2 y el ítem 8 el ajuste del CCFE 3 tal como se refleja en la siguiente tabla:

**Sección Cuerpo Nota de Crédito Electrónica**

De esta manera se está detallando los ítems a los cuales se aplica el ajuste por cada documento, es importante
aclarar que los documentos que aplican a esta sección (documentos relacionados), como ya se había mencionado,
en el cuerpo de los documentos podrá describir hasta un máximo de 2000 ítem, es decir si por ejemplo se relacionara
un CCF a una NCE para realizar un ajuste y dicho CCF tuviera 2000 ítems y todos requieren ajustarse podrá relacionar
en la sección relacionados solo este CCF en esta Nota de Crédito Electrónica. Si se diera el caso que tengo 50 CCF
con 1000 ítem cada uno, pero solo es necesario realizar ajuste en 2 ítem por cada CCF, en la NCE perfectamente
detallaría en la sección de relacionados los 50 CCF y en el cuerpo de la nota de crédito podría detallar los dos ítems
de cada documento ingresando un total de 100 ítems.

**Notas importantes:**

1. Los Comprobantes de Crédito Fiscal, Facturas, Notas de Remisión, Comprobantes de Retención y
    Comprobantes de Liquidación electrónicos que se relacionen con otro DTE deberán encontrarse activos y
    contar con sello de recepción.
2. Cuando en Comprobantes de Crédito Fiscal Electrónicos o Factura electrónica se referencien Documentos
    Contables de Liquidación sin sello de recepción, será obligatorio que el emisor transmita los DCL dentro de
    los plazos correspondientes.

```
Cuerpo del documento^
N° De
ítem
```
```
Tipo
de
Ítem
```
```
Número de documento
relacionado Cantidad^ Código^
```
```
Tributo
sujeto a
cálculo de
IVA.
```
```
Unidad de
Medida Descripción^
Precio
Unitario
```
```
Descuento,
Bonificación
Rebajas por
ítem
```
```
Ventas
No
Sujetas
```
```
Ventas
Exentas
Ventas
Gravadas
```
```
Código
del
Tributo
```
```
1 1 S221001345 1 Null Null 59
Ajuste por
devolución
camisa/negra
$ 10.00 $ 0.00 $ 0.00 $ 0.00 $ 10 .00 20
```
2 1 S221001345 2 Null Null (^59) devolución/ JeansAjuste por $ 20 .00 $ 0.00 $ 0.00 $ 0.00 $ 40 .00 20
3 1 FF54E9DBB432-EC552C97EFB9-79C3-42CE - 5 Null Null 59
Ajuste por
descuento no
aplicado
Camisas/negro
$ 1 .00 $ 0.00 $ 0.00 $ 0.00 $ 5.00 20
4 1 FF54E9DBB432-EC552C97EFB9-79C3-42CE - 15 Null Null 59
Ajuste por
descuento no
aplicado/ Centros
$ 0.50 $ 0.00 $ 0.00 $ 0.00 $ 7.50 20
5 1 FF54E9DBB432-EC552C97EFB9-79C3-42CE - 25 Null Null 59
Ajuste por
descuento no
aplicado/ Jeans
$ 1.00 $ 0.00 $ 0.00 $ 0.00 $ 25.00 20
6 1 FF54E9DBB432-EC552C97EFB9-79C3-42CE - 5 Null Null
59 Ajuste por
descuento no
aplicado/ Cinturón
$ 2 .00 $ 0.00 $ 0.00 $ 0.00 $ 10.00 20
7 1 FF54E9DBB432-EC552C97EFB9-79C3-42CE - 10 Null Null
59 Ajuste por
descuento no
aplicado/ cartera
$ 2.50.00 $ 0.00 $ 0.00 $ 0.00 $ 25.00 20
8 1 FF54E9DBB432-EC552C97EF33-79C3-42CE - 10 Null Null 59 Ajuste en precio/ cartera $ 3.00 $ 0.00 $ 0.00 $ 0.00 $ 30.00 20


## XV. Uso de Sección Otros Documentos Asociados.

Esta sección aplica para Factura Electrónica, Comprobante de Crédito Fiscal Electrónico, Factura de exportación
Electrónica y Comprobante de Donación Electrónico; en esta se permite anexar información relevante de la
operación que puede ser requerida de acuerdo a ciertas particularidades del negocio que no son de carácter
tributario.

Para el ingreso de información es esta sección se debe considerar el catálogo 021 “Otros Documentos Asociados”
cuya codificación deberá ingresar en campo “Documento asociado” indicado si la información a describir
corresponde a el emisor, al receptor, médico y transportista.

En el caso particular de la Factura Electrónica y Comprobante de Crédito Fiscal Electrónico además de tener la opción
de ingresar información general del emisor y/o receptor (tales como: contratos, resoluciones, autorizaciones entre
otros) podrá también indicar siempre que la operación lo requiera, las generales del médico (identificación, nombre,
procedimiento, etc.) cuando se trate de aquellas actividades económicas referentes a la prestación de servicios
médicos.

Si campo "documento asociado" está completo con las opciones 1 o 2 en esta línea deberá contener solamente los
siguientes campos:

```
Documento
asociado
```
```
Identificación del doc.
Asociado
```
```
Descripción de documento
asociado
```
Si campo "documento asociado" está completo con las opciones 3 esta línea deberá contener solamente los
siguientes campos:

```
Nombre de médico que
presta el Servicio
```
```
NIT de médico que
presta el Servicio
```
```
Documento de identificación de médico
no domiciliados
```
```
Código del Servicio
realizado
```
Debiendo considerar la codificación del catálogo 010 Código tipo de Servicio (Médico).

Si campo "documento asociado" está completo con las opciones 4 esta línea deberá contener los siguientes campos:

```
Modo de transporte
```
```
Número de
identificación del
transporte
```
```
N° documento de
identificación del
conductor
```
```
Nombre y apellidos
del conductor
```
Debiendo considerar la codificación del catálogo 030 - Transporte

El detalle de la información del transportista aplica de manera opcional y únicamente tiene aplicación para Factura
de Exportación Electrónica.


En el caso del Comprobante de Donación Electrónico solo permitirá los códigos 1- Emisor y 2- Receptor, siendo
requerido el ingreso de al menos un registro que corresponda al Donatario (Emisor), para detallar la resolución de
calificación como sujeto excluido.

**Ejemplo de aplicación para Factura Electrónica y Comprobante de Crédito Fiscal Electrónica.**

Se emitirá una factura a razón de una cirugía que se cubrirá con una póliza de seguro y a raíz de esta cirugía se
recetará un medicamento que requiere autorización por la DNM. Para su respaldo, el emisor podrá detallar la
información en esta sección de la siguiente manera:

```
Otros documentos asociados para F y CCF
```
```
Document
o asociado
```
```
Identificación del
doc. asociado
```
```
Descripción de
documento
asociado:
```
```
Nombre de
médico que
presta el Servicio
```
```
NIT de médico que
presta el Servicio
```
```
Documento de
identificación de
médico no
domiciliados
```
```
Código del
Tipo de
Servicio
Realizado
```
```
2
```
```
Seguro médico
/Aseguradora x Pxxxxx
1 Permiso DNM UIEDM-P- 01 - PXX-X
3 Chamba Cabal 22222222222221 null 1
```
En la línea 1 se detalla código 2 ya que el documento asociado que pertenece al receptor es una póliza de seguro
médico hospitalario (seguro médico/ aseguradora x) y se referencia el número (Pxxxxx).

En la segunda línea se referencia código 1 enunciando que el documento corresponde al emisor, el cual consiste en
un permiso otorgado por la DNM (UIEDM-P- 01 - PXX-X) para la venta de un medicamento especifico con el cual tratara
a su paciente.

En la línea 3 se hace referencia a las generales del médico que atendió la cirugía. (Chamba Cabal con NIT:
22222222222221 tipo de servicio realizado Cirugía).

Pudiendo ingresar un máximo de 10 líneas para relacionar información relacionada, que, si bien esta no es de
carácter tributario, de acuerdo las particularidades del negocio podrán ser necesario el ingreso de la misma para
respaldar la operación.

Para el caso particular de la Factura de Exportación Electrónica, podrá indicar de igual manera además de la
información del emisor y el receptor la información del transportista, mediante 4 campos específicos.

**Ejemplo de aplicación para Factura de Exportación Electrónica:**

Se está realizando exportación de pollitas rojas bebes, para lo cual el exportador ha obtenido un permiso
zoosanitario.


```
Otros documentos asociados para FEXE.
```
```
Documento
asociado
```
```
Identificación del doc.
asociado
```
```
Descripción
de documento
asociado:
```
```
Modo de
transporte
```
```
Número de
identificación del
transporte
```
```
N° documento
de identificación
del conductor
```
```
Nombre y
apellidos del
conductor
1 Permiso Zoosanitario XXXXXXXX
4 1 HNXXXXX CRXXXX-X Chamba Cabal
```
De esta manera estamos detallando un permiso zoosanitario (XXXXXXXX) que corresponde al emisor de la factura
de exportación y la información del transportista (Chamba Cabal, Número de identificación del transporte HNXXXXX,
N° documento de identificación del conductor CRXXXX-X, Modo de transporte 1-Terrestre).

En esta sección para factura de exportación Electrónica podrá ingresar un máximo de 20 líneas que de acuerdo las
particularidades de negocios.

## XVI. Venta cuenta de terceros........................................................................................................................

Las estructuras establecidas para FE, CCFE, NRE, NCE, NDE y FEXE contienen la sección “Venta a cuenta de terceros”
donde se encuentran los campos: “NIT por cuenta de terceros” y “Nombre, denominación o razón social del Tercero”
para detallar las ventas que el emisor realice por cuenta de sus mandantes.

Cuando no se haga uso de esta sección; es decir, cuando la venta no sea una operación por cuenta de un tercero,
deberá enviar esta sección con la palabra null.

Cuando la venta que realice el emisor sea por cuenta de un tercero debe detallar el Número de Identificación
Tributaria (NIT) y el Nombre del Mandante en los campos antes citados.

**Para la emisión de los DTE a cuenta de terceros debe considerar lo siguiente:**

1. La sección venta cuenta a terceros permitirá el detalle de un solo mandante, es decir un Número de
    Identificación Tributaria y un nombre de tercero.
2. Las ventas a cuenta de tercero se deben emitir en un DTE de forma independiente de las ventas propias; es
    decir no pueden emitirse DTE mezclando ventas propias y con ventas a cuenta de terceros.
3. En los casos que tuviera varios mandantes debe emitir los DTE uno a uno, no puede detallarse ventas de
    varios mandantes en un solo DTE.

**Detalle de los DTE emitido a cuenta de terceros en el Comprobante de Liquidación Electrónico (CLE)**

1. El CLE solo aceptará el ingreso de documentos de ventas emitidos con información en la sección “Venta a
    cuenta de terceros” (El tercero que se detalle en FE, CCFE, NRE, NCE, NDE o FEXE será el receptor en el CLE).
2. No podrá informar los DTE en un CLE si no se ha detallado información en la sección “Venta a cuenta de
    terceros” del documento de venta.
3. Los documentos tributarios detallados en el CLE se deben realizar con la información del resumen,
    ingresando el valor resumen del DTE por cada ítem; es decir, no se debe trasladar en detalle cada uno de
    los ítems contenidos en el DTE.


4. El documento tributario que se referencia en el CLE debe tener correspondencia al periodo en que se está
    emitiendo el CLE.
5. El documento tributario solo puede referenciarse una vez y en un solo CLE, a excepción de los documentos
    invalidados que podrán referenciarse por primera vez activos y por segunda vez invalidados pudiendo
    reflejarse dicha invalidación en el mismo CLE o en uno posterior a haber informado DTE activo en un CLE
    previo.
6. Para la elaboración del CLE se deben considerar las especificaciones del llenado de campos establecidos en
    las la estructura y validaciones contenidas en la normativa de cumplimiento de los DTE.

## XVII. Aplicación de los campos “Descuento, Bonificación, Rebajas

## por ítem” y “Monto Global de Descuento, Bonificación,

## Rebajas y otros” en los DTE.

Se pueden definir los Descuento, Bonificación, Rebajas y otros como una disminución en el precio de un bien o
un servicio. Estos descuentos pueden darse en forma de porcentaje, cantidad fija de unidades monetarias o
acumulativos, entre otras muchas opciones.

Para facturación electrónica se consideran los campos de descuento en los tipos de documentos: Factura Electrónica,
Comprobante de Crédito Fiscal Electrónico, Nota de Remisión Electrónica, Nota de Crédito Electrónica, Nota de
Débito Electrónica, Factura Sujeto Excluido Electrónica y Factura de exportación Electrónica. A fin de garantizar la
aplicación de toda la casuística que pudiera darse en las diferentes operaciones del día a día; Se consideran dos
formas de ingresar estos descuentos en los DTE los cuales se describen a continuación:

**1. Descuento, Bonificación, Rebajas por ítem:** considera las disminuciones de precios al producto, este deberá
    ingresarse dentro de la sección cuerpo del documento, de forma consolidada restándose al resultado de
    multiplicar el precio por la cantidad en el ítem o línea.
    En el supuesto que se vendan 10 cuadernos a un precio unitario de $1.00 y se aplica un descuento de $0.10
    ctvs. a cada lápiz, debo detallar en campo “cantidad” 10, en campo “precio unitario” $1.00 y en campo
    “Descuento, Bonificación, Rebajas por ítem o línea de operación” $1.00 (se aplicó un descuento de $0.10
    ctvs. por cada cuaderno).

**Ejemplo de aplicación 1**

N° de ítem (^) Cantidad
Precio
Unitario
Descuento,
Bonificación,
Rebajas por ítem
Ventas No
Sujetas
Ventas
Exentas
Ventas
Gravadas
1 10 $1.00 $1.00 $0.00 $0.00 $9.00
2 10 $20.00 $0.00 $0.00 $0.00 $200.00
3 4 $20.00 $5.00 $0.00 $75.00 $0.00
Cuando no se requiera aplicar descuento, bonificación, rebajas por ítem deberá enviar este campo con valor
$0.00.

**2. Monto global de Descuento, Bonificación, Rebajas y otros”** estas disminuciones se aplican al valor total de
    la venta por cada tipo de venta, deberán ingresarse en la sección resumen dependiendo del tipo de venta


```
al que se aplique, en los campos “Monto global de Descuento, Bonificación, Rebajas y otros a ventas
exentas”, “Monto global de Descuento, Bonificación, Rebajas y otros no sujetas” y “Monto global de
Descuento, Bonificación, Rebajas y otros a ventas gravadas” según corresponda.
```
```
En estos campos se aplicarán aquellas disminuciones globales a las ventas que se necesiten aplicar, por
ejemplo, un monto fijo, descuentos acumulados, descuentos por pronto pago, descuentos por fidelidad,
descuento general por el uso de una tarjeta específica, rebajas especiales por un monto de consumo o
promociones especiales, subsidios por consumo, entre otros. Los cuales se aplican de manera general sobre
el valor total de la venta (es decir no por producto por línea de operación).
```
```
Cuando no se requiera aplicar descuentos de este tipo se deberá enviar este campo con valor $0.00.
```
**3. Porcentaje del monto global de Descuento, Bonificación, Rebajas y otros:** este campo se encuentra en la
    sección resumen de las estructuras de FE, CCFE, NRE, NCE, NDE y FEXE donde podrá si lo desea indicar el
    porcentaje global de descuento a aplicar sin utilizar el símbolo de porcentaje.

```
Por ejemplo, si se aplica un 10% de descuento en este campo deberá ingresar el número 10.
```
**4. Total, del monto de Descuento, Bonificación, Rebajas:** este campo se encuentra en la sección resumen de
    las estructuras de FE, CCFE, NRE, NCE, NDE, FSEE y FEXE es importante aclarar que este campo solo será **de**
    **uso informativo,** a efecto de mostrar el total de disminuciones aplicadas. Sumará todas las disminuciones
    aplicadas por ítem contenidos en campo “Descuento, Bonificación, Rebajas por ítem” contenidas en el
    cuerpo del documento más los descuentos globales por tipo de venta contenidas en la sección resumen.

**Ejemplo de aplicación 2**

Se genera un DTE con los siguientes ítems con sus respectivos detalles:

N° De ítem (^) Cantidad
Precio
Unitario
Descuento,
Bonificación,
Rebajas por ítem
Ventas No
Sujetas
Ventas
Exentas
Ventas
Gravadas
1 10 $25.00 $25.00 $0.00 $0.00 $225.00
2 5 $80.00 $15.00 $0.00 $0.00 $385.00
3 4 $10.00 $5.00 $0.00 $35.00 $0.00
Un comercio tiene una promoción de temporada que por consumo mayor a $500.00 el cliente recibe un 10% de
descuento global sobre el monto. Lo cual se aplicaría de la siguiente manera en la sección resumen:
**Resumen** (^)
Total, de Operaciones no sujetas (^) $0.00
Total, de Operaciones exentas (^) $35.00
Total, de Operaciones Gravadas (^) $610.00
Suma de operaciones sin impuestos (^) $645.00
Monto de Descuento, Bonificación, Rebajas y otros no sujetas (^) $0.00
Monto de Descuento, Bonificación, Rebajas y otros a ventas exentas (^) $3.50


**Como se puede visualizar “Total, del monto de Descuento, Bonificación, Rebajas”** es la suma de Descuento,
Bonificación, Rebajas por ítem o línea de operación **($25.00+$15.00+$5.00)** + los Monto global de Descuento,
Bonificación, Rebajas y otros por tipo de venta **($3.50+$61.00) =$109.50.**

**Nota:** Para la Factura de Exportación Electrónica en el contexto de esta explicación de la aplicación de los descuentos
el campo “Monto de Descuento, Bonificación, Rebajas y otros a ventas gravadas” tiene equivalencia a campo “Monto
de Descuento, Bonificación, Rebajas y otros a ventas afectas” Y para el caso de la FSEE tiene equivalencia a Monto
global de Descuento, Bonificación, Rebajas y otros al total de operaciones.

## XVIII.Invalidación de documentos

El evento de invalidación tendrá aplicación cuando ocurran errores formales así mismo en el caso de la FE, FEXE Y
FSEE, además de invalidarse por errores formales también tiene aplicación la invalidación por ajustes que
disminuyan, anulen o rescindan operaciones.

En la estructura de datos proporcionada para el envío de dicho evento, en la sección “Motivo de la Invalidación” se
encuentra el campo “Tipo de Invalidación” donde se ingresará por medio de un código el tipo de error por el cual se
requiere invalidar el DTE, dicha codificación únicamente podrá ser la establecida en el catálogo 024-Tipo de
Invalidación.

Cuando en campo motivo de invalidación se encuentre lleno con la opción 1 (Error en la Información del Documento
Tributario Electrónico a invalidar) o 3 (Otro), deberá primero generar, transmitir y obtener el sello de recepción del
documento que corrige la operación, ya que el evento de invalidación requiere dejar constancia del código de
generación del documento correcto. Se exceptúa de esta condición la Nota de Crédito y Comprobante de
Liquidación.

Cuando en campo motivo de invalidación se encuentre lleno con la opción 2 (Rescindir de la operación realizada) o
el documento a invalidar sea Nota de Crédito Electrónico o Comprobante de Liquidación Electrónico, en campo
“Código de generación del documento que reemplaza al documento invalidado” deberá ingresar la palabra null.

**Invalidación de los documentos relacionados con otro DTE.**

Cuando se requiera invalidar un DTE relacionado con otro DTE además de considera los procesos establecidos en el
evento de invalidación contenido en el “Manual de aplicación de las estructuras de los DTE, Eventos y Pruebas
Mínimas para el Sistema de Transmisión” deberá tomar en cuenta los procesos que se detallan en la siguiente tabla:

Monto de Descuento, Bonificación, Rebajas y otros a ventas gravadas (^) $61.00
Porcentaje del monto global de Descuento, Bonificación, Rebajas y otros (^10)
**Total, del monto de Descuento, Bonificación, Rebajas** (^) $109.50


**DTE a
invalidar
Proceso
Doc.
Relacionado**

### FE

```
Si el tipo de invalidación es 1 o 3 deberá generar y transmitir la nueva factura con la
que corregirá la operación, para posteriormente invalidar la factura incorrecta,
ingresando en el evento de invalidación tanto el código de generación de la factura
a invalidar (Factura incorrecta) como el código de generación de la factura que la
sustituye (factura correcta).
```
```
Si el tipo de invalidación es 2 deberá generar y transmitir el evento de invalidación
referenciando únicamente el código de generación de la FE incorrecta, ingresando
en campo “código de generación del documento que reemplaza al invalidado” la
palabra null.
```
```
Si hubiera documento relacionado a la factura no hay necesidad de invalidar los
documentos relacionados para invalidarla (Nota de Remisión, Documento Contable
de Liquidación).
```
### NR/DCL

### CCFE

```
Si el tipo de invalidación es 1 o 3 deberá generar, transmitir y obtener el sello de
recepción del nuevo CCFE con el que corregirá la operación, para posteriormente
realizar proceso de invalidación del CCFE incorrecto, ingresando en la estructura del
evento de invalidación tanto el código de generación del documento a invalidar
(CCFE incorrecto) como el código de generación del CCFE que sustituye la operación
(CCFE correcto).
```
```
Si el Tipo de invalidación es 2 deberá generar y transmitir el evento de invalidación
referenciando únicamente el código de generación del CCFE incorrecto, ingresando
en campo “código de generación del documento que reemplaza al invalidado” la
palabra null.
No hay necesidad de invalidar los documentos que fueron relacionados al CCFE para
invalidarlo (Nota de Remisión, Documento Contable de Liquidación o Comprobante
de liquidación).
```
```
Notas:
```
1. No podrá invalidarse CCFE que esté relacionado a una Nota de Crédito o Nota de
Débito activa. (primero debe invalidar la Nota de Crédito o Nota de Débito para
posteriormente invalidar dicho CCFE).
2. Si se requiere invalidar un CCFE referenciado a un CRE podrá realizarse
invalidación sin necesidad de invalidar previamente el CRE, ya que los ajustes al CRE
procederán por medio de Nota de Crédito.

### NR /DCL /CL


**DTE a
invalidar
Proceso
Doc.
Relacionado**

### NCE

```
Si el tipo de invalidación es 1 o 3 deberá realizar el evento de invalidación
referenciando únicamente el código de generación de la NCE incorrecta e
ingresando en campo “código de generación del documento que reemplaza al
invalidado” la palabra null. Una vez invalidada la NCE incorrecta deberá generar,
transmitir y obtener el sello de recepción de una nueva NCE con la que corregirá la
operación.
```
```
Si el Tipo de invalidación es 2 deberá generar y transmitir el evento de invalidación
referenciando únicamente el código de generación de la NCE incorrecta, ingresando
en campo “código de generación del documento que reemplaza al invalidado” la
palabra null.
```
```
Para invalidar NCE no es necesario invalidar los documentos relacionados (CCFE,
CR E).
```
### CCF/CR

### NDE

```
Si el tipo de invalidación es 1 o 3 deberá generar, transmitir y obtener el sello de
recepción de una nueva NDE con la que corregirá la operación, posteriormente
realizar la invalidación de la NDE incorrecta, ingresando en el evento de invalidación
tanto el código de generación de la NDE a invalidar (incorrecta) como el código de
generación de la NDE que la sustituye (correcta)
```
```
Si el Tipo de invalidación es 2 deberá generar y transmitir el evento de invalidación
referenciando únicamente el código de generación de la NDE incorrecta, ingresando
en campo “código de generación del documento que reemplaza al invalidado” la
palabra null.
```
```
Para invalidar NDE no es necesario invalidar los documentos relacionados (CCFE,
CRE).
```
### CCF/ CR

### NRE

```
Si el tipo de invalidación es 1 o 3 deberá generar, transmitir y obtener el sello de
recepción de la nueva NRE con la que corregirá la operación, posteriormente
realizar proceso de invalidación de la NRE incorrecta, ingresando en la estructura
del evento de invalidación tanto el código de generación del documento a invalidar
como el código de generación de la NRE que contiene la información correcta.
```
```
Si el Tipo de invalidación es 2 deberá generar y transmitir el evento de invalidación
referenciando únicamente el código de generación de la NRE incorrecta, ingresando
en campo “código de generación del documento que reemplaza al invalidado” la
palabra null.
```
```
No hay necesidad de invalidar los documentos relacionados (FE o CCFE).
```
### F/CCF

### CRE

```
Si el tipo de invalidación es 1 o 3, deberá generar, transmitir y obtener el sello de
recepción de un nuevo CRE con el que corregirá la operación, posteriormente
generar y transmitir el evento de invalidación del CRE incorrecto, ingresando en la
estructura de dicho evento, tanto el código de generación del documento a
```
```
N/A sección
de
relacionados
```

**DTE a
invalidar
Proceso
Doc.
Relacionado**
invalidar (CRE incorrecto) como el código de generación del documento que
sustituye al anterior (CRE correcto).

```
Si el tipo de invalidación es la opción 2, deberá generar y transmitir el evento de
invalidación referenciando únicamente el código de generación del CRE incorrecto,
ingresando en campo “código de generación del documento que reemplaza al
invalidado” la palabra null.
```
```
No hay necesidad de invalidar los documentos informados en el CRE para su
invalidación.
```
### CLE

```
Si el tipo de invalidación es 1 o 3 deberá realizar el evento de invalidación
referenciando únicamente el código de generación del CLE incorrecto e ingresando
en campo “código de generación del documento que reemplaza al invalidado” la
palabra null. Una vez invalidado el CLE incorrecto deberá generar, transmitir y
obtener el sello de recepción de un nuevo CLE con el que corregirá la operación.
```
```
Si el Tipo de invalidación es 2 deberá generar y transmitir el evento de invalidación
referenciando únicamente el código de generación del CLE incorrecto, ingresando
en campo “código de generación del documento que reemplaza al invalidado” la
palabra null.
```
```
Para invalidar CLE no es necesario invalidar los documentos informados (FE, CCFE,
NCE, NDE, FEXE). En el momento que se realice la invalidación del CLE incorrecto,
los documentos informados estarán disponibles para que sean ingresados en un
nuevo CLE.
```
```
N/A sección
de
relacionados
```
### DCLE

```
Si el tipo de invalidación es 1 o 3 deberá generar, transmitir y obtener el sello de
recepción para un nuevo DCLE con el que corregirá la operación, posteriormente
realizará la invalidación del DCLE incorrecto, ingresando en la estructura de dicho
evento, tanto el código de generación del documento a invalidar (DCLE incorrecto)
como el código de generación del documento que sustituye al anterior (DCLE
correcto).
```
```
Si el Tipo de invalidación es 2 deberá generar y transmitir el evento de invalidación
referenciando únicamente el código de generación del DCLE incorrecto, ingresando
en campo “código de generación del documento que reemplaza al invalidado” la
palabra null.
```
```
N/A sección
de
relacionados
```

**DTE a
invalidar
Proceso
Doc.
Relacionado**

### FEXE

```
Si el tipo de invalidación es 1 o 3 deberá generar, transmitir y obtener el sello de
recepción de la FEXE con la que corregirá la operación y posteriormente invalidará
la FEXE incorrecta, ingresando en el evento de invalidación tanto el código de
generación de la FEXE a invalidar (incorrecta) como el código de generación de la
FEXE que la sustituye (correcta).
```
```
Si el Tipo de invalidación es 2 deberá generar y transmitir el evento de invalidación
referenciando únicamente el código de generación de la FEXE incorrecta,
ingresando en campo “código de generación del documento que reemplaza al
invalidado” la palabra null.
```
```
N/A sección
de
relacionados
```
### FSEE

```
Si el tipo de invalidación es 1 o 3 deberá generar, transmitir y obtener el sello de
recepción de la FSEE con la que corregirá la operación y posteriormente invalidará
la FSEE incorrecta, ingresando en el evento de invalidación tanto el código de
generación de la FSEE a invalidar (incorrecta) como el código de generación de la
FSEE que la sustituye (correcta).
```
```
Si el Tipo de invalidación es 2 deberá generar y transmitir el evento de invalidación
referenciando únicamente el código de generación de la FSEE incorrecta,
ingresando en campo “código de generación del documento que reemplaza al
invalidado” la palabra null.
```
```
N/A sección
de
relacionados
```
### CDE

```
Si el tipo de invalidación es 1 o 3 deberá generar, transmitir y obtener el sello de
recepción del CDE con el que corregirá la operación y posteriormente invalidará el
CDE incorrecto, ingresando en el evento de invalidación tanto el código de
generación de la CDE a invalidar (incorrecto) como el código de generación del CDE
que lo sustituye (correcto).
```
```
Si el Tipo de invalidación es 2 deberá generar y transmitir el evento de invalidación
referenciando únicamente el código de generación del CDE incorrecto, ingresando
en campo “código de generación del documento que reemplaza al invalidado” la
palabra null.
```
```
N/A sección
de
relacionados
```

## XIX. Ingreso de información en campos relativos al pago

Para el llenado de los DTE: Comprobante de Crédito Fiscal Electrónico, Factura Electrónica, Factura de Sujeto
Excluido Electrónica y Factura de Exportación Electrónica, es necesario agregar la forma cómo se efectúa el pago de
la operación

La Condición de la operación consiste en los términos en que se acuerda realizar el pago de una operación entre el
emisor y el receptor del DTE, mediante el campo denominado “Condición de la Operación”, utilizando el catálogo
016 , con las siguientes opciones:

```
Código Valores
1 Contado
2 A crédito
3 Otro
```
Las condiciones de la operación dictarán la manera de ingreso de las diferentes formas de pago.

Para detallar las formas de pago se ha establecido en las estructuras de los DTE antes mencionados los siguientes
campos:

1. **Código de forma de pago:** Donde ingresará la codificación respectiva contenida en el catálogo 017.
2. **Monto por forma de pago:** Donde ingresará los valores monetarios que correspondan a cada una de las
    formas de pago que se detallen.
3. **Referencia de modalidad de pago:** Cuando aplique podrá detallar el número de referencia de cada
    modalidad de pago detallada, a excepción de la modalidad de pago "billetes y monedas" (Ejemplo: Número
    de Cheque, transferencia bancaria, etc.).

Si la forma de pago es "billetes y monedas " deberá enviar campo con null.

4. **Plazo:** Cuando aplique deberá contener el tiempo del plazo otorgado expresado de acuerdo al código según
    Catálogo 018 Plazo. Ejemplo si los pagos se han determinados mensuales se ingresará el código “2” Meses.
5. **Periodo de Plazo:** Cuando aplique deberá de ingresar el número de días, meses o años en que se otorga el
    plazo. Ejemplo: si el plazo es 6 meses, en este campo se deberá ingresar únicamente el número 6.

Como se hizo mención anteriormente, las formas de pago están relacionadas directamente con la condición de la
operación, a continuación, se detalla el llenado de campos según corresponde:

**1. Condición de la Operación 1-Contado**

En este caso es necesario que se ingrese desde “1” hasta “n” formas de pago, debiendo detallar la información
solicitada de la siguiente manera:


```
a) Ejemplo de Venta de Contado con una forma de pago: Cliente paga en billetes y monedas por un valor de
$50.00
```
```
Condición de la operación: 1,
```
```
Código de forma de pago 01,
Monto por forma de pago: $50.00,
Referencia de modalidad de pago: null,
Plazo: null,
Periodo plazo: null
```
```
b) Ejemplo de Venta de contado con varias formas de pago: Venta por un valor de $150.00, cliente decide
cancelar de la siguiente manera: $100.00 en billetes y monedas y $50.00 con tarjeta de crédito número
0000000054782, el DTE se completará de la siguiente forma:
```
```
Condición de la operación: 1,
{Código de forma de pago 01,
Monto por forma de pago: $100.00,
Referencia de modalidad de pago: null,
Plazo: null,
Periodo plazo: null},
```
```
{Código de forma de pago 02,
Monto por forma de pago: $50.00,
Referencia de modalidad de pago: 0000000054782,
Plazo: null,
Periodo plazo: null}
```
De esta manera podrá ingresar “n” formas de pago según necesite, detallando los 5 campos por cada una de las
formas de pago que adicione en el DTE y separando cada arreglo de datos por comas.

**2. Condición de la Operación 2-Crédito.**

Cuando la condición de la operación sea Crédito se deberá detallar la forma de pago, el plazo y periodo. Para detallar
el plazo se deberá considera la codificación establecida en el catálogo 018-Plazo.

Ejemplo: Se realiza una venta por $500.00 con pago a 6 meses plazo, se deberá detallar de la siguiente manera:

```
Condición de la operación: 2,
```
```
Código Valor
01 Días
02 Meses
03 Años
```

```
Código de forma de pago 01,
Monto por forma de pago: $500.00,
Referencia de modalidad de pago: null,
Plazo: 02,
Periodo plazo: 6
```
**3. Condición de la Operación 3- Otro**

Deberá utilizar esta opción cuando requiera ingresar condiciones de pago mixtas, es decir una parte del valor a pagar
de contado y otra al crédito.

Por ejemplo una venta por un valor de $474.60 por la cual se emitirá una Factura Electrónica y el cliente decide pagar
de la siguiente manera: $174.60 con tarjeta de débito referencia 123456 y el resto al crédito ($300.00) en un plazo
de dos meses.

Se deberá completar de la siguiente manera:

Condición de la operación: 3,

```
{Código de forma de pago: 02,
Monto por forma de pago: $174.60),
Referencia de modalidad de pago: 123456
Plazo: null,
Periodo plazo: null},
```
```
{Código de forma de pago 02,
Monto por forma de pago: $300.00),
Referencia de modalidad de pago: null
Plazo: 02,
Periodo plazo: 2}
```
## XX. Ingreso de información para los ítems del Comprobante de Donación

Existen tres tipos de donación que una entidad puede recibir, a cada tipo de donación se le ha asignado un código
que deberá ingresar en el campo “Tipo de donación” contenido en la sección cuerpo, dicha codificación se encuentra
en el catálogo 026 de la siguiente manera: 1- Efectivo, 2- Bien, 3- Servicio

**1. Cuando el tipo de donación es Efectivo se condicionará la información en los campos siguientes:**

```
a) Cantidad: “1”
b) Descripción: Se deberá indicar el concepto de la donación.
c) Unidad de Medida: Se debe consignar “99” (Otra)
d) Depreciación: se deberá colocar $0.00
```

```
e) Valor Unitario: se deberá ingresar el valor del efectivo donado
f) Valor Donado: Deberá consignarse el resultado del campo “Valor Unitario” multiplicado por el campo
“Cantidad” menos la cantidad consignada en el campo “Depreciación”.
```
**2. Cuando el tipo de donación consiste en un Bien se ingresará de la siguiente manera:**

```
a) Cantidad se debe consignar la cantidad de bienes del mismo tipo.
b) Descripción se deberá indicar el concepto de la donación. Ejemplo: “Ambulancia Marca Mercedes Benz,
Modelo T1, Año 2022”
c) Unidad de Medida se debe consignar la que corresponda conforme al CAT-014 unidad de medida.
d) Depreciación se deberá colocar el valor depreciado del bien según aplique (En caso de Bienes usados).
e) Valor Unitario se deberá ingresar el Valor del bien donado.
f) Valor Donado deberá consignarse el resultado del campo “Valor Unitario” multiplicado por el campo
“Cantidad” menos la cantidad consignada en el campo “Depreciación”.
```
**3. Cuando el tipo de donación consiste en un Servicio.**

```
a) Cantidad: se debe consignar la cantidad de servicios del mismo tipo.
b) Descripción: Se deberá indicar el concepto de la donación.
c) Unidad de Medida: Se debe consignar “99” (Otra)
d) Depreciación: se deberá colocar $0.00
e) Valor Unitario: se deberá ingresar el valor del servicio donado
f) Valor Donado: Deberá consignarse el resultado del campo “Valor Unitario” multiplicado por el campo
“Cantidad”
```
Es importante mencionar que en un mismo Comprobante de Donación Electrónico se pueden ingresar más de una
donación y diferentes tipos de donación, ya que son ingresadas cada una por ítem.

## XXI. Redondeos y Holguras

**Redondeo:** Consiste en una regla fija para “elevar” en cada operación la última posición decimal dentro del rango,
cuando la primera posición decimal fuera de rango sea mayor a un número convencional, representado por un
número decimal igual o mayor a 5.

Para efectos de los valores que se reflejen en la sección cuerpo de los DTES se ha establecido una longitud de 11.8,
en los casos que los sistemas de facturación internos utilizados por los contribuyentes estén configurados con una
longitud de decimales mayor, y la novena posición decimal de esta longitud sea igual o mayor a 5, la octava
posición decimal se deberá redondear 1 hacia arriba. Cuando la novena posición decimal sea menor a
cinco, se mantendrá el número que contenga la octava posición.

**Regla de Redondeos**

**Se presenta un ejemplo de un mismo ítem utilizando en una fila 8 decimales y en otros 15 decimales:**

**Ejemplos 1:**


```
Campos Sistema del Contribuyente Estructura DTE
```
```
Cantidad 1.87654321 987654 1.87654322
```
```
Precio 3.55555555 400000 3.55555555
```
```
Descuento 1 1
```
```
Venta 5.67215366 775307 5.67215367
```
Como se visualiza en el ejemplo la novena posición en el campo “Cantidad” en el Sistema del Contribuyente se
redondea a 2 en la octava posición decimal en la estructura del DTE ya que el número que ocupa la novena posición
decimal es mayor que 5. Misma situación se observa en el campo “Venta”.

Además, en campo precio donde la octava posición decimal se mantiene en 5 ya que la novena posición decimal es
menor a 5

Si su sistema interno utiliza una cantidad mayor de decimales para efecto de la transmisión del archivo DTE deberá
cumplir con las reglas de redondeo definidas por la Administración Tributaria, ya que en la recepción del documento
en los servidores del Ministerio de Hacienda se corren procesos de validación aritméticos, los cuales pueden generar
rechazo.

**Redondeos en Sección Resumen**

Se permitirá hasta dos posiciones decimales (fraccionaria) en los campos numéricos de la Sección Resumen de los
DTE. Si el contribuyente utiliza más de dos decimales en su sistema de facturación, la segunda posición decimal de
estos campos se deberá redondear 1 hacia arriba cuando la tercera posición decimal sea 5 o mayor. Para los casos
en que la tercera posición decimal sea menor a 5, se mantendrá el valor de la posición 2.

```
Ejemplos:
```
```
Campo Total a Pagar
Campo Total a Pagar en Sistema
para ser Transmitido
5.664 5.66
5.665 5.67
5.666 5.67
```
**Regla de Holgura:**

```
Holgura: Es la diferencia permitida en los campos numéricos de los DTE en referencia a los cálculos internos para
efecto de verificaciones del cumplimiento de los datos recepcionados.
```
Para efecto de los DTE en los valores ingresados en la sección resumen se permitirá una tolerancia de una centésima.

**Ejemplo:** Se tiene la siguiente información en la sección cuerpo aplicando las reglas de redondeo antes mencionadas
y las holguras.


```
Holgura en Sección Cuerpo
```
```
Ítem Cantidad Precio Venta Gravada
```
```
Venta Gravada
(con redondeo)
```
```
V. G. Holgura
(-0.01)
```
```
V.G. Holgura
(+0.01)
```
(^1) 1.1219999999 2 2.2439999998 (^) 2.24400000 2 .23400000 2.25400000
2 1.1259999999 2 2.2519999998 2.25200000 (^) 2.24200000 2.26200000
(^3) 1.1299999999 2 2.2599999998 (^) 2.26000000 2.25000000 (^) 2.27000000
Partiendo de esta información contenida en la sección cuerpo los valores en el resumen deberán reflejarse de la
siguiente manera:
Holguras
Total de
operaciones
ventas
gravadas
Total, de
operaciones
ventas gravadas
(redondeo dos
decimales)
Holgura
(0.0)
Holgura
(-0.01)
Holgura
(+0.01)
Suma V.G. Holgura 0.0 6.75599996 6.76 6.76 6.75 6.77
Suma V.G. Holgura -0.01 6.72600000 6.73 6.73 6.72 6.74
Suma V.G. Holgura +0.01 6.78600000 6.79 6.79 6 .78 6.80
Se puede observar que, para efectos de ingresar los valores correspondientes al Total de operaciones ventas
gravadas el valor con las reglas de redondeo a ingresar en el campo es $6.76, teniendo una tolerancia de $0.01 hacia
arriba o hacia abajo, por tanto, es posible ingresar en este campo los siguientes valores: $6.75, $6.76 o $6.77.
Si se retoman los valores aplicando holguras de -0.01 en el cuerpo del documento el valor a ingresar es $6.73
teniendo una tolerancia de $0.01 hacia arriba o hacia abajo, por tanto, es posible ingresar en este campo los
siguientes valores: $6.72, $6.73 o $6.74.
Si se retoman los valores aplicando holguras de +0.01 en el cuerpo del documento el valor a ingresar es $6.79
teniendo una tolerancia de $0.01 hacia arriba o hacia abajo, por tanto, es posible ingresar en este campo los
siguientes valores: $6.78, $6.79 o $6.80.
En ese sentido, sin perjuicio de las posiciones decimales utilizadas por los contribuyentes en sus operaciones
internas, éstos deberán cumplir con las anteriores reglas de redondeos y holgura en la generación de los DTE,
ajustándose a ocho posiciones decimales los campos por ítem y a dos posiciones decimales los campos de la Sección
Resumen, dentro de la holgura antes establecida.


## XXII. Versiones Legibles

## 1. Factura Electrónica

La Versión Legible que se presenta a continuación es de carácter sugerido, usted puede configurar la que va a
desarrollar de acuerdo a sus necesidades y su operatividad, respetando la categorización asignada a cada campo.

```
Ver.1
```
```
EMISOR
Nombre Comercial:
```
```
Nombre Comercial:
```
```
Descripción:
```
```
CUERPO N° Cantidad Unidad UnitarioPrecio Otros montos no afectos Descuento por Ítem SujetasVentas No ExentasVentas GravadasVentas
```
```
Valor del Tributo
RESUMEN
```
```
N° de Documento:
N° de Documento:
```
```
Tipo de doc. de Identificación:
```
```
N° de documento: Fecha del Documento:
OTROS DOCUMENTOS ASOCIADOS
Identificación documento:
```
```
VENTA A CUENTA DE TERCEROS
```
```
RECEPTOR
```
```
Número de Control:
```
```
Pagina 1 de 1
```
```
EMISOR
```
```
RECEPTOR
```
```
IDENTIFICACIÓN
```
```
DOCUMENTOS RELACIONADOS
```
```
Monto global Desc., Rebajas y otros a ventas no sujetas:
```
```
Monto global Desc., Rebajas y otros a ventas gravadas:
Nombre del Tributo
```
```
Monto Total de la Operación:
Total Otros Montos No Afectos:
Total a Pagar:
```
```
Suma de Ventas:
```
```
Código de Generación:
```
```
Nota: En sección Receptor, El campo "Tipo de doc. de Identificación" será dinamico, es decir de acuerdo al tipo de documento seleccionado por la persona que esta realizando el DTE así aparecerá en la Representación Gráfica. Ejemplo, si se selecciono el tipo de
documento pasaporte, aparecerá la palabra pasaporte y el número de documento respectivo a la par.
```
```
DOCUMENTO TRIBUTARIO ELECTRÓNICO
FACTURA
Módelo de Facturación:
```
```
IVA Retenido:
Retención Renta:
```
```
Monto global Desc., Rebajas y otros a ventas exentas:
```
```
Sumatoria de ventas:
```
```
Sub-Total
```
```
Descripción
```
```
T ipo de Documento:
```
```
DOCUMENTOS RELACIONADOS
```
```
Número de teléfono:Dirección:
```
```
Correo Electrónico:
Correo electrónico:
```
```
Actividad económica :
```
```
NIT:
```
```
Nombre o razón social: Nombre o razón social:
```
```
Tipo de Transmisión:
Fecha y Hora de Generación:
```
```
EXTENSIÓN Responsable por parte del Receptor:
```
```
SELLO DE
RECEPCIÓN
```
```
DOCUMENTOS OTROS
ASOCIADOS
```
```
VENTA A
CUENTA DE TERCEROS
```
```
Valor en Letras: Condición de la Operación:
Observaciones
Responsable por parte del Emisor:
```
```
NRC:
```
```
N° de doc. de Identificación:
```
```
Tipo de establecimiento:
```
```
NIT : Nombre, denominación o razón social:
```
```
Sello de Recepción:
```

## 2. Comprobante de Crédito Fiscal Electrónico V3

La Versión Legible que se presenta a continuación es de carácter sugerido, usted puede configurar la que va a
desarrollar de acuerdo a sus necesidades y su operatividad, respetando la categorización asignada a cada campo.

```
Ver.3
```
```
IDENTIFICACIÓN
```
```
RECEPTOR
Nombre o razón social: Nombre o razón social:
NIT: NIT:
Actividad económica:NRC: Actividad económica:NRC:
Dirección: Dirección: RECEPTOR
Número de teléfono: Correo electrónico:
Correo electrónico: Nombre comercial:
Nombre comercial:
Tipo de establecimiento:
```
```
OTROS DOCUMENTOS ASOCIADOS
```
```
CUERPO N° Cantidad Unidad Descripción
UnitarioPrecio Descuento por item Otros montos no afectos Ventas No Sujetas Ventas Exentas GravadasVentas
```
```
Valor del Tributo
```
```
Condición de la Operación:
```
```
Pagina 1 de 1
```
```
RECEPCIÓNSELLO DE
```
```
Valor en Letras:
Observaciones:
```
```
SUMA DE VENTAS:
```
```
Monto global Desc., Rebajas y otros a ventas Exentas:
Monto global Desc., Rebajas y otros a ventas gravadas:
Nombre del Tributo:
```
```
EXTENSIÓN Responsable por parte del emisor:
```
```
Identificación del documento:
```
```
NIT:
DOCUMENTOS RELACIONADOS
```
```
Sub-Total:
IVA Percibido:
IVA Retenido:
Monto Total de la Operación:Retención Renta:
Total Otros montos no afectos:
```
```
Responsable por parte del Receptor:
```
```
N° de Documento:
N° de Documento:
```
```
RESUMEN
```
```
Total a Pagar:
```
```
Suma Total de Operaciones:
Monto global Desc., Rebajas y otros a ventas no sujetas:
```
```
Tipo de Documento: N° de documento: Fecha de documento: DOCUMENTOS
RELACIONADOS
```
```
OTROS DOCUMENTOS ASOCIADOS
```
```
VENTA A CUENTA DE TERCEROS
VENTAS A CUENTA DE TERCEROS
```
```
Descripción:
```
```
Nombre, denominación o razón social:
```
```
EMISOR
```
```
DOCUMENTO TRIBUTARIO ELECTRÓNICO
COMPROBANTE DE CRÉDITO FISCAL
Código de Generación: Módelo de Facturación:
Número de Control : Tipo de Transmisión:
Sello de recepción: Fecha y Hora de Generación:
EMISOR
```

## 3. Nota de Remisión Electrónica v3

La Versión Legible que se presenta a continuación es de carácter sugerido, usted puede configurar la que va a
desarrollar de acuerdo a sus necesidades y su operatividad, respetando la categorización asignada a cada campo.

```
Ver. 3
```
```
Módelo de Facturación:
```
```
CUERPO N° Cantidad Unidad UnitarioPrecio Descuento por item Ventas No Sujetas ExentasVentas GravadasVentas
```
```
Valor del
Tributo
RESUMEN
```
```
Valor en Letras:
Observaciones:
```
```
Responsable por parte del Receptor:
Pagina 1 de 1
```
```
DOCUMENTO TRIBUTARIO ELECTRÓNICO
NOTA DE REMISIÓN
Código de Generación:
```
```
EMISOR RECEPTOR
```
```
Número de Control: Tipo de Transmisión:
Sello de Recepción:
```
```
Nombre o razón social:
```
```
DOCUMENTOS RELACIONADOS
```
```
VENTA A CUENTA DE TERCEROS
```
```
IDENTIFICACIÓN
```
```
VENTA A CUENTA DE
TERCEROS
```
```
NIT:
NRC:
Actividad
EMISOR económica:
Dirección: NRC:
```
```
SELLO DE
RECEPCIÓN
```
```
IVA Percibido:
IVA Retenido:
```
```
N° de Documento:
```
```
Número de teléfono: Dirección:
Correo electrónico: Correo electrónico:
Nombre Comercial: Nombre Comercial:
```
```
Tipo de Documento de
Identificación :
```
```
Actividad económica:
```
```
Número de documento
de Identificación:
```
```
Nombre o razón social:
```
```
EXTENSIÓN
```
```
T ipo de Documento: N° de documento:
```
```
Suma Total de Operaciones:
Monto global Desc., Rebajas y otros a ventas no
sujetas:
```
```
Descripción
```
```
Monto global Desc., Rebajas y otros a ventas
exentas:
Monto global Desc., Rebajas y otros a ventas
gravadas:
Nombre del Tributo:
```
```
Monto Total de la Operación:
```
```
Suma de Ventas:
```
```
Responsable por parte del Emisor: N° de Documento:
```
```
Sub-Total:
```
```
NIT : Nombre, denominación o razón social:
```
```
Tipo de establecimiento:
```
```
Fecha y Hora de Generación:
```
```
RECEPTOR
```
```
Fecha del Documento: DOCUMENTOS RELACIONADOS
```

## 4. Nota de Crédito Electrónica V3

La Versión Legible que se presenta a continuación es de carácter sugerido, usted puede configurar la que va a
desarrollar de acuerdo a sus necesidades y su operatividad, respetando la categorización asignada a cada campo.

```
Ver.3
```
```
RECEPTOR
```
```
DOCUMENTOS
RELACIONADOS
```
```
CUERPO N° Cantidad Unidad UnitarioPrecio Descuento por item Ventas No Sujetas ExentasVentas GravadasVentas
```
```
Valor del
Tributo RESUMEN
```
```
Pagina 1 de 1
```
```
Observaciones:
```
```
Responsable por parte del Emisor:
Responsable por parte del Receptor:
```
```
N° de Documento:
EXTENSIÓN N° de Documento:
```
```
Monto global Desc., Rebajas y otros a ventas no
sujetas:
Monto global Desc., Rebajas y otros a ventas
exentas:
Monto global Desc., Rebajas y otros a ventas
gravadas:
Nombre del Tributo:
```
```
NOTA DE CRÉDITO
IDENTIFICACIÓN
Código de Generación: Módelo de Facturación:
```
```
SELLO DE
RECEPCIÓN
```
```
Valor en Letras: Condición de la Operación:
```
```
EMISOR
Nombre o razón social:
```
```
Número de Control : Tipo de Transmisión:
Sello de Recepción: Fecha y Hora de Generación:
```
```
NRC:
```
```
SUMA DE VENTAS:
```
```
Actividad económica:
```
```
NIT:
```
```
VENTA A CUENTA
DE TERCEROS
```
```
Nombre Comercial:
```
```
Dirección: RECEPTOR
Correo electrónico:
```
```
DOCUMENTO TRIBUTARIO ELECTRÓNICO
```
```
Tipo de Documento: N° de Documento: Fecha del Documento:
```
```
Monto Total de la Operación:
```
```
Sub-Total:
IVA Percibido:
```
```
Correo electrónico:
```
```
Tipo de establecimiento:
```
```
Nombre o razón social:
NIT:
NRC:
Actividad económica :
Dirección:
Número de teléfono:
```
```
DOCUMENTOS RELACIONADOS
```
```
VENTA A CUENTA DE TERCEROS
NIT:
```
```
EMISOR
```
```
IVA Retenido:
```
```
Suma Total de Operaciones:
```
```
Nombre Comercial:
```
```
Nombre, denominación o razón social:
```
```
Descripción
```

## 5. Nota de Débito Electrónica v3

La Versión Legible que se presenta a continuación es de carácter sugerido, usted puede configurar la que va a
desarrollar de acuerdo a sus necesidades y su operatividad, respetando la categorización asignada a cada campo.

```
Ver.3
```
```
Código de Generación: Módelo de Facturación:
Número de Control: Tipo de Transmisión:
Sello de Recepción: Fecha y Hora de Generación:
```
```
RECEPTOR
Nombre o razón social: Nombre o razón social:
NIT: NIT:
NRC: NRC:
Actividad Económica: Actividad económica:
Dirección: Dirección:
Número de teléfono: Correo electrónico:
Correo electrónico: Nombre Comercial:
Nombre Comercial:
Tipo de establecimiento:
```
```
DOCUMENTOS RELACIONADOS
DOCUMENTOS
RELACIONADOS
```
```
CUERPO N° Cantidad Unidad Descripción UnitarioPrecio Descuento por item Ventas No Sujetas ExentasVentas GravadasVentas
```
```
Valor del
EXTENSIÓN Tributo RESUMEN
```
```
Pagina 1 de 1
```
```
EXTENSIÓN
```
```
Observaciones:
```
```
Condición de la Operación:
```
```
Responsable por parte del Emisor:
```
```
Responsable por parte del Emisor: N° de Documento:
N° de Documento:
```
```
SELLO DE
RECEPCIÓN
```
```
Tipo de Documento: N° de Documento:
```
```
Valor en Letras:
```
```
DOCUMENTO TRIBUTARIO ELECTRÓNICO
NOTA DE DÉBITO
```
```
EMISOR
```
```
Monto global Desc., Rebajas y otros a ventas no
sujetas:
```
```
Fecha del Documento:
```
```
IDENTIFICACIÓN
```
```
EMISOR
```
```
RECEPTOR
```
```
Monto global Desc., Rebajas y otros a ventas
gravadas:
Nombre del Tributo:
```
```
VENTA A CUENTA DE TERCEROS
VENTA A CUENTA
DE TERCEROS
NIT : Nombre, denominación o razón social:
```
```
SUMA DE VENTAS
Suma Total de Operaciones:
```
```
Monto global Desc., Rebajas y otros a ventas
exentas:
```
```
Monto Total de la Operación:
```
```
Sub-Total:
IVA Percibido:
IVA Retenido:
```

## 6. Comprobante de Retención Electrónico v1...............................................................................................

La Versión Legible que se presenta a continuación es de carácter sugerido, usted puede configurar la que va a
desarrollar de acuerdo a sus necesidades y su operatividad, respetando la categorización asignada a cada campo.

```
Ver.1
```
```
Código de Generación: Módelo de Facturación:
Número de Control: Tipo de Transmisión:
Sello de Recepción: Fecha y Hora de Generación:
```
```
Nombre Comercial:
```
```
NRC: Actividad económica : AGENTE DE RETENCIÓN
```
```
Correo electrónico:
```
```
NRC:
Nombre comercial:
Dirección:
```
```
N° N° del Doc. relacionado Fecha del doc. Descripción Monto Sujeto a Retención IVA Retenido CUERPO
```
```
N° de Documento:
N° de Documento:
```
```
Pagina 1 de 1
```
```
DOCUMENTO TRIBUTARIO ELECTRÓNICO
COMPROBANTE DE RETENCIÓN
```
```
Nombre o razón social: Tipo de Documento de Identificación:
```
```
IDENTIFICACIÓN
```
```
AGENTE DE RETENCIÓN
Nombre o razón social: NIT:
```
```
Dirección:
```
```
Tipo de establecimiento:
```
```
SUJETO DE
Actividad económica: N° Documento de Identificación: RETENCIÓN
Correo Electrónico:
```
```
EXTENSIÓN
```
```
Número de teléfono:
```
```
SUJETO DE RETENCIÓN (RECEPTOR)
```
```
Total Monto sujeto a retención:
Valor en Letras IVA retenido: Total IVA Retenido:
```
```
Tipo de Doc. Relacionado
```
```
RESUMEN
```
```
SELLO DE
RECEPCIÓN
```
```
Observación General:
```
```
Responsable por parte del Receptor:
```
```
Responsable por parte del Emisor:
```

## 7. Comprobante de Liquidación v1

La Versión Legible que se presenta a continuación es de carácter sugerido, usted puede configurar la que va a
desarrollar de acuerdo a sus necesidades y su operatividad, respetando la categorización asignada a cada campo.

```
Ver.1
```
```
Nombre Comercial:
```
```
N° RelacionadoTipo de Doc. Relacionado N° Doc. Fecha Exportaciones Ventas No Sujetas ExentasVentas GravadasVentas CUERPO
```
```
Valor del
Tributo
```
```
N° de Documento:
N° de Documento:
Pagina 1 de 1
```
```
Observaciones:
```
```
EXTENCIÓN
```
```
Responsable por parte del Emisor:
Responsable por parte del Receptor:
```
```
IVA percibido:
Total:
```
```
Valor en Letras: Condición de la Operación:
```
```
EXTENSIÓN
Monto Total de la Operación:
```
```
Tipo de establecimiento:
```
```
Observación por ítem
```
```
Suma de Ventas:
Suma Total Operaciones:
Nombre del Tributo:
```
```
Correo electrónico: Nombre Comercial:
```
```
INFORMACIÓN
COMISIONISTA
```
```
Actividad económica : Actividad económica:
```
```
Número de teléfono: Correo electrónico:
```
```
Dirección: Dirección:
```
```
NIT: NIT:
NRC: NRC:
INFORMACIÓN
MANDANTE
```
```
COMISIONISTA (Emisor) MANDANTE (Receptor)
Nombre o razón social: Nombre o razón social:
```
```
SELLO DE
RECEPCIÓN
```
```
Número de Control: Tipo de Transmisión:
Sello de Recepción: Fecha y Hora de Generación:
```
```
DOCUMENTO TRIBUTARIO ELECTRÓNICO
COMPROBANTE DE LIQUIDACIÓN
```
```
IDENTIFICACIÓN
Código de Generación: Módelo de Facturación:
```

## 8. Documento Contable de Liquidación Electrónico v1

La Versión Legible que se presenta a continuación es de carácter sugerido, usted puede configurar la que va a
desarrollar de acuerdo a sus necesidades y su operatividad, respetando la categorización asignada a cada campo.

```
Ver.1
```
```
NIT :
Dirección:
Tipo de
establecimiento:
```
```
EXTENSIÓN
```
```
Pagina 1 de 1
```
```
DOCUMENTO TRIBUTARIO ELECTRÓNICO
DOCUMENTO CONTABLE DE LIQUIDACIÓN
```
```
Número de Control:
Sello de Recepción:
```
```
Código de Generación: Módelo de Facturación:
SELLO DE
RECEPCIÓN
```
```
AGENTE PERCEPTOR (Emisor)
Nombre Comercial:
NRC: Actividad económica :
```
```
Nombre o razón social:
```
```
Nombre o razón social:
```
```
Correo electrónico:
```
```
AFILIADO (Receptor)
```
```
Número de teléfono:
```
```
Actividad económica:
```
```
Cantidad de documentos de
Valor de las operaciones a liquidar: liquidación:
```
```
NRC:
Tipo de establecimiento: Nombre Comercial:
```
```
NIT: Dirección:
Correo electrónico:
```
```
Observaciones:
```
```
Nombre del Responsable de la liquidación:
```
```
Valor Liquido a pagar al Afiliado:
Valor en Letras:
```
```
IVA de las operaciones a liquidar:
Montos sujetos a percepción sin IVA:
```
```
Doc. de identificación:
```
```
Porcentaje de comisión:
IVA de la comisión:
```
```
Descripción del monto no sujeto a
percepción:
Valores no sujetos a percepción:
Subtotal:
```
```
IVA Percibido (2%):
```
```
IDENTIFICACIÓN
```
```
EMISOR
(AGENTE
PERCEPTOR)
```
```
RECEPTOR
(AFILIADO)
```
```
Fecha inicio del periodo de
Liquidación: Fecha fin del periodo de liquidación:
```
```
CUERPO
```
```
Fecha y Hora de Generación:
```
```
Tipo de Transmisión:
```
```
Comisión:
```

## 9. Factura de Exportación Electrónica v1

La Versión Legible que se presenta a continuación es de carácter sugerido, usted puede configurar la que va a
desarrollar de acuerdo a sus necesidades y su operatividad, respetando la categorización asignada a cada campo.

```
Ver.1
```
```
Código de Generación:
Número de Control:
Sello de Recepción:
```
```
Nombre Comercial:
```
```
Nombre del Conductor: Identificación:N°de Modo de Transporte: N° ID transporte:
```
```
CUERPO N° Cantidad Unidad Precio Unitario Descuento por item Otros montos no afectos AfectasVentas
```
```
Pagina 1 de 1
```
```
NIT: N° de Doc. de Identificación del receptor:
NRC: Actividad Económica
Actividad económica : País destino:
```
```
DOCUMENTO TRIBUTARIO ELECTRÓNICO
FACTURA DE EXPORTACIÓN
Módelo de Facturación:
Tipo de Transmisión:
Fecha y Hora de Generación:
```
```
EXPORTADOR (Emisor) RECEPTOR
Nombre o razón social: Nombre o razón social:
```
```
Identificación del
doc. Asociado:
```
```
VENTA A CUENTA
DE TERCEROS
```
```
Monto global de Desc., Rebajas de operaciones
afectas:
```
```
Condición de la Operación:
```
```
VENTA A CUENTA DE TERCEROS
```
```
Descripción de doc.
asociado:
```
```
RESUMEN
```
```
NIT : Nombre, denominación o razón social:
```
```
Descripción
```
```
SELLO DE
RECEPCIÓN
```
```
IDENTIFICACIÓN
```
```
Monto Total de la Operación:
Total Otros Montos No Afectos:
Total General
```
```
Observaciones:
```
```
Total de Operaciones Afectas
```
```
Seguro:
Flete:
```
```
Valor en Letras:
Descripción Incoterms:
```
```
DOCUMENTOS
ASOCIADOS
```
```
EMISOR RECEPTOR
```
```
DOCUMENTOS ASOCIADOS
```
```
Dirección: Dirección:
Número de teléfono: Nombre Comercial:
Correo electrónico:
Tipo de establecimiento:
Recinto fiscal:
Regimen de exportación:
```

## 10. Factura Sujeto Excluido Electrónica v1

La Versión Legible que se presenta a continuación es de carácter sugerido, usted puede configurar la que va a
desarrollar de acuerdo a sus necesidades y su operatividad, respetando la categorización asignada a cada campo.

```
Ver.1
```
```
EMISOR
```
```
Nombre Comercial:
```
```
CUERPO N° Cantidad Unidad Precio Unitario Ventas
```
```
RESUMEN
```
```
Observaciones
```
```
N° de doc. de Identificación:
N° de teléfono:
```
```
Sub-Total
Total a Pagar:
Valor en Letras: Condición de la Operación:
Pagina 1 de 1
```
```
Sumatoria de ventas:
```
```
Tipo de establecimiento:
```
```
Descripción Descuento por ítem
```
```
Correo electrónico:
```
```
Número de teléfono: Dirección:
```
```
Dirección:
```
```
Actividad económica : RECEPTOR
```
```
NIT: Tipo de doc. de Identificación:
```
```
EMISOR RECEPTOR
Nombre o razón social: Nombre o razón social:
```
```
SELLO DE
RECEPCIÓN
```
```
Número de Control: Tipo de Transmisión:
Sello de Recepción: Fecha y Hora de Generación:
```
```
DOCUMENTO TRIBUTARIO ELECTRÓNICO
FACTURA SUJETO EXCLUIDO
Código de Generación: Módelo de Facturación: IDENTIFICACIÓN
```

## 11. Comprobante de Donación Electrónico v1

La Versión Legible que se presenta a continuación es de carácter sugerido, usted puede configurar la que va a
desarrollar de acuerdo a sus necesidades y su operatividad, respetando la categorización asignada a cada campo.

```
Ver.1
```
```
EMISOR
```
```
CUERPO N° Cantidad Unidad de Medida UnitarioValor DonadoValor
```
```
RESUMEN
```
```
N° de Teléfono:
Correo electrónico:
```
```
Total de la Donación
```
```
Valor en Letras:
Observaciones
```
```
Identificación documento: Descripción:
```
```
Pagina 1 de 1
```
```
Descripción Depreciación
```
```
Teléfono:
Correo electrónico:
```
```
OTROS DOCUMENTOS ASOCIADOS
OTROS
DOCUMENTOS
ASOCIADOS
```
```
Documento Asociado:
```
```
Tipo de establecimiento: RECEPTOR
Dirección:
```
```
Nombre, denominación o razón social:
Dirección:
```
```
Actividad económica :
```
```
Número de documento de
Identificación:
```
```
Tipo de documento de identificación:
```
```
EMISOR RECEPTOR
```
```
Nombre o razón social:
```
```
SELLO DE
RECEPCIÓN
```
```
Número de Control: Tipo de Transmisión:
Sello de Recepción: Fecha y Hora de Generación:
```
### DOCUMENTO TRIBUTARIO ELECTRÓNICO

```
COMPROBANTE DE DONACIÓN
Código de Generación: Módelo de Facturación: IDENTIFICACIÓN
```

## XXIII. Ejemplo Archivo DTE

Se muestra ejemplo de archivo JSON DTE firmado y con Sello de Recepción:
```json
{"identificacion":{"version":3,"ambiente":"00","tipoDte":"03","numeroControl":"DTE- 03 - 00000000 -
000000000000253","codigoGeneracion":"341CA743-70F1-4CFE-88BC-
7E4AE72E60CB","tipoModelo":1,"tipoOperacion":1,"tipoContingencia":null,"motivoContin":null,"fecEmi":"2
022 - 11 -
28","horEmi":"10:19:44","tipoMoneda":"USD"},"documentoRelacionado":null,"emisor":{"nit":"22222222222
221","nrc":"9000089","nombre":"SALVADOR CABALITO","codActividad":"46900","descActividad":"Venta
al por mayor de otros
productos","nombreComercial":null,"tipoEstablecimiento":"02","direccion":{"departamento":"06","municipio
":"14","complemento":"AV. ALVARADO DIAG. CENTROAMERICA, #
4,"},"telefono":"78963333","correo":"salvador@ggg.com","codEstableMH":null,"codEstable":null,"codPunt
oVentaMH":null,"codPuntoVenta":null},"receptor":{"nit":"22222222222211","nrc":"9000009","nombre":"SA
LVADOR CABAL","codActividad":"69","descActividad":"ACTIVIDADES JURÍDICAS Y
CONTABLES","nombreComercial":null,"direccion":{"departamento":"06","municipio":"14","complemento":"
Dirección de Prueba 1, N°
1234"},"telefono":"22444444","correo":"salvadorcabal@prueba.com"},"otrosDocumentos":null,"ventaTerc
ero":null,"cuerpoDocumento":[{"numItem":1,"tipoItem":1,"numeroDocumento":null,"codigo":null,"codTribut
o":null,"descripcion":"Servicio de consultoria
contable","cantidad":1,"uniMedida":59,"precioUni":2000,"montoDescu":0,"ventaNoSuj":0,"ventaExenta":0,
"ventaGravada":2000,"tributos":["20"],"psv":0,"noGravado":0}],"resumen":{"totalNoSuj":0,"totalExenta":0,"t
otalGravada":2000,"subTotalVentas":2000,"descuNoSuj":0,"descuExenta":0,"descuGravada":0,"porcentaj
eDescuento":0,"totalDescu":0,"tributos":[{"codigo":"20","descripcion":"Impuesto al Valor Agregado
13%","valor":260}],"subTotal":2000,"ivaPerci1":0,"ivaRete1":0,"reteRenta":0,"montoTotalOperacion":2260,
"totalNoGravado":0,"totalPagar":2260,"totalLetras":"DOS MIL DOSCIENTOS SESENTA DÓLARES
","saldoFavor":0,"condicionOperacion":1,"pagos":[{"codigo":"01","montoPago":2260,"plazo":null,"referenci
a":"","periodo":null}],"numPagoElectronico":null},"extension":{"nombEntrega":null,"docuEntrega":null,"nom
bRecibe":null,"docuRecibe":null,"observaciones":null,"placaVehiculo":null},"apendice":null,"firmaElectronic
a":"eyJhbGciOiJSUzUxMiJ9.ewogICJpZGVudGlmaWNhY2lvbiIgOiB7CiAgICAidmVyc2lvbiIgOiAzLAogIC
AgImFtYmllbnRlIiA6ICIwMCIsCiAgICAidGlwb0R0ZSIgOiAiMDMiLAogICAgIm51bWVyb0NvbnRyb2wiIDo
gIkRURS0wMy0wMDAwMDAwMC0wMDAwMDAwMDAwMDAyNTMiLAogICAgImNvZGlnb0dlbmVyYWN
pb24iIDogIjM0MUNBNzQzLTcwRjEtNENGRS04OEJDLTdFNEFFNzJFNjBDQiIsCiAgICAidGlwb01vZGVs
byIgOiAxLAogICAgInRpcG9PcGVyYWNpb24iIDogMSwKICAgICJ0aXBvQ29udGluZ2VuY2lhIiA6IG51bG
wsCiAgICAibW90aXZvQ29udGluIiA6IG51bGwsCiAgICAiZmVjRW1pIiA6ICIyMDIyLTExLTI4IiwKICAgICJo
b3JFbWkiIDogIjEwOjE5OjQ0IiwKICAgICJ0aXBvTW9uZWRhIiA6ICJVU0QiCiAgfSwKICAiZG9jdW1lbnRv
UmVsYWNpb25hZG8iIDogbnVsbCwKICAiZW1pc29yIiA6IHsKICAgICJuaXQiIDogIjIyMjIyMjIyMjIyMjIxIiwK
ICAgICJucmMiIDogIjkwMDAwODkiLAogICAgIm5vbWJyZSIgOiAiU0FMVkFET1IgQ0FCQUxJVE8iLAogIC
AgImNvZEFjdGl2aWRhZCIgOiAiNDY5MDAiLAogICAgImRlc2NBY3RpdmlkYWQiIDogIlZlbnRhIGFsIHBvc
iBtYXlvciBkZSBvdHJvcyBwcm9kdWN0b3MiLAogICAgIm5vbWJyZUNvbWVyY2lhbCIgOiBudWxsLAogIC
AgInRpcG9Fc3RhYmxlY2ltaWVudG8iIDogIjAyIiwKICAgICJkaXJlY2Npb24iIDogewogICAgICAiZGVwYXJ
0YW1lbnRvIiA6ICIwNiIsCiAgICAgICJtdW5pY2lwaW8iIDogIjE0IiwKICAgICAgImNvbXBsZW1lbnRvIiA6ICJ
BVi4gQUxWQVJBRE8gRElBRy4gQ0VOVFJPQU1FUklDQSwgIyA0LCIKICAgIH0sCiAgICAidGVsZWZvb
m8iIDogIjc4OTYzMzMzIiwKICAgICJjb3JyZW8iIDogInNhbHZhZG9yQGdnZy5jb20iLAogICAgImNvZEVzd
GFibGVNSCIgOiBudWxsLAogICAgImNvZEVzdGFibGUiIDogbnVsbCwKICAgICJjb2RQdW50b1ZlbnRhT
UgiIDogbnVsbCwKICAgICJjb2RQdW50b1ZlbnRhIiA6IG51bGwKICB9LAogICJyZWNlcHRvciIgOiB7CiAgI
CAibml0IiA6ICIyMjIyMjIyMjIyMjIxMSIsCiAgICAibnJjIiA6ICI5MDAwMDA5IiwKICAgICJub21icmUiIDogIlNB
TFZBRE9SIENBQkFMIiwKICAgICJjb2RBY3RpdmlkYWQiIDogIjY5IiwKICAgICJkZXNjQWN0aXZpZGFkIi
A6ICJBQ1RJVklEQURFUyBKVVLDjURJQ0FTIFkgQ09OVEFCTEVTIiwKICAgICJub21icmVDb21lcmNpY
WwiIDogbnVsbCwKICAgICJkaXJlY2Npb24iIDogewogICAgICAiZGVwYXJ0YW1lbnRvIiA6ICIwNiIsCiAgIC
AgICJtdW5pY2lwaW8iIDogIjE0IiwKICAgICAgImNvbXBsZW1lbnRvIiA6ICJEaXJlY2Npw7NuIGRlIFBydWV
iYSAxLCBOwrAgMTIzNCIKICAgIH0sCiAgICAidGVsZWZvbm8iIDogIjIyNDQ0NDQ0IiwKICAgICJjb3JyZW
8iIDogInNhbHZhZG9yY2FiYWxAcHJ1ZWJhLmNvbSIKICB9LAogICJvdHJvc0RvY3VtZW50b3MiIDogbnV
sbCwKICAidmVudGFUZXJjZXJvIiA6IG51bGwsCiAgImN1ZXJwb0RvY3VtZW50byIgOiBbIHsKICAgICJud
W1JdGVtIiA6IDEsCiAgICAidGlwb0l0ZW0iIDogMSwKICAgICJudW1lcm9Eb2N1bWVudG8iIDogbnVsbCw
KICAgICJjb2RpZ28iIDogbnVsbCwKICAgICJjb2RUcmlidXRvIiA6IG51bGwsCiAgICAiZGVzY3JpcGNpb24iI
DogIlNlcnZpY2lvIGRlIGNvbnN1bHRvcmlhIGNvbnRhYmxlIiwKICAgICJjYW50aWRhZCIgOiAxLAogICAgIn
VuaU1lZGlkYSIgOiA1OSwKICAgICJwcmVjaW9VbmkiIDogMjAwMCwKICAgICJtb250b0Rlc2N1IiA6IDAs
CiAgICAidmVudGFOb1N1aiIgOiAwLAogICAgInZlbnRhRXhlbnRhIiA6IDAsCiAgICAidmVudGFHcmF2YW
RhIiA6IDIwMDAsCiAgICAidHJpYnV0b3MiIDogWyAiMjAiIF0sCiAgICAicHN2IiA6IDAsCiAgICAibm9HcmF2
YWRvIiA6IDAKICB9IF0sCiAgInJlc3VtZW4iIDogewogICAgInRvdGFsTm9TdWoiIDogMCwKICAgICJ0b3R
hbEV4ZW50YSIgOiAwLAogICAgInRvdGFsR3JhdmFkYSIgOiAyMDAwLAogICAgInN1YlRvdGFsVmVudG
FzIiA6IDIwMDAsCiAgICAiZGVzY3VOb1N1aiIgOiAwLAogICAgImRlc2N1RXhlbnRhIiA6IDAsCiAgICAiZGV
zY3VHcmF2YWRhIiA6IDAsCiAgICAicG9yY2VudGFqZURlc2N1ZW50byIgOiAwLAogICAgInRvdGFsRGV
zY3UiIDogMCwKICAgICJ0cmlidXRvcyIgOiBbIHsKICAgICAgImNvZGlnbyIgOiAiMjAiLAogICAgICAiZGVzY
3JpcGNpb24iIDogIkltcHVlc3RvIGFsIFZhbG9yIEFncmVnYWRvIDEzJSIsCiAgICAgICJ2YWxvciIgOiAyNjA
KICAgIH0gXSwKICAgICJzdWJUb3RhbCIgOiAyMDAwLAogICAgIml2YVBlcmNpMSIgOiAwLAogICAgIml2
YVJldGUxIiA6IDAsCiAgICAicmV0ZVJlbnRhIiA6IDAsCiAgICAibW9udG9Ub3RhbE9wZXJhY2lvbiIgOiAyMj
YwLAogICAgInRvdGFsTm9HcmF2YWRvIiA6IDAsCiAgICAidG90YWxQYWdhciIgOiAyMjYwLAogICAgInR
vdGFsTGV0cmFzIiA6ICJET1MgTUlMIERPU0NJRU5UT1MgU0VTRU5UQSBEw5NMQVJFUyAiLAogICA
gInNhbGRvRmF2b3IiIDogMCwKICAgICJjb25kaWNpb25PcGVyYWNpb24iIDogMSwKICAgICJwYWdvcyI
gOiBbIHsKICAgICAgImNvZGlnbyIgOiAiMDEiLAogICAgICAibW9udG9QYWdvIiA6IDIyNjAsCiAgICAgICJw
bGF6byIgOiBudWxsLAogICAgICAicmVmZXJlbmNpYSIgOiAiIiwKICAgICAgInBlcmlvZG8iIDogbnVsbAogI
CAgfSBdLAogICAgIm51bVBhZ29FbGVjdHJvbmljbyIgOiBudWxsCiAgfSwKICAiZXh0ZW5zaW9uIiA6IHsKI
CAgICJub21iRW50cmVnYSIgOiBudWxsLAogICAgImRvY3VFbnRyZWdhIiA6IG51bGwsCiAgICAibm9tYlJ
lY2liZSIgOiBudWxsLAogICAgImRvY3VSZWNpYmUiIDogbnVsbCwKICAgICJvYnNlcnZhY2lvbmVzIiA6IG
51bGwsCiAgICAicGxhY2FWZWhpY3VsbyIgOiBudWxsCiAgfSwKICAiYXBlbmRpY2UiIDogbnVsbAp9.Dttb
L4-a5kJi583xK2gpdAoOxKHoUH8cUo_J8i2f-zKKfOUAhtn8R8FRjskMyi9WVL41QlsBJ0QB5j6kp-
njP8K5gfS0enWbmvthb-
ZpQgTaIf3EuDPXRq1KO7k46AFtZzu5C21gZ8tXYzIh4atGg8inH2EV9BNtOnDNSNFlm1CB5YEh8ypLCA
gTcuYnkcY9OvJAHkp_6R3QfMGYHQrf9Tp2HidQ1zRWcbnN-iD9Z9l9d3H2Gu-N3Gd3vdDQ-
hvtnuKIDZAKnoXEXRSi6bS4e_ycko6iN_9pSSzY6A5b68oTCN_DdbS3NUotpWIrAKdVt7qkWIzi-7r3z-
nG1V8iYw","selloRecibido":"20227A1DE27CA974440985C1791AE37F7821LT8M"}
```

## XXIV. Glosario

- **JSON:** JavaScript Object Notation (JSON) es un formato basado en texto estándar para representar datos
    estructurados en la sintaxis de objetos de JavaScript.
- **ESTRUCTURAS:** el esquema define sus tablas, sus campos en cada tabla y las relaciones entre cada campo
    y cada tabla.
- **ENVÍO DE DOCUMENTOS UNO A UNO** : en esta opción de envío, el emisor trasmite a la Administración
    Tributaria cada uno de los documentos electrónicos de forma independiente para su validación.
- **ENVÍO DE DOCUMENTOS POR LOTES:** en esta opción de envío, el emisor trasmite a la Administración
    Tributaria un grupo de documentos electrónicos de forma grupal, para la validación de cada uno de los
    documentos del lote.
- **COMISIONISTA:** persona que trabaja a cambio de comisiones mercantiles, vendiendo a cuenta de otro y
    cobrando una comisión.
- **CONSIGNATARIO:** persona natural o jurídica que recibe las mercancías en calidad de depósito y tiene la
    responsabilidad de conservarlas en el estado en que las recibió hasta que efectúe le venta, obteniendo una
    comisión sobre el precio pactado.
- **SUBASTADORES:** los subastadores valoran artículos, y organizan y dirigen subastas. Algunos se especializan
    en un tipo de artículo, en el que pueden ser entendidos. Los subastadores valoran las piezas que vayan a
    venderse en una subasta y organizan todos los aspectos de la venta.
- **EMISOR:** persona que emite el Documento Tributario Electrónico.
- **RECEPTOR:** persona que recibe el Documento Tributario Electrónico.
- **INCOTERM** : representa un término universal que define una transacción entre importador y exportador,
    de forma que ambas partes entiendan las tareas, costos, riesgos y responsabilidades, así como el manejo
    logístico y de transportación desde la salida del producto hasta la recepción por el país importador.
- **FLETE:** precio pagado o por pagar por el traslado de mercancías en un medio de transporte, sea este
    marítimo, aéreo o terrestre.
- **SEGURO (TRANSPORTE):** es un contrato que cubre las mercancías contra los diversos riesgos que puedan
    afectarlas durante su traslado de un lugar a otro durante determinado período (estancia), o situaciones
    (carga y descarga), relacionadas con el hecho de transporte.


## XXV. Abreviaturas

- **CT:** Código Tributario
- **NIT:** Número de Identificación Tributaria
- **NRC:** Número de Registro de Contribuyente
- **DTE:** Documento Tributario Electrónico
- **DE:** Documento Electrónico
- **CCFE:** Comprobante de Crédito Fiscal Electrónico
- **NCE:** Nota de Crédito Electrónica
- **NDE:** Nota de Débito Electrónica
- **NRE:** Nota de Remisión Electrónica
- **CRE:** Comprobante de Retención Electrónico
- **CLE:** Comprobante de Liquidación Electrónico
- **DCLE:** Documento Contable de Liquidación Electrónico
- **FSEE:** Factura Sujeto Excluido Electrónico
- **CDE:** Comprobante de Donación Electrónico
- **FE:** Factura Electrónica
- **FEXE:** Factura de Exportación Electrónica
- **UUID v4** : UUID son las siglas de Universally Unique Identifier, que en inglés significa, literalmente,
    ‘identificador único universal’ y v4 es la versión
- **DGII** : Dirección General de Impuestos Internos
- **AT:** Administración Tributaria