---
title: Remodelación de diapositivas de presentación con Aspose.Slides para .NET
linktitle: Cambiar el orden de las formas en las diapositivas de una presentación usando Aspose.Slides
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda a remodelar las diapositivas de una presentación usando Aspose.Slides para .NET. Siga esta guía paso a paso para reordenar las formas y mejorar el atractivo visual.
weight: 26
url: /es/net/shape-effects-and-manipulation-in-slides/changing-order-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introducción
Crear diapositivas de presentación visualmente atractivas es un aspecto crucial de una comunicación eficaz. Aspose.Slides para .NET permite a los desarrolladores manipular diapositivas mediante programación, ofreciendo una amplia gama de funcionalidades. En este tutorial, profundizaremos en el proceso de cambiar el orden de las formas en las diapositivas de una presentación usando Aspose.Slides para .NET.
## Requisitos previos
Antes de embarcarnos en este viaje, asegúrese de cumplir con los siguientes requisitos previos:
-  Aspose.Slides para .NET: asegúrese de tener la biblioteca Aspose.Slides integrada en su proyecto .NET. Si no, puedes descargarlo desde[página de lanzamientos](https://releases.aspose.com/slides/net/).
- Entorno de desarrollo: configure un entorno de desarrollo funcional con Visual Studio o cualquier otra herramienta de desarrollo .NET.
- Comprensión básica de C#: familiarícese con los conceptos básicos del lenguaje de programación C#.
## Importar espacios de nombres
En su proyecto C#, incluya los espacios de nombres necesarios para acceder a la funcionalidad Aspose.Slides:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Paso 1: configura tu proyecto
Cree un nuevo proyecto en Visual Studio o su entorno de desarrollo .NET preferido. Asegúrese de que se haga referencia a Aspose.Slides para .NET en su proyecto.
## Paso 2: cargue la presentación
```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## Paso 3: acceda a la diapositiva y las formas
```csharp
ISlide slide = presentation.Slides[0];
```
## Paso 4: agrega una nueva forma
```csharp
IAutoShape shp3 = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
shp3.FillFormat.FillType = FillType.NoFill;
shp3.AddTextFrame(" ");
```
## Paso 5: modifica el texto en la forma
```csharp
ITextFrame txtFrame = shp3.TextFrame;
IParagraph para = txtFrame.Paragraphs[0];
IPortion portion = para.Portions[0];
portion.Text = "Watermark Text Watermark Text Watermark Text";
```
## Paso 6: agrega otra forma
```csharp
shp3 = slide.Shapes.AddAutoShape(ShapeType.Triangle, 200, 365, 400, 150);
```
## Paso 7: cambiar el orden de las formas
```csharp
slide.Shapes.Reorder(2, shp3);
```
## Paso 8: guarde la presentación modificada
```csharp
presentation.Save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
```
Esto completa la guía paso a paso para cambiar el orden de las formas en las diapositivas de una presentación usando Aspose.Slides para .NET.
## Conclusión
Aspose.Slides para .NET simplifica la tarea de manipular diapositivas de presentación mediante programación. Siguiendo este tutorial, habrá aprendido cómo reordenar formas, lo que le permitirá mejorar el atractivo visual de sus presentaciones.
## Preguntas frecuentes
### P: ¿Puedo usar Aspose.Slides para .NET en entornos Windows y Linux?
R: Sí, Aspose.Slides para .NET es compatible con entornos Windows y Linux.
### P: ¿Existe alguna consideración de licencia para usar Aspose.Slides en un proyecto comercial?
 R: Sí, puede encontrar detalles de licencia y opciones de compra en el[Página de compra de Aspose.Slides](https://purchase.aspose.com/buy).
### P: ¿Hay una prueba gratuita disponible para Aspose.Slides para .NET?
 R: Sí, puedes explorar las funciones con el[prueba gratis](https://releases.aspose.com/) disponible en el sitio web de Aspose.Slides.
### P: ¿Dónde puedo encontrar soporte o hacer preguntas relacionadas con Aspose.Slides para .NET?
 R: Visita el[Foro Aspose.Slides](https://forum.aspose.com/c/slides/11) para obtener apoyo e interactuar con la comunidad.
### P: ¿Cómo puedo obtener una licencia temporal de Aspose.Slides para .NET?
 R: Puedes adquirir un[licencia temporal](https://purchase.aspose.com/temporary-license/) para fines de evaluación.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
