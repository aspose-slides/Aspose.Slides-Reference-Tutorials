---
title: Extraer vídeo de diapositiva
linktitle: Extraer vídeo de diapositiva
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Domine la extracción de videos de diapositivas de PowerPoint usando Aspose.Slides para .NET. Siga nuestra guía con ejemplos de código.
type: docs
weight: 14
url: /es/net/audio-and-video-extraction/extract-video/
---

## Introducción

En el mundo digital actual, las presentaciones multimedia se han convertido en una parte esencial de la comunicación. Las presentaciones de PowerPoint suelen incluir una combinación de texto, imágenes y vídeos para transmitir información de forma eficaz. Sin embargo, puede haber ocasiones en las que necesites extraer un vídeo de una diapositiva para diversos fines, como archivarlo, compartirlo o editarlo más. Aquí es donde entra en juego Aspose.Slides para .NET.

## Requisitos previos

Antes de sumergirnos en la guía paso a paso, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos de C# y .NET framework.
- Visual Studio instalado
-  Biblioteca Aspose.Slides para .NET (descargar desde[aquí](https://releases.aspose.com/slides/net)

## Guía paso por paso

Repasemos el proceso de extracción de un video de una diapositiva usando Aspose.Slides para .NET:

### Paso 1: instalación

1. Abra Visual Studio y cree un nuevo proyecto de C#.
2. Haga clic derecho en su proyecto en el Explorador de soluciones y seleccione "Administrar paquetes NuGet".
3. Busque "Aspose.Slides" e instale la última versión.

### Paso 2: cargar la presentación

```csharp
using Aspose.Slides;

// Cargar la presentación
using var presentation = new Presentation("your-presentation.pptx");
```

 Reemplazar`"your-presentation.pptx"` con la ruta real a su archivo de presentación de PowerPoint.

### Paso 3: extraer vídeo

```csharp
// Obtenga la primera diapositiva
var slide = presentation.Slides[0];

// Iterar a través de formas de diapositivas
foreach (var shape in slide.Shapes)
{
    if (shape is IVideoFrame videoFrame)
    {
        // Extrae el vídeo del fotograma del vídeo.
        var video = videoFrame.EmbeddedVideo;
        // Se puede realizar un procesamiento adicional con el objeto de video.
    }
}
```

### Paso 4: guardar vídeo

```csharp
// Guarde el video extraído
video.WriteToFile("extracted-video.mp4");
```

 Reemplazar`"extracted-video.mp4"` con el nombre y la ruta deseados para el archivo de vídeo extraído.

## Conclusión

Aspose.Slides para .NET simplifica la tarea de extraer vídeos de presentaciones de PowerPoint. Con sólo unas pocas líneas de código, puede recuperar vídeos incrustados en diapositivas y guardarlos como archivos de vídeo independientes. Ya sea que esté buscando reutilizar contenido o crear compilaciones, esta biblioteca proporciona una solución perfecta.

## Preguntas frecuentes

### ¿Cómo puedo acceder a la documentación de Aspose.Slides?

 Puede consultar la documentación de Aspose.Slides para .NET en[aquí](https://reference.aspose.com/slides/net/).

### ¿Aspose.Slides está disponible para otros lenguajes de programación?

Sí, Aspose.Slides está disponible para múltiples lenguajes de programación, incluido Java. Puede encontrar las bibliotecas adecuadas en el sitio web de Aspose.

### ¿Puedo extraer audio usando el mismo enfoque?

No, el ejemplo proporcionado es específicamente para extraer videos. Para extraer audio, deberá modificar el código para que funcione con fotogramas de audio.

### ¿Existe alguna tarifa de licencia por usar Aspose.Slides?

Sí, Aspose.Slides es un producto comercial. Puede encontrar información detallada sobre licencias y precios en el sitio web de Aspose.

### ¿Cómo accedo a las propiedades del video extraído?

 El`EmbeddedVideo` objeto obtenido de la`IVideoFrame` proporciona acceso a varias propiedades del video, como duración, resolución y más.