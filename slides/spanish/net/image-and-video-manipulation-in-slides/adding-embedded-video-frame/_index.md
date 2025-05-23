---
"description": "Mejore sus presentaciones con vídeos incrustados con Aspose.Slides para .NET. Siga nuestra guía paso a paso para una integración perfecta."
"linktitle": "Aspose.Slides&#58; Cómo añadir vídeos incrustados en presentaciones .NET"
"second_title": "API de procesamiento de PowerPoint Aspose.Slides .NET"
"title": "Aspose.Slides&#58; Cómo añadir vídeos incrustados en presentaciones .NET"
"url": "/es/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides: Cómo añadir vídeos incrustados en presentaciones .NET

## Introducción
En el dinámico mundo de las presentaciones, la integración de elementos multimedia puede mejorar significativamente la interacción. Aspose.Slides para .NET ofrece una potente solución para incorporar fotogramas de vídeo en las diapositivas de sus presentaciones. Este tutorial le guiará a través del proceso, detallando cada paso para garantizar una experiencia fluida.
## Prerrequisitos
Antes de sumergirnos en el tutorial, asegúrese de tener lo siguiente:
- Biblioteca Aspose.Slides para .NET: Descargue e instale la biblioteca desde [página de lanzamiento](https://releases.aspose.com/slides/net/).
- Contenido multimedia: tiene un archivo de video (por ejemplo, "Wildlife.mp4") que desea incrustar en su presentación.
## Importar espacios de nombres
Comience importando los espacios de nombres necesarios en su proyecto .NET:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Paso 1: Configurar directorios
Asegúrese de que su proyecto tenga los directorios necesarios para los archivos de documentos y multimedia:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// Crear directorio si aún no está presente.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## Paso 2: Crear una instancia de la clase de presentación
Cree una instancia de la clase Presentación para representar el archivo PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // Obtener la primera diapositiva
    ISlide sld = pres.Slides[0];
```
## Paso 3: Incrustar el vídeo dentro de la presentación
Utilice el siguiente código para insertar un vídeo dentro de la presentación:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Paso 4: Agregar fotograma de vídeo
Ahora, agrega un fotograma de vídeo a la diapositiva:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## Paso 5: Establecer las propiedades del vídeo
Establezca el vídeo en el fotograma de vídeo y configure el modo de reproducción y el volumen:
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## Paso 6: Guardar la presentación
Por último, guarde el archivo PPTX en el disco:
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Repita estos pasos para cada vídeo que desee incrustar en su presentación.
## Conclusión
¡Felicitaciones! Has añadido correctamente un fotograma de vídeo incrustado a tu presentación con Aspose.Slides para .NET. Esta función dinámica puede llevar tus presentaciones a un nuevo nivel, cautivando a tu audiencia con elementos multimedia integrados a la perfección en tus diapositivas.
## Preguntas frecuentes
### ¿Puedo incrustar vídeos en cualquier diapositiva de la presentación?
Sí, puedes elegir cualquier diapositiva modificando el índice en `pres.Slides[index]`.
### ¿Qué formatos de vídeo son compatibles?
Aspose.Slides admite una variedad de formatos de video, incluidos MP4, AVI y WMV.
### ¿Puedo personalizar el tamaño y la posición del fotograma del vídeo?
¡Por supuesto! Ajusta los parámetros en `AddVideoFrame(x, y, width, height, video)` según sea necesario.
### ¿Existe un límite en la cantidad de vídeos que puedo insertar?
La cantidad de videos incrustados generalmente está limitada por la capacidad de su software de presentación.
### ¿Cómo puedo buscar más ayuda o compartir mi experiencia?
Visita el [Foro de Aspose.Slides](https://forum.aspose.com/c/slides/11) Para apoyo y debates de la comunidad.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}