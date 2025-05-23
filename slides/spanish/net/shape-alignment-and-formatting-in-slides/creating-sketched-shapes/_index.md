---
"description": "Aprende a añadir formas creativas a tus diapositivas con Aspose.Slides para .NET. ¡Mejora tu atractivo visual sin esfuerzo!"
"linktitle": "Creación de formas esbozadas en diapositivas de presentación con Aspose.Slides"
"second_title": "API de procesamiento de PowerPoint Aspose.Slides .NET"
"title": "Crea formas esbozadas impresionantes con Aspose.Slides"
"url": "/es/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Crea formas esbozadas impresionantes con Aspose.Slides

## Introducción
Bienvenido a nuestra guía paso a paso para crear formas esbozadas en diapositivas de presentación con Aspose.Slides para .NET. Si desea añadir un toque de creatividad a sus presentaciones, las formas esbozadas proporcionan una estética única y dibujada a mano. En este tutorial, le guiaremos a través del proceso, desglosándolo en pasos sencillos para garantizar una experiencia fluida.
## Prerrequisitos
Antes de sumergirnos en el tutorial, asegúrese de tener los siguientes requisitos previos:
- Aspose.Slides para .NET: Asegúrate de tener instalada la biblioteca Aspose.Slides para .NET. Puedes descargarla. [aquí](https://releases.aspose.com/slides/net/).
- Entorno de desarrollo: configure un entorno de desarrollo .NET con su IDE preferido.
## Importar espacios de nombres
Comience importando los espacios de nombres necesarios en su proyecto .NET. Este paso garantiza el acceso a las clases y funcionalidades necesarias para trabajar con Aspose.Slides.
```csharp
using System;
using System.Collections.Generic;
using System.Drawing.Imaging;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Util;
using Aspose.Slides.Export;
using Aspose.Slides.MathText;
```
## Paso 1: Configurar el proyecto
Comience creando un nuevo proyecto .NET o abriendo uno existente. Asegúrese de incluir Aspose.Slides en las referencias del proyecto.
## Paso 2: Inicializar Aspose.Slides
Inicialice Aspose.Slides añadiendo el siguiente fragmento de código. Esto configura la presentación y especifica las rutas de salida para el archivo de presentación y la imagen en miniatura.
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // Continúe con los siguientes pasos...
}
```
## Paso 3: Agregar la forma esbozada
Ahora, agreguemos una forma esbozada a la diapositiva. En este ejemplo, agregaremos un rectángulo con efecto de boceto a mano alzada.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// Transformar la forma en un boceto de estilo a mano alzada
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## Paso 4: Generar miniatura
Genere una miniatura de la diapositiva para visualizar la forma esbozada. Guarde la miniatura como archivo PNG.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## Paso 5: Guardar la presentación
Guarde el archivo de presentación con la forma esbozada.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
¡Listo! Has creado una presentación con formas esbozadas usando Aspose.Slides para .NET.
## Conclusión
Añadir formas esbozadas a las diapositivas de tu presentación puede mejorar el atractivo visual y captar la atención de tu audiencia. Con Aspose.Slides para .NET, el proceso se simplifica, permitiéndote dar rienda suelta a tu creatividad sin esfuerzo.
## Preguntas frecuentes
### 1. ¿Puedo personalizar el efecto del boceto?
Sí, Aspose.Slides para .NET ofrece varias opciones de personalización para efectos de boceto. Consulte la [documentación](https://reference.aspose.com/slides/net/) para obtener información detallada.
### 2. ¿Hay una prueba gratuita disponible?
¡Claro! Puedes probar una prueba gratuita de Aspose.Slides para .NET. [aquí](https://releases.aspose.com/).
### 3. ¿Dónde puedo obtener ayuda?
Para cualquier ayuda o consulta, visite el [Foro de Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 4. ¿Cómo puedo comprar Aspose.Slides para .NET?
Para comprar Aspose.Slides para .NET, visite el sitio web [página de compra](https://purchase.aspose.com/buy).
### 5. ¿Ofrecen licencias temporales?
Sí, hay licencias temporales disponibles [aquí](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}