---
title: Agregar marcos de video a diapositivas de presentación usando Aspose.Slides
linktitle: Agregar marcos de video a diapositivas de presentación usando Aspose.Slides
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda cómo mejorar sus presentaciones agregando cuadros de video usando Aspose.Slides para .NET. Cree contenido atractivo e interactivo sin problemas.
type: docs
weight: 19
url: /es/net/shape-effects-and-manipulation-in-slides/adding-video-frames/
---

## Introducción a Aspose.Slides e integración de vídeo

Aspose.Slides es una biblioteca completa que permite a los desarrolladores crear, manipular y convertir presentaciones de PowerPoint mediante programación. Al integrar marcos de video en sus diapositivas, puede mejorar sus presentaciones y hacerlas más dinámicas y atractivas.

## Requisitos previos para incorporar videos

Antes de comenzar, asegúrese de tener lo siguiente:

- Visual Studio o cualquier entorno de desarrollo .NET preferido
- Aspose.Slides para la biblioteca .NET instalada
- Una presentación de PowerPoint (PPTX) donde desea agregar cuadros de video

## Configurar su entorno de desarrollo

1. Abra Visual Studio y cree un nuevo proyecto .NET.
2.  Instale el paquete Aspose.Slides NuGet:`Install-Package Aspose.Slides`.

## Cargar una presentación y acceder a diapositivas

Para comenzar, cargue su presentación de PowerPoint usando Aspose.Slides:

```csharp
using Aspose.Slides;

// Cargar la presentación
using Presentation presentation = new Presentation("your-presentation.pptx");

// Acceder a diapositivas
ISlideCollection slides = presentation.Slides;
```

## Agregar archivos de video a la presentación

1. Coloque sus archivos de video en una carpeta dentro de su proyecto.
2. Agregue referencias a estos archivos en su código:

```csharp
// Agregar archivos de vídeo
string videoPath = "path-to-your-videos-folder";
string[] videoFiles = Directory.GetFiles(videoPath, "*.mp4");
```

## Colocar fotogramas de vídeo en diapositivas

Repita las diapositivas y agregue fotogramas de vídeo:

```csharp
foreach (ISlide slide in slides)
{
    foreach (string videoFile in videoFiles)
    {
        IVideoFrame videoFrame = slide.Shapes.AddVideoFrame(100, 100, 320, 240, videoFile);
    }
}
```

## Personalización de las propiedades del fotograma de vídeo

Puede personalizar las propiedades del fotograma de vídeo como la posición, el tamaño y el estilo:

```csharp
foreach (IVideoFrame videoFrame in slide.Shapes.OfType<IVideoFrame>())
{
    videoFrame.X = 200;
    videoFrame.Y = 150;
    videoFrame.Width = 480;
    videoFrame.Height = 360;
}
```

## Manejo de opciones de reproducción

 Controle la reproducción de vídeo usando el`VideoPlayModePreset` enumeración:

```csharp
foreach (IVideoFrame videoFrame in slide.Shapes.OfType<IVideoFrame>())
{
    videoFrame.PlayMode = VideoPlayModePreset.Auto;
}
```

## Guardar y exportar la presentación modificada

Guarde su presentación después de agregar cuadros de video:

```csharp
presentation.Save("modified-presentation.pptx", SaveFormat.Pptx);
```

## Conclusión

La incorporación de fotogramas de vídeo en las diapositivas de su presentación utilizando Aspose.Slides mejora el impacto visual de su contenido. Ha aprendido a integrar vídeos sin problemas, personalizar las propiedades de los fotogramas de vídeo y controlar las opciones de reproducción. Comience a crear presentaciones dinámicas y atractivas que cautiven a su audiencia.

## Preguntas frecuentes

### ¿Cómo agrego varios videos a una sola diapositiva?

Repita sus archivos de video y agregue fotogramas de video a la diapositiva deseada usando el código proporcionado.

### ¿Puedo controlar la configuración de reproducción de video?

 Sí, puedes usar el`VideoPlayModePreset` enumeración para configurar opciones de reproducción como la reproducción automática.

### ¿Qué formatos de vídeo son compatibles?

Aspose.Slides admite varios formatos de video, incluidos MP4, AVI, WMV y más.

### ¿Es posible agregar vídeos mediante programación en C#?

Por supuesto, Aspose.Slides para .NET proporciona una API fácil de usar para agregar videos a diapositivas mediante programación usando C#.

### ¿Puedo modificar la apariencia del cuadro de video?

Sí, puede personalizar la posición, el tamaño y otras propiedades visuales del cuadro de video según sus requisitos.