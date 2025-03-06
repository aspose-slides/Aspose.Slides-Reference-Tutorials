---
title: Agregar desplazamiento de estiramiento a la izquierda en PowerPoint con Aspose.Slide
linktitle: Agregar desplazamiento de estiramiento a la izquierda para el marco de imagen en Aspose.Slides
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda cómo mejorar las presentaciones de PowerPoint usando Aspose.Slides para .NET. Siga nuestra guía paso a paso para agregar un desplazamiento elástico hacia la izquierda en los marcos de cuadros.
weight: 14
url: /es/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introducción
Aspose.Slides para .NET es una poderosa biblioteca que permite a los desarrolladores manipular presentaciones de PowerPoint con facilidad. En este tutorial, exploraremos el proceso de agregar un desplazamiento de estiramiento a la izquierda para un marco de imagen usando Aspose.Slides para .NET. Siga esta guía paso a paso para mejorar sus habilidades para trabajar con imágenes y formas en presentaciones de PowerPoint.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
-  Aspose.Slides para .NET: asegúrese de tener la biblioteca instalada. Si no, descárgalo del[Aspose.Slides para la documentación de .NET](https://reference.aspose.com/slides/net/).
- Entorno de desarrollo: disponer de un entorno de desarrollo funcional con capacidades .NET.
## Importar espacios de nombres
Comience importando los espacios de nombres necesarios en su proyecto .NET:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Paso 1: configura tu proyecto
Cree un nuevo proyecto o abra uno existente. Asegúrese de tener referencia a la biblioteca Aspose.Slides en su proyecto.
## Paso 2: crear un objeto de presentación
 Instanciar el`Presentation` clase, que representa el archivo PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // Su código para los pasos siguientes irá aquí.
}
```
## Paso 3: obtenga la primera diapositiva
Recupere la primera diapositiva de la presentación:
```csharp
ISlide slide = pres.Slides[0];
```
## Paso 4: crear una instancia de la imagen
Cargue la imagen que desea utilizar:
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgEx = pres.Images.AddImage(img);
```
## Paso 5: agregar autoforma de rectángulo
Cree una autoforma de tipo rectángulo:
```csharp
IAutoShape aShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Paso 6: establezca el tipo de relleno y el modo de relleno de imagen
Configure el tipo de relleno de la forma y el modo de relleno de la imagen:
```csharp
aShape.FillFormat.FillType = FillType.Picture;
aShape.FillFormat.PictureFillFormat.PictureFillMode = PictureFillMode.Stretch;
```
## Paso 7: configurar la imagen para llenar la forma
Especifique la imagen para rellenar la forma:
```csharp
aShape.FillFormat.PictureFillFormat.Picture.Image = imgEx;
```
## Paso 8: especificar compensaciones de estiramiento
Defina los desplazamientos de la imagen desde los bordes correspondientes del cuadro delimitador de la forma:
```csharp
aShape.FillFormat.PictureFillFormat.StretchOffsetLeft = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetRight = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetTop = -20;
aShape.FillFormat.PictureFillFormat.StretchOffsetBottom = -10;
```
## Paso 9: guarde la presentación
Escriba el archivo PPTX en el disco:
```csharp
pres.Save(dataDir + "StretchOffsetLeftForPictureFrame_out.pptx", SaveFormat.Pptx);
```
¡Felicidades! Ha agregado con éxito un desplazamiento de extensión a la izquierda para un marco de imagen usando Aspose.Slides para .NET.
## Conclusión
En este tutorial, exploramos el proceso de manipulación de marcos de imágenes en presentaciones de PowerPoint usando Aspose.Slides para .NET. Al seguir la guía paso a paso, obtendrá información sobre cómo trabajar con imágenes, formas y desplazamientos.
## Preguntas frecuentes
### P: ¿Puedo aplicar compensaciones de estiramiento a otras formas además de los rectángulos?
R: Si bien este tutorial se centra en rectángulos, se pueden aplicar compensaciones de estiramiento a varias formas admitidas por Aspose.Slides.
### P: ¿Cómo puedo ajustar las compensaciones de estiramiento para obtener diferentes efectos?
R: Experimente con diferentes valores de compensación para lograr el impacto visual deseado. Ajuste los valores para adaptarlos a sus requisitos específicos.
### P: ¿Aspose.Slides es compatible con el último marco .NET?
R: Aspose.Slides se actualiza periódicamente para garantizar la compatibilidad con las últimas versiones de .NET Framework.
### P: ¿Dónde puedo encontrar ejemplos y recursos adicionales para Aspose.Slides?
 R: Explora el[Documentación de Aspose.Slides](https://reference.aspose.com/slides/net/) para obtener ejemplos y orientación completos.
### P: ¿Puedo aplicar múltiples compensaciones de estiramiento a una sola forma?
R: Sí, puede combinar múltiples compensaciones de estiramiento para lograr efectos visuales complejos y personalizados.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
