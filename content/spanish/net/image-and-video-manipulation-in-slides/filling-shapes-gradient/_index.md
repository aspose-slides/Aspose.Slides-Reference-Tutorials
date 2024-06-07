---
title: Cree impresionantes degradados en PowerPoint con Aspose.Slides
linktitle: Rellenar formas con degradado en diapositivas de presentación usando Aspose.Slides
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: ¡Mejore sus presentaciones con Aspose.Slides para .NET! Conozca el proceso paso a paso de rellenar formas con degradados. ¡Descarga tu prueba gratuita ahora!
type: docs
weight: 21
url: /es/net/image-and-video-manipulation-in-slides/filling-shapes-gradient/
---
## Introducción
Crear diapositivas de presentación visualmente cautivadoras es esencial para captar y mantener la atención de su audiencia. En este tutorial, lo guiaremos a través del proceso de mejorar sus diapositivas llenando una forma de elipse con un degradado usando Aspose.Slides para .NET.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
- Conocimientos básicos del lenguaje de programación C#.
- Visual Studio instalado en su máquina.
-  Aspose.Slides para la biblioteca .NET. Descargalo[aquí](https://releases.aspose.com/slides/net/).
- Un directorio de proyecto para organizar sus archivos.
## Importar espacios de nombres
En su proyecto de C#, incluya los espacios de nombres necesarios para Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Paso 1: crea una presentación
Comience creando una nueva presentación usando la biblioteca Aspose.Slides:
```csharp
string dataDir = "Your Documents Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Tu código va aquí...
}
```
## Paso 2: agrega una forma de elipse
Inserta una forma de elipse en la primera diapositiva de tu presentación:
```csharp
ISlide sld = pres.Slides[0];
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 75, 150);
```
## Paso 3: aplicar formato de degradado
Especifique que la forma debe rellenarse con un degradado y defina las características del degradado:
```csharp
shp.FillFormat.FillType = FillType.Gradient;
shp.FillFormat.GradientFormat.GradientShape = GradientShape.Linear;
shp.FillFormat.GradientFormat.GradientDirection = GradientDirection.FromCorner2;
```
## Paso 4: agregar paradas de degradado
Defina los colores y posiciones de las paradas del degradado:
```csharp
shp.FillFormat.GradientFormat.GradientStops.Add((float)1.0, PresetColor.Purple);
shp.FillFormat.GradientFormat.GradientStops.Add((float)0, PresetColor.Red);
```
## Paso 5: guarde la presentación
Guarde su presentación con la forma llena de degradado recién agregada:
```csharp
pres.Save(dataDir + "EllipseShpGrad_out.pptx", SaveFormat.Pptx);
```
Repita estos pasos en su código C#, asegurándose de que la secuencia y los valores de los parámetros sean adecuados. Esto dará como resultado un archivo de presentación con una forma de elipse visualmente atractiva rellena con un degradado.
## Conclusión
With Aspose.Slides for .NET, you can effortlessly elevate the visual aesthetics of your presentations. By following this guide, you've learned how to fill shapes with gradients, giving your slides a professional and engaging look.
---
## Preguntas frecuentes
### P: ¿Puedo aplicar degradados a formas que no sean elipses?
R: ¡Ciertamente! Aspose.Slides para .NET admite el relleno de degradado para varias formas, como rectángulos, polígonos y más.
### P: ¿Dónde puedo encontrar ejemplos adicionales y documentación detallada?
 R: Explora el[Aspose.Slides para la documentación de .NET](https://reference.aspose.com/slides/net/) para guías completas y ejemplos.
### P: ¿Hay una prueba gratuita disponible para Aspose.Slides para .NET?
 R: Sí, puedes acceder a una prueba gratuita[aquí](https://releases.aspose.com/).
### P: ¿Cómo puedo obtener soporte para Aspose.Slides para .NET?
R: Busque ayuda e interactúe con la comunidad en el[Foro Aspose.Slides](https://forum.aspose.com/c/slides/11).
### P: ¿Puedo comprar una licencia temporal de Aspose.Slides para .NET?
 R: Ciertamente, puedes obtener una licencia temporal.[aquí](https://purchase.aspose.com/temporary-license/).