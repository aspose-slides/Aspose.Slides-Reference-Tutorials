---
title: Crear formas de grupo en diapositivas de presentación con Aspose.Slides
linktitle: Crear formas de grupo en diapositivas de presentación con Aspose.Slides
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda a crear diapositivas de presentación cautivadoras con formas grupales usando Aspose.Slides para .NET. Siga nuestra guía paso a paso y nuestro ejemplo de código fuente para agregar, agrupar y transformar formas fácilmente, mejorando sus presentaciones.
type: docs
weight: 11
url: /es/net/image-and-video-manipulation-in-slides/creating-group-shapes/
---

## Introducción a Aspose.Slides para .NET

Aspose.Slides para .NET es una biblioteca completa y rica en funciones que permite a los desarrolladores manipular presentaciones de PowerPoint mediante programación. Ya sea que desee crear, modificar o convertir archivos de presentación, Aspose.Slides proporciona una amplia gama de herramientas y funcionalidades para simplificar el proceso.

## Requisitos previos

Antes de comenzar a trabajar con Aspose.Slides para .NET, asegúrese de cumplir con los siguientes requisitos previos:

- Visual Studio: instale Visual Studio en su máquina.
-  Biblioteca Aspose.Slides: descargue y haga referencia a la biblioteca Aspose.Slides en su proyecto. Puedes descargarlo desde[aquí](https://releases.aspose.com/slides/net/).

## Agregar Aspose.Slides a su proyecto

1. Descargue la biblioteca Aspose.Slides desde el enlace proporcionado.
2. Cree un nuevo proyecto en Visual Studio o abra uno existente.
3. Haga clic derecho en su proyecto en el Explorador de soluciones y seleccione "Administrar paquetes NuGet".
4. Elija la pestaña "Examinar" y busque "Aspose.Slides".
5. Instale el paquete Aspose.Slides en su proyecto.

## Crear una nueva presentación

Comencemos creando una nueva presentación de PowerPoint usando Aspose.Slides:

```csharp
using Aspose.Slides;

// Crear una nueva presentación
Presentation presentation = new Presentation();
```

## Agregar formas a la diapositiva

A continuación, agreguemos algunas formas a la diapositiva. En este ejemplo, agregaremos dos rectángulos:

```csharp
// Accede a la primera diapositiva
ISlide slide = presentation.Slides[0];

// Agregar rectángulos a la diapositiva
IShape shape1 = slide.Shapes.AddRectangle(100, 100, 200, 100);
IShape shape2 = slide.Shapes.AddRectangle(300, 100, 150, 150);
```

## Agrupar formas

Ahora, agrupemos las formas para administrarlas colectivamente:

```csharp
// Formas de grupo
IGroupShape groupShape = slide.Shapes.GroupShapes(new IShape[] { shape1, shape2 });
```

## Aplicar transformaciones a formas agrupadas

Puedes aplicar varias transformaciones a las formas agrupadas. Por ejemplo, rotemos las formas agrupadas 45 grados:

```csharp
// Girar el grupo 45 grados.
groupShape.Rotation = 45;
```

## Ejemplo de código fuente

Aquí está el ejemplo de código fuente completo sobre la creación de formas de grupo usando Aspose.Slides:

```csharp
using Aspose.Slides;

namespace GroupShapesExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Crear una nueva presentación
            Presentation presentation = new Presentation();

            // Accede a la primera diapositiva
            ISlide slide = presentation.Slides[0];

            // Agregar rectángulos a la diapositiva
            IShape shape1 = slide.Shapes.AddRectangle(100, 100, 200, 100);
            IShape shape2 = slide.Shapes.AddRectangle(300, 100, 150, 150);

            // Formas de grupo
            IGroupShape groupShape = slide.Shapes.GroupShapes(new IShape[] { shape1, shape2 });

            // Girar el grupo 45 grados.
            groupShape.Rotation = 45;

            // guardar la presentación
            presentation.Save("GroupShapesExample.pptx", SaveFormat.Pptx);
        }
    }
}
```

## Conclusión

En este tutorial, aprendió cómo crear formas de grupo en diapositivas de presentación usando Aspose.Slides para .NET. La biblioteca proporciona una forma sencilla de agregar formas, agruparlas y aplicar transformaciones para mejorar sus presentaciones de forma dinámica.

## Preguntas frecuentes

### ¿Cómo instalo Aspose.Slides para .NET?

 Puede descargar la biblioteca Aspose.Slides desde el enlace proporcionado:[aquí](https://releases.aspose.com/slides/net/). Una vez descargado, puede agregarlo a su proyecto usando paquetes NuGet.

### ¿Puedo aplicar diferentes transformaciones a formas agrupadas?

Sí, puedes aplicar varias transformaciones como rotación, escala y posicionamiento a las formas agrupadas, lo que te permite personalizar la apariencia visual de tus diapositivas.

### ¿Aspose.Slides es adecuado tanto para crear como para modificar presentaciones?

¡Absolutamente! Aspose.Slides para .NET es una biblioteca versátil que admite la creación, modificación y conversión de archivos de presentación. Proporciona una amplia gama de funciones para satisfacer diferentes necesidades.

### ¿Puedo agrupar formas de diferentes tipos?

 Sí, puedes agrupar formas de diferentes tipos, como rectángulos, círculos y cuadros de texto, usando el`GroupShapes` método. Esto le permite gestionarlos y manipularlos colectivamente.

### ¿Aspose.Slides es adecuado sólo para aplicaciones .NET?

Sí, Aspose.Slides está diseñado específicamente para aplicaciones .NET. Sin embargo, también hay versiones disponibles para otros lenguajes de programación, como Java.