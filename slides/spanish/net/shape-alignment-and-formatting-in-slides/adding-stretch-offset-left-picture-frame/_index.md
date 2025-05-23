---
"description": "Aprenda a mejorar sus presentaciones de PowerPoint con Aspose.Slides para .NET. Siga nuestra guía paso a paso para añadir desplazamiento de estiramiento a la izquierda en los marcos de imagen."
"linktitle": "Cómo añadir un desplazamiento de estiramiento a la izquierda para el marco de imagen en Aspose.Slides"
"second_title": "API de procesamiento de PowerPoint Aspose.Slides .NET"
"title": "Cómo agregar desplazamiento de estiramiento a la izquierda en PowerPoint con Aspose.Slide"
"url": "/es/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Cómo agregar desplazamiento de estiramiento a la izquierda en PowerPoint con Aspose.Slide

## Introducción
Aspose.Slides para .NET es una potente biblioteca que permite a los desarrolladores manipular presentaciones de PowerPoint con facilidad. En este tutorial, exploraremos el proceso de añadir un desplazamiento de estiramiento a la izquierda para un marco de imagen usando Aspose.Slides para .NET. Siga esta guía paso a paso para mejorar sus habilidades con imágenes y formas en presentaciones de PowerPoint.
## Prerrequisitos
Antes de sumergirse en el tutorial, asegúrese de tener los siguientes requisitos previos:
- Aspose.Slides para .NET: Asegúrese de tener la biblioteca instalada. De lo contrario, descárguela desde [Documentación de Aspose.Slides para .NET](https://reference.aspose.com/slides/net/).
- Entorno de desarrollo: Disponer de un entorno de desarrollo funcional con capacidades .NET.
## Importar espacios de nombres
Comience importando los espacios de nombres necesarios en su proyecto .NET:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Paso 1: Configura tu proyecto
Cree un nuevo proyecto o abra uno existente. Asegúrese de tener la biblioteca Aspose.Slides referenciada en su proyecto.
## Paso 2: Crear un objeto de presentación
Instanciar el `Presentation` clase, que representa el archivo PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // Su código para los pasos siguientes irá aquí.
}
```
## Paso 3: Obtener la primera diapositiva
Recuperar la primera diapositiva de la presentación:
```csharp
ISlide slide = pres.Slides[0];
```
## Paso 4: Crear una instancia de la imagen
Carga la imagen que quieras utilizar:
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgEx = pres.Images.AddImage(img);
```
## Paso 5: Agregar autoforma de rectángulo
Crear una autoforma de tipo Rectángulo:
```csharp
IAutoShape aShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Paso 6: Establezca el tipo de relleno y el modo de relleno de la imagen
Configure el tipo de relleno de la forma y el modo de relleno de la imagen:
```csharp
aShape.FillFormat.FillType = FillType.Picture;
aShape.FillFormat.PictureFillFormat.PictureFillMode = PictureFillMode.Stretch;
```
## Paso 7: Configurar la imagen para rellenar la forma
Especifique la imagen para rellenar la forma:
```csharp
aShape.FillFormat.PictureFillFormat.Picture.Image = imgEx;
```
## Paso 8: Especificar los desplazamientos de estiramiento
Define los desplazamientos de la imagen desde los bordes correspondientes del cuadro delimitador de la forma:
```csharp
aShape.FillFormat.PictureFillFormat.StretchOffsetLeft = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetRight = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetTop = -20;
aShape.FillFormat.PictureFillFormat.StretchOffsetBottom = -10;
```
## Paso 9: Guardar la presentación
Escriba el archivo PPTX en el disco:
```csharp
pres.Save(dataDir + "StretchOffsetLeftForPictureFrame_out.pptx", SaveFormat.Pptx);
```
¡Felicitaciones! Has añadido correctamente un desplazamiento de estiramiento a la izquierda para un marco de imagen usando Aspose.Slides para .NET.
## Conclusión
En este tutorial, exploramos el proceso de manipulación de marcos de imagen en presentaciones de PowerPoint con Aspose.Slides para .NET. Siguiendo la guía paso a paso, ha adquirido conocimientos sobre cómo trabajar con imágenes, formas y desplazamientos.
## Preguntas frecuentes
### P: ¿Puedo aplicar desplazamientos de estiramiento a otras formas además de rectángulos?
R: Si bien este tutorial se centra en los rectángulos, los desplazamientos de estiramiento se pueden aplicar a varias formas compatibles con Aspose.Slides.
### P: ¿Cómo puedo ajustar los desplazamientos de estiramiento para obtener diferentes efectos?
Experimente con diferentes valores de compensación para lograr el impacto visual deseado. Ajuste los valores según sus necesidades específicas.
### P: ¿Aspose.Slides es compatible con el último marco .NET?
R: Aspose.Slides se actualiza periódicamente para garantizar la compatibilidad con las últimas versiones de .NET Framework.
### P: ¿Dónde puedo encontrar ejemplos y recursos adicionales para Aspose.Slides?
A: Explora el [Documentación de Aspose.Slides](https://reference.aspose.com/slides/net/) para obtener ejemplos completos y orientación.
### P: ¿Puedo aplicar múltiples desplazamientos de estiramiento a una sola forma?
R: Sí, puedes combinar múltiples desplazamientos de estiramiento para lograr efectos visuales complejos y personalizados.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}