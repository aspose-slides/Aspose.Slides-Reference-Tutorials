---
"description": "Aprenda a extraer vídeos de diapositivas de PowerPoint con Aspose.Slides para .NET. Esta guía paso a paso le simplifica el proceso."
"linktitle": "Extraer vídeo de la diapositiva"
"second_title": "API de procesamiento de PowerPoint Aspose.Slides .NET"
"title": "Cómo extraer vídeo de una diapositiva con Aspose.Slides para .NET"
"url": "/es/net/audio-and-video-extraction/extract-video/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Cómo extraer vídeo de una diapositiva con Aspose.Slides para .NET


Aspose.Slides para .NET es una potente biblioteca que permite trabajar con presentaciones de PowerPoint en un entorno .NET. Una de sus útiles funciones es la posibilidad de extraer vídeos de las diapositivas. En esta guía paso a paso, le mostraremos cómo extraer un vídeo de una diapositiva de PowerPoint con Aspose.Slides para .NET.

## Prerrequisitos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

- Aspose.Slides para .NET: Necesita tener instalado Aspose.Slides para .NET. Puede obtenerlo en [sitio web](https://purchase.aspose.com/buy).

- Una presentación de PowerPoint: prepare una presentación de PowerPoint (por ejemplo, Video.pptx) que contenga el vídeo que desea extraer.

## Importar espacios de nombres

Necesita importar los espacios de nombres necesarios para trabajar con Aspose.Slides para .NET. A continuación, le mostramos cómo hacerlo:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

Ahora, vamos a dividir el proceso de extracción de un vídeo de una diapositiva en varios pasos.

## Paso 1: Establecer el directorio del documento

```csharp
string dataDir = "Your Document Directory";
```

Reemplazar `"Your Document Directory"` con la ruta al directorio donde se encuentra su presentación de PowerPoint.

## Paso 2: Cargar la presentación

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

Este código inicializa un objeto Presentación, que representa su archivo de presentación de PowerPoint.

## Paso 3: Iterar a través de diapositivas y formas

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

Aquí, recorremos cada diapositiva de la presentación y luego iteramos a través de las formas en la primera diapositiva (modificándolas según sea necesario).

## Paso 4: Comprueba si la forma es un fotograma de vídeo

```csharp
if (shape is VideoFrame)
{
    IVideoFrame vf = shape as IVideoFrame;
    String type = vf.EmbeddedVideo.ContentType;
```

Este paso verifica si la forma de la diapositiva es un fotograma de vídeo.

## Paso 5: Extraer datos de vídeo

```csharp
int ss = type.LastIndexOf('/');
type = type.Remove(0, type.LastIndexOf('/') + 1);
Byte[] buffer = vf.EmbeddedVideo.BinaryData;
```

Este código extrae información sobre el vídeo, incluido su tipo de contenido y datos binarios.

## Paso 6: Guardar el vídeo

```csharp
using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

Finalmente, este paso guarda el vídeo en un nuevo archivo en el directorio especificado.

Una vez que haya completado estos pasos, habrá extraído con éxito un video de una diapositiva de PowerPoint usando Aspose.Slides para .NET.

## Conclusión

Aspose.Slides para .NET simplifica el trabajo con presentaciones de PowerPoint, permitiéndole realizar tareas como extraer vídeos de diapositivas con facilidad. Siguiendo esta guía paso a paso y utilizando la biblioteca Aspose.Slides, podrá mejorar sus aplicaciones .NET con potentes funciones de PowerPoint.

## Preguntas frecuentes (FAQ)

### ¿Qué es Aspose.Slides para .NET?
Aspose.Slides para .NET es una biblioteca que permite que las aplicaciones .NET trabajen con presentaciones de PowerPoint, incluida la creación, edición y extracción de contenido.

### ¿Dónde puedo encontrar la documentación de Aspose.Slides para .NET?
Puede encontrar la documentación [aquí](https://reference.aspose.com/slides/net/).

### ¿Aspose.Slides para .NET está disponible para una prueba gratuita?
Sí, puedes obtener una versión de prueba gratuita desde [aquí](https://releases.aspose.com/).

### ¿Cómo puedo obtener una licencia temporal de Aspose.Slides para .NET?
Puede solicitar una licencia temporal a [este enlace](https://purchase.aspose.com/temporary-license/).

### ¿Dónde puedo obtener soporte para Aspose.Slides para .NET?
Puede encontrar ayuda en el [Foro de Aspose.Slides](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}