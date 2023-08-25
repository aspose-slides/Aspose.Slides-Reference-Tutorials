---
title: Exportar formas a formato SVG desde la presentación
linktitle: Exportar formas a formato SVG desde la presentación
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda a exportar formas desde una presentación de PowerPoint al formato SVG usando Aspose.Slides para .NET. Guía paso a paso con código fuente incluido. Extraiga formas de manera eficiente para diversas aplicaciones.
type: docs
weight: 16
url: /es/net/presentation-manipulation/export-shapes-to-svg-format-from-presentation/
---
Esta guía lo guiará a través del proceso de exportar formas de una presentación al formato SVG usando la biblioteca Aspose.Slides para .NET. Aspose.Slides es una potente API que le permite trabajar con archivos de Microsoft PowerPoint mediante programación. En este tutorial, aprenderá cómo extraer formas de una presentación y guardarlas en formato SVG usando C#.

## Requisitos previos

Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Visual Studio instalado
- Comprensión básica de la programación en C#.
-  Aspose.Slides para la biblioteca .NET. Puedes descargarlo desde[aquí](https://releases.aspose.com/slides/net/).

## Guía paso por paso

Siga estos pasos para exportar formas a formato SVG desde una presentación:

### 1. Crea un nuevo proyecto

Abra Visual Studio y cree un nuevo proyecto de C#.

### 2. Agregar referencia a Aspose.Slides

En su proyecto, haga clic derecho en "Referencias" en el Explorador de soluciones, luego haga clic en "Agregar referencia". Busque y seleccione la DLL Aspose.Slides que descargó.

### 3. Cargue la presentación

```csharp
using Aspose.Slides;

// Cargar la presentación
Presentation presentation = new Presentation("presentation.pptx");
```

### 4. Iterar a través de formas

```csharp
foreach (IShape shape in presentation.Slides[0].Shapes)
{
    // Comprueba si la forma es una forma de grupo.
    if (shape is IGroupShape groupShape)
    {
        foreach (IShape groupChildShape in groupShape.Shapes)
        {
            // Exportar la forma a SVG
            string svgFileName = $"shape_{groupChildShape.Id}.svg";
            groupChildShape.WriteAsSvg(svgFileName);
        }
    }
    else
    {
        // Exportar la forma a SVG
        string svgFileName = $"shape_{shape.Id}.svg";
        shape.WriteAsSvg(svgFileName);
    }
}
```

### 5. Guarde archivos SVG

```csharp
presentation.Save("output.pptx", SaveFormat.Pptx); // Guardar cambios en la presentación.
```

## Preguntas frecuentes

### ¿Cómo puedo instalar Aspose.Slides para .NET?

 Puede descargar la biblioteca Aspose.Slides para .NET desde[aquí](https://releases.aspose.com/slides/net/). Siga las instrucciones de instalación proporcionadas en la documentación.

### ¿Cómo cargo una presentación de PowerPoint usando Aspose.Slides?

 Puedes cargar una presentación usando el`Presentation` constructor de clases. Proporcione la ruta al archivo de PowerPoint como parámetro.

### ¿Cómo exporto una forma al formato SVG?

 Puedes usar el`WriteAsSvg` método en un`IShape` objeto para exportarlo a formato SVG. Debe especificar el nombre del archivo para la salida SVG.

## Conclusión

En este tutorial, aprendió cómo exportar formas desde una presentación de PowerPoint al formato SVG usando la biblioteca Aspose.Slides para .NET. Esto puede resultar útil cuando necesita extraer formas individuales para usarlas en otras aplicaciones o plataformas que admitan gráficos SVG. Aspose.Slides proporciona una forma sencilla y eficiente de lograr esto mediante programación.

 Para obtener más detalles y funciones avanzadas, consulte la[Aspose.Slides para referencia de API .NET](https://reference.aspose.com/slides/net/).