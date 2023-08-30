---
title: Crear formas esbozadas en diapositivas de presentación con Aspose.Slides
linktitle: Crear formas esbozadas en diapositivas de presentación con Aspose.Slides
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda a crear diapositivas de presentación cautivadoras con formas esbozadas utilizando Aspose.Slides para .NET. Siga esta guía paso a paso con el código fuente completo para agregar elementos personalizados y creativos a sus diapositivas.
type: docs
weight: 13
url: /es/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---

## Introducción a la creación de formas esbozadas en diapositivas de presentación

Las diapositivas de presentación son una herramienta poderosa para transmitir información visualmente. A veces, es posible que desees agregar un toque personal a tus diapositivas incorporando formas esbozadas, lo que puede hacer que tus presentaciones sean más atractivas y creativas. En esta guía paso a paso, exploraremos cómo lograr esto usando la biblioteca Aspose.Slides para .NET. Al final de este tutorial, podrá crear diapositivas de presentación con formas esbozadas que se destaquen. ¡Vamos a sumergirnos!

## Configurando el proyecto

 Antes de comenzar, asegúrese de tener el entorno de desarrollo .NET configurado en su máquina. Puede descargar la última versión de Aspose.Slides desde el sitio web[aquí](https://releases.aspose.com/slides/net/). Una vez descargada, instale la biblioteca en su proyecto.

## Crear una nueva presentación

Comencemos creando una nueva presentación usando Aspose.Slides. Así es como puedes hacerlo:

```csharp
using Aspose.Slides;

// Crear una nueva presentación
Presentation presentation = new Presentation();
```

## Agregar formas esbozadas

Para agregar formas esbozadas a sus diapositivas, puede usar formas libres disponibles en Aspose.Slides. Estas formas se pueden personalizar para que parezcan bocetos dibujados a mano. A continuación se muestra un ejemplo de cómo agregar un rectángulo esbozado a una diapositiva:

```csharp
// Accede a la primera diapositiva
ISlide slide = presentation.Slides[0];

// Definir los puntos para el rectángulo esbozado.
PointF[] points = new PointF[]
{
    new PointF(100, 100),
    new PointF(200, 100),
    new PointF(200, 200),
    new PointF(100, 200)
};

// Agregar una forma libre a la diapositiva
IFreeformShape freeformShape = slide.Shapes.AddFreeform(ShapeType.Rectangle, points);

// Personaliza la apariencia de la forma esbozada.
freeformShape.LineFormat.Style = LineStyle.Single;
freeformShape.LineFormat.Width = 2;
freeformShape.FillFormat.FillType = FillType.Solid;
freeformShape.FillFormat.SolidFillColor.Color = Color.LightGray;
```

## Personalización de formas esbozadas

Puede personalizar aún más las formas esbozadas ajustando sus colores, estilos de línea y otras propiedades. Experimente con diferentes configuraciones para lograr el efecto de dibujado a mano deseado.

## Guardar y exportar la presentación

Una vez que haya agregado formas esbozadas a su presentación, puede guardarla y exportarla a varios formatos, como PPTX o PDF. Así es como puedes hacerlo:

```csharp
// Guarde la presentación en un archivo.
presentation.Save("SketchedShapesPresentation.pptx", SaveFormat.Pptx);
```

## Conclusión

En este tutorial, exploramos cómo crear diapositivas de presentación con formas esbozadas usando Aspose.Slides para .NET. Al agregar formas esbozadas a sus diapositivas, puede agregar un toque creativo y personalizado a sus presentaciones, haciéndolas más atractivas para su audiencia. Siéntete libre de experimentar con diferentes formas y opciones de personalización para crear diapositivas visualmente atractivas que dejen un impacto duradero.

## Preguntas frecuentes

### ¿Cómo puedo descargar Aspose.Slides para .NET?

 Puede descargar la última versión de Aspose.Slides para .NET desde su página de lanzamientos.[aquí](https://releases.aspose.com/slides/net/).

### ¿Puedo personalizar la apariencia de las formas esbozadas?

Sí, puedes personalizar la apariencia de las formas esbozadas ajustando sus colores, estilos de línea y otras propiedades usando Aspose.Slides.

### ¿Aspose.Slides es adecuado tanto para principiantes como para desarrolladores experimentados?

Sí, Aspose.Slides proporciona una API fácil de usar que es adecuada tanto para principiantes como para desarrolladores experimentados. Ofrece documentación completa para ayudarle a comenzar.

### ¿Puedo exportar mi presentación con formas esbozadas a PDF?

¡Absolutamente! Puede exportar su presentación con formas esbozadas a varios formatos, incluido PDF, utilizando las opciones de exportación proporcionadas por Aspose.Slides.

### ¿Cómo puedo agregar otros tipos de formas esbozadas, como círculos o líneas?

 Puede agregar otros tipos de formas esbozadas, como círculos o líneas, modificando los puntos y el tipo de forma en el`AddFreeform` método. Experimente con diferentes configuraciones de puntos para crear las formas que desee.