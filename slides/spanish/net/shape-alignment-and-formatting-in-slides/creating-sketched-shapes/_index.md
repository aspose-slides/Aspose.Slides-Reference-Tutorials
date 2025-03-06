---
title: Crea impresionantes formas esbozadas con Aspose.Slides
linktitle: Crear formas esbozadas en diapositivas de presentación con Aspose.Slides
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda a agregar formas esbozadas creativas a las diapositivas de su presentación usando Aspose.Slides para .NET. ¡Mejora el atractivo visual sin esfuerzo!
weight: 13
url: /es/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introducción
Bienvenido a nuestra guía paso a paso sobre cómo crear formas esbozadas en diapositivas de presentación usando Aspose.Slides para .NET. Si desea agregar un toque de creatividad a sus presentaciones, las formas esbozadas brindan una estética única y dibujada a mano. En este tutorial, lo guiaremos a través del proceso, dividiéndolo en pasos simples para garantizar una experiencia fluida.
## Requisitos previos
Antes de sumergirnos en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
-  Aspose.Slides para .NET: asegúrese de tener instalada la biblioteca Aspose.Slides para .NET. Puedes descargarlo[aquí](https://releases.aspose.com/slides/net/).
- Entorno de desarrollo: configure un entorno de desarrollo .NET con su IDE preferido.
## Importar espacios de nombres
Comience importando los espacios de nombres necesarios en su proyecto .NET. Este paso garantiza que tenga acceso a las clases y funcionalidades necesarias para trabajar con Aspose.Slides.
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
## Paso 1: configurar el proyecto
Comience creando un nuevo proyecto .NET o abriendo uno existente. Asegúrese de incluir Aspose.Slides en las referencias de su proyecto.
## Paso 2: Inicializar Aspose.Slides
Inicialice Aspose.Slides agregando el siguiente fragmento de código. Esto configura la presentación y especifica las rutas de salida para el archivo de presentación y la imagen en miniatura.
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // Continúe con los siguientes pasos...
}
```
## Paso 3: agregue la forma esbozada
Ahora, agreguemos una forma esbozada a la diapositiva. En este ejemplo, agregaremos un rectángulo con un efecto de boceto a mano alzada.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// Transforma la forma en un boceto de un estilo a mano alzada.
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## Paso 4: generar miniatura
Genere una miniatura de la diapositiva para visualizar la forma esbozada. Guarde la miniatura como un archivo PNG.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## Paso 5: guardar la presentación
Guarde el archivo de presentación con la forma esbozada.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
¡Eso es todo! Ha creado con éxito una presentación con formas esbozadas utilizando Aspose.Slides para .NET.
## Conclusión
Agregar formas esbozadas a las diapositivas de tu presentación puede mejorar el atractivo visual y atraer a tu audiencia. Con Aspose.Slides para .NET, el proceso se vuelve sencillo y le permite dar rienda suelta a su creatividad sin esfuerzo.
## Preguntas frecuentes
### 1. ¿Puedo personalizar el efecto del boceto?
 Sí, Aspose.Slides para .NET ofrece varias opciones de personalización para efectos de boceto. Referirse a[documentación](https://reference.aspose.com/slides/net/) para obtener información detallada.
### 2. ¿Hay una prueba gratuita disponible?
 ¡Ciertamente! Puede explorar una prueba gratuita de Aspose.Slides para .NET[aquí](https://releases.aspose.com/).
### 3. ¿Dónde puedo obtener ayuda?
 Para cualquier ayuda o consulta, visite el[Foro Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 4. ¿Cómo puedo comprar Aspose.Slides para .NET?
 Para comprar Aspose.Slides para .NET, visite el[pagina de compra](https://purchase.aspose.com/buy).
### 5. ¿Ofrecen licencias temporales?
 Sí, hay licencias temporales disponibles[aquí](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
