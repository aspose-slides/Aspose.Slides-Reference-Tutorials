---
tiitle: Aspose.Slides agregar videos incrustados en presentaciones .NET
linktiitle: Aspose.Slides agregar videos incrustados en presentaciones .NET
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Mejore sus presentaciones con videos incrustados usando Aspose.Slides para .NET. Siga nuestra guía paso a paso para una integración perfecta.
type: docs
weight: 19
url: /es/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/
---
## Introducción
En el dinámico mundo de las presentaciones, la integración de elementos multimedia puede mejorar significativamente la participación. Aspose.Slides para .NET proporciona una potente solución para incorporar fotogramas de vídeo incrustados en las diapositivas de su presentación. Este tutorial lo guiará a través del proceso, desglosando cada paso para garantizar una experiencia perfecta.
## Requisitos previos
Antes de sumergirnos en el tutorial, asegúrese de tener lo siguiente:
-  Aspose.Slides para la biblioteca .NET: descargue e instale la biblioteca desde[página de lanzamiento](https://releases.aspose.com/slides/net/).
- Contenido multimedia: tenga un archivo de vídeo (por ejemplo, "Wildlife.mp4") que desee incrustar en su presentación.
## Importar espacios de nombres
Comience importando los espacios de nombres necesarios en su proyecto .NET:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Paso 1: configurar directorios
Asegúrese de que su proyecto tenga los directorios necesarios para documentos y archivos multimedia:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// Cree un directorio si aún no está presente.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## Paso 2: crear una instancia de la clase de presentación
Cree una instancia de la clase Presentación para representar el archivo PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // Obtenga la primera diapositiva
    ISlide sld = pres.Slides[0];
```
## Paso 3: incrustar video dentro de la presentación
Utilice el siguiente código para insertar un vídeo dentro de la presentación:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Paso 4: agregar marco de video
Ahora, agregue un cuadro de video a la diapositiva:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## Paso 5: configurar las propiedades del video
Configure el video en el cuadro de video y configure el modo de reproducción y el volumen:
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## Paso 6: guarde la presentación
Finalmente, guarde el archivo PPTX en el disco:
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Repita estos pasos para cada video que desee insertar en su presentación.
## Conclusión
¡Felicidades! Ha agregado con éxito un fotograma de video incrustado a su presentación usando Aspose.Slides para .NET. Esta característica dinámica puede elevar sus presentaciones a nuevas alturas, cautivando a su audiencia con elementos multimedia perfectamente integrados en sus diapositivas.
## Preguntas frecuentes
### ¿Puedo incrustar vídeos en cualquier diapositiva de la presentación?
 Sí, puedes elegir cualquier diapositiva modificando el índice en`pres.Slides[index]`.
### ¿Qué formatos de vídeo son compatibles?
Aspose.Slides admite una variedad de formatos de video, incluidos MP4, AVI y WMV.
### ¿Puedo personalizar el tamaño y la posición del fotograma del vídeo?
 ¡Absolutamente! Ajuste los parámetros en`AddVideoFrame(x, y, width, height, video)` según sea necesario.
### ¿Existe un límite en la cantidad de videos que puedo insertar?
La cantidad de videos incrustados generalmente está limitada por la capacidad de su software de presentación.
### ¿Cómo puedo buscar más ayuda o compartir mi experiencia?
 Visita el[Foro Aspose.Slides](https://forum.aspose.com/c/slides/11) para apoyo y debates de la comunidad.