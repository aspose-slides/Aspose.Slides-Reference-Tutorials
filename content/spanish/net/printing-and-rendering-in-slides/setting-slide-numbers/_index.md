---
title: Configuración de números de diapositivas para presentaciones usando Aspose.Slides
linktitle: Configuración de números de diapositivas para presentaciones usando Aspose.Slides
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda a agregar y personalizar números de diapositivas en presentaciones de PowerPoint usando Aspose.Slides para .NET. Esta guía paso a paso proporciona ejemplos de código fuente para configurar el proyecto, cargar una presentación, agregar números de diapositiva, personalizar su formato y ajustar su ubicación.
type: docs
weight: 16
url: /es/net/printing-and-rendering-in-slides/setting-slide-numbers/
---

## Introducción a Aspose.Slides para .NET

Aspose.Slides para .NET es una biblioteca versátil que permite a los desarrolladores de .NET crear, modificar y manipular presentaciones de PowerPoint mediante programación. Proporciona una amplia gama de funciones para interactuar con varios elementos de presentaciones, incluidas diapositivas, formas, texto, imágenes y más. En esta guía, nos centraremos en agregar y personalizar números de diapositivas usando Aspose.Slides para .NET.

## Requisitos previos

Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Visual Studio (o cualquier otro entorno de desarrollo .NET)
-  Biblioteca Aspose.Slides para .NET (Descargar desde[aquí](https://releases.aspose.com/slides/net/)

## Configurando el proyecto

1. Cree un nuevo proyecto de Visual Studio (aplicación de consola, por ejemplo).
2. Agregue una referencia a la biblioteca Aspose.Slides para .NET.

## Cargando una presentación

Para comenzar, carguemos una presentación de PowerPoint existente:

```csharp
using Aspose.Slides;

// Cargar la presentación
using Presentation presentation = new Presentation("your-presentation.pptx");
```

## Agregar números de diapositiva

A continuación, agreguemos números de diapositiva a cada diapositiva de la presentación:

```csharp
// Habilitar números de diapositiva
foreach (ISlide slide in presentation.Slides)
{
    // Agregar forma de número de diapositiva
    IAutoShape slideNumberShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 10, 10, 50, 20);
    slideNumberShape.TextFrame.Text = (slide.SlideNumber).ToString();
}
```

## Personalización del formato del número de diapositiva

Puede personalizar la apariencia de los números de diapositiva ajustando la fuente, el color, el tamaño y más:

```csharp
foreach (IAutoShape shape in presentation.Slides[0].Shapes.OfType<IAutoShape>())
{
    // Personaliza la fuente y el color
    ITextFrame textFrame = shape.TextFrame;
    IParagraph paragraph = textFrame.Paragraphs[0];
    IPortion portion = paragraph.Portions[0];
    
    portion.PortionFormat.FontHeight = 12;
    portion.PortionFormat.FillFormat.SolidFillColor.Color = Color.Black;
}
```

## Actualización de la ubicación del número de diapositiva

También puede ajustar la posición de los números de diapositiva en cada diapositiva:

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IAutoShape shape in slide.Shapes.OfType<IAutoShape>())
    {
        shape.Left = slide.SlideSize.Size.Width - shape.Width - 10;
        shape.Top = slide.SlideSize.Size.Height - shape.Height - 10;
    }
}
```

## Guardar la presentación modificada

Una vez que haya agregado y personalizado los números de diapositiva, guarde la presentación modificada:

```csharp
presentation.Save("output-presentation.pptx", SaveFormat.Pptx);
```

## Conclusión

En esta guía, exploramos cómo mejorar sus presentaciones agregando y personalizando números de diapositivas usando Aspose.Slides para .NET. Si sigue los pasos proporcionados y los ejemplos de código, puede automatizar el proceso de agregar números de diapositiva y crear presentaciones de aspecto profesional.

## Preguntas frecuentes

### ¿Cómo instalo Aspose.Slides para .NET?

 Puede descargar la biblioteca Aspose.Slides para .NET desde[aquí](https://releases.aspose.com/slides/net/). Después de la descarga, agregue una referencia a la biblioteca en su proyecto .NET.

### ¿Puedo personalizar la apariencia de los números de diapositivas?

Sí, puede personalizar la fuente, el color, el tamaño y otros atributos de los números de diapositiva utilizando los ejemplos de código proporcionados.

### ¿Cómo puedo ajustar la posición de los números de diapositiva en cada diapositiva?

Puede ajustar la posición de los números de diapositiva modificando las coordenadas de las formas de los números de diapositiva, como se muestra en los ejemplos de código.

### ¿Aspose.Slides para .NET solo sirve para agregar números de diapositivas?

No, Aspose.Slides para .NET ofrece una amplia gama de funciones más allá de agregar números de diapositiva. Le permite crear, modificar y manipular varios elementos de presentaciones de PowerPoint mediante programación.

### ¿Las modificaciones son reversibles si deseo eliminar los números de diapositiva más adelante?

Sí, puedes eliminar fácilmente los números de las diapositivas eliminando las formas correspondientes de las diapositivas usando la biblioteca Aspose.Slides.