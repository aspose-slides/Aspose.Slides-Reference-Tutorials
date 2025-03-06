---
title: Dominar imágenes agregar segmentos con Aspose.Slides en .NET
linktitle: Agregar segmentos a la forma geométrica en una presentación con Aspose.Slides
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda cómo mejorar sus aplicaciones .NET con Aspose.Slides. Este tutorial lo guiará a través de la adición de segmentos a formas geométricas para presentaciones cautivadoras.
weight: 13
url: /es/net/shape-geometry-and-positioning-in-slides/adding-segments-geometry-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dominar imágenes agregar segmentos con Aspose.Slides en .NET

## Introducción
En el mundo del desarrollo .NET, crear presentaciones visualmente atractivas es un requisito común. Aspose.Slides para .NET es una poderosa biblioteca que facilita la integración perfecta de sólidas capacidades de creación de presentaciones en sus aplicaciones .NET. Este tutorial se centra en un aspecto específico del diseño de presentaciones: agregar segmentos a formas geométricas.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
- Conocimientos básicos del lenguaje de programación C#.
- Visual Studio instalado en su máquina.
- Biblioteca Aspose.Slides para .NET descargada y referenciada en su proyecto.
## Importar espacios de nombres
En su código C#, asegúrese de importar los espacios de nombres necesarios para acceder a las funcionalidades de Aspose.Slides. Agregue las siguientes líneas a su código:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Ahora, dividamos el ejemplo en varios pasos.
## Paso 1: configura tu proyecto
Comience creando un nuevo proyecto de C# en Visual Studio. Asegúrese de tener referencia a la biblioteca Aspose.Slides en su proyecto.
## Paso 2: crea una presentación
Inicialice un nuevo objeto de presentación utilizando la biblioteca Aspose.Slides. Esto servirá como lienzo para tu forma geométrica.
```csharp
using (Presentation pres = new Presentation())
{
    // Su código para crear una presentación va aquí
}
```
## Paso 3: agrega una forma geométrica
Crea una forma geométrica dentro de la presentación. Por ejemplo, agreguemos un rectángulo a la primera diapositiva.
```csharp
GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
## Paso 4: obtener la ruta de geometría
Recupera la ruta geométrica de la forma creada para manipular sus segmentos.
```csharp
IGeometryPath geometryPath = shape.GetGeometryPaths()[0];
```
## Paso 5: agregar segmentos
Agregue segmentos (líneas) al trazado geométrico. En este ejemplo, se agregan dos líneas a la ruta.
```csharp
geometryPath.LineTo(100, 50, 1);
geometryPath.LineTo(100, 50, 4);
```
## Paso 6: Asignar ruta de geometría editada
Asigne la ruta de geometría modificada nuevamente a la forma para aplicar los cambios.
```csharp
shape.SetGeometryPath(geometryPath);
```
## Paso 7: guarde la presentación
Guarde la presentación modificada en la ubicación deseada.
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Con estos pasos, habrá agregado exitosamente segmentos a una forma geométrica en una presentación usando Aspose.Slides para .NET.
## Conclusión
Aspose.Slides para .NET permite a los desarrolladores mejorar sus aplicaciones con capacidades avanzadas de creación de presentaciones. Agregar segmentos a formas geométricas proporciona un medio para personalizar los elementos visuales de sus presentaciones.
### Preguntas frecuentes
### ¿Puedo agregar diferentes tipos de formas usando Aspose.Slides?
Sí, Aspose.Slides admite varios tipos de formas, incluidos rectángulos, círculos y formas geométricas personalizadas.
### ¿Se requiere una licencia para usar Aspose.Slides en mi proyecto?
Sí, se necesita una licencia válida. Puede obtener una licencia temporal para fines de prueba o comprar una licencia completa para producción.
### ¿Cómo puedo obtener asistencia para consultas relacionadas con Aspose.Slides?
 Visita el[Foro Aspose.Slides](https://forum.aspose.com/c/slides/11) para apoyo y debates de la comunidad.
### ¿Hay otros tutoriales disponibles para Aspose.Slides?
 Explorar el[documentación](https://reference.aspose.com/slides/net/) para guías completas y ejemplos.
### ¿Puedo probar Aspose.Slides gratis antes de comprarlo?
 Sí, puedes descargar una prueba gratuita desde[aquí](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
