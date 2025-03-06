---
title: Creación de geometría personalizada en C# con Aspose.Slides para .NET
linktitle: Creación de geometría personalizada en forma de geometría usando Aspose.Slides
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda a crear geometría personalizada en Aspose.Slides para .NET. Eleva tus presentaciones con formas únicas. Guía paso a paso para desarrolladores de C#.
weight: 15
url: /es/net/shape-geometry-and-positioning-in-slides/creating-custom-geometry/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introducción
En el dinámico mundo de las presentaciones, agregar formas y geometrías únicas puede elevar su contenido, haciéndolo más atractivo y visualmente atractivo. Aspose.Slides para .NET proporciona una poderosa solución para crear geometrías personalizadas dentro de formas, lo que le permite liberarse de los diseños convencionales. Este tutorial lo guiará a través del proceso de creación de geometría personalizada en GeometryShape usando Aspose.Slides para .NET.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
- Un conocimiento básico del lenguaje de programación C#.
- Biblioteca Aspose.Slides para .NET instalada en su entorno de desarrollo.
- Visual Studio o cualquier entorno de desarrollo C# preferido configurado.
## Importar espacios de nombres
Para comenzar, importe los espacios de nombres necesarios a su proyecto C#:
```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Drawing;
using System.IO;
using Aspose.Slides.Export;
```
## Paso 1: configura tu proyecto
Cree un nuevo proyecto de C# en su entorno de desarrollo preferido. Asegúrese de que Aspose.Slides para .NET esté instalado correctamente.
## Paso 2: Defina su directorio de documentos
```csharp
string dataDir = "Your Document Directory";
bool isExists = Directory.Exists(dataDir);
if (!isExists)
    Directory.CreateDirectory(dataDir);
```
## Paso 3: Establecer el radio de la estrella exterior e interior
```csharp
float R = 100, r = 50; // Radio de estrella exterior e interior
```
## Paso 4: crear una ruta de geometría estelar
```csharp
GeometryPath starPath = CreateStarGeometry(R, r);
```
## Paso 5: crea una presentación
```csharp
using (Presentation pres = new Presentation())
{
    // Crear nueva forma
    GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, R * 2, R * 2);
    // Establecer una nueva ruta de geometría para la forma
    shape.SetGeometryPath(starPath);
    // guardar la presentación
    string resultPath = Path.Combine(dataDir, "GeometryShapeCreatesCustomGeometry.pptx");
    pres.Save(resultPath, SaveFormat.Pptx);
}
```
## Paso 6: Definir el método CreateStarGeometry
```csharp
private static GeometryPath CreateStarGeometry(float outerRadius, float innerRadius)
{
    GeometryPath starPath = new GeometryPath();
    List<PointF> points = new List<PointF>();
    int step = 72;
    for (int angle = -90; angle < 270; angle += step)
    {
        double radians = angle * (Math.PI / 180f);
        double x = outerRadius * Math.Cos(radians);
        double y = outerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
        radians = Math.PI * (angle + step / 2) / 180.0;
        x = innerRadius * Math.Cos(radians);
        y = innerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
    }
    starPath.MoveTo(points[0]);
    for (int i = 1; i < points.Count; i++)
    {
        starPath.LineTo(points[i]);
    }
    starPath.CloseFigure();
    return starPath;
}
```
## Conclusión
¡Felicidades! Ha aprendido con éxito cómo crear geometría personalizada en GeometryShape usando Aspose.Slides para .NET. Esto abre un mundo de posibilidades para crear presentaciones únicas y visualmente impresionantes.
## Preguntas frecuentes
### 1. ¿Puedo utilizar Aspose.Slides para .NET con otros lenguajes de programación?
Sí, Aspose.Slides admite varios lenguajes de programación, pero este tutorial se centra en C#.
### 2. ¿Dónde puedo encontrar la documentación de Aspose.Slides para .NET?
 Visita el[documentación](https://reference.aspose.com/slides/net/) para obtener información detallada.
### 3. ¿Existe una prueba gratuita disponible de Aspose.Slides para .NET?
 Sí, puedes explorar un[prueba gratis](https://releases.aspose.com/) para experimentar las características.
### 4. ¿Cómo puedo obtener soporte para Aspose.Slides para .NET?
 Busque ayuda e interactúe con la comunidad en el[Foro Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 5. ¿Dónde puedo comprar Aspose.Slides para .NET?
 Puedes comprar Aspose.Slides para .NET[aquí](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
