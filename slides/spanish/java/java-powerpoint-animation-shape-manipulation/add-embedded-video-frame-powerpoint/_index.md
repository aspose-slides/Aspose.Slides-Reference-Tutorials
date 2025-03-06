---
title: Agregar marco de video incrustado en PowerPoint
linktitle: Agregar marco de video incrustado en PowerPoint
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda cómo incrustar cuadros de video en PowerPoint usando Aspose.Slides para Java con este tutorial paso a paso. Mejore sus presentaciones fácilmente.
weight: 21
url: /es/java/java-powerpoint-animation-shape-manipulation/add-embedded-video-frame-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introducción
Agregar videos a sus presentaciones de PowerPoint puede hacerlas más atractivas e informativas. Con Aspose.Slides para Java, puede incrustar fácilmente videos directamente en sus diapositivas. En este tutorial, lo guiaremos a través del proceso paso a paso, asegurándonos de que comprenda cada parte del código y cómo funciona. Ya sea que sea un desarrollador experimentado o recién esté comenzando, esta guía lo ayudará a mejorar sus presentaciones con videos integrados.
## Requisitos previos
Antes de profundizar en el código, asegúrese de cumplir los siguientes requisitos previos:
1. Kit de desarrollo de Java (JDK): asegúrese de tener JDK instalado en su máquina.
2. Aspose.Slides para Java: descargue e instale la biblioteca Aspose.Slides para Java.
3. Entorno de desarrollo integrado (IDE): utilice un IDE como IntelliJ IDEA o Eclipse para una mejor experiencia de desarrollo.
4. Archivo de video: tenga un archivo de video que desee incrustar en su presentación de PowerPoint.
## Importar paquetes
Primero, deberá importar los paquetes necesarios para trabajar con Aspose.Slides. Estas importaciones lo ayudarán a administrar diapositivas, videos y archivos de presentación.
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## Paso 1: configure su entorno
Antes de comenzar a codificar, asegúrese de que su entorno esté configurado correctamente. Esto implica crear los directorios necesarios y preparar el archivo de vídeo.
```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
String videoDir = "Path to Your Video Directory";
String resultPath = "Path to Save Result" + "VideoFrame_out.pptx";
// Cree un directorio si aún no está presente.
boolean isExists = new File(dataDir).exists();
if (!isExists) new File(dataDir).mkdirs();
```
## Paso 2: crear una instancia de la clase de presentación
 Crear una instancia del`Presentation` clase. Esta clase representa su archivo de PowerPoint.
```java
// Crear una instancia de la clase de presentación que representa el PPTX
Presentation pres = new Presentation();
```
## Paso 3: obtenga la primera diapositiva
Accede a la primera diapositiva de la presentación donde incrustarás el vídeo.
```java
// Obtenga la primera diapositiva
ISlide sld = pres.getSlides().get_Item(0);
```
## Paso 4: agregue el video a la presentación
Incruste el archivo de video en la presentación. Asegúrese de que la ruta del video esté especificada correctamente.
```java
// Insertar vídeo dentro de la presentación
IVideo vid = pres.getVideos().addVideo(new FileInputStream(videoDir + "Wildlife.mp4"), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Paso 5: agregar un marco de video a la diapositiva
Cree un cuadro de video en la diapositiva y establezca sus dimensiones y posición.
```java
// Agregar marco de video
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 350, vid);
```
## Paso 6: Configurar las propiedades del cuadro de video
Configure el video en el cuadro de video y configure sus ajustes de reproducción, como el modo de reproducción y el volumen.
```java
// Establecer vídeo en fotograma de vídeo
vf.setEmbeddedVideo(vid);
// Establecer el modo de reproducción y el volumen del vídeo
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## Paso 7: guarde la presentación
Guarde la presentación con el vídeo incrustado en su directorio especificado.
```java
// Escriba el archivo PPTX en el disco
pres.save(resultPath, SaveFormat.Pptx);
```
## Paso 8: Limpiar recursos
Finalmente, deshazte del objeto de presentación para liberar recursos.
```java
// Desechar el objeto de presentación.
if (pres != null) pres.dispose();
```
## Conclusión
Incrustar un video en sus presentaciones de PowerPoint usando Aspose.Slides para Java es un proceso sencillo. Si sigue los pasos descritos en esta guía, podrá mejorar sus presentaciones con contenido de vídeo atractivo. Recuerde, la práctica hace la perfección, así que intente insertar diferentes videos y ajustar sus propiedades para ver cuál funciona mejor para sus necesidades.
## Preguntas frecuentes
### ¿Puedo insertar varios vídeos en una sola diapositiva?
Sí, puedes incrustar varios vídeos en una sola diapositiva añadiendo varios fotogramas de vídeo.
### ¿Cómo puedo controlar la reproducción del vídeo?
 Puede controlar la reproducción utilizando el`setPlayMode` y`setVolume` métodos de la`IVideoFrame` clase.
### ¿Qué formatos de vídeo son compatibles con Aspose.Slides?
Aspose.Slides admite varios formatos de video, incluidos MP4, AVI y WMV.
### ¿Necesito una licencia para usar Aspose.Slides?
Sí, necesita una licencia válida para utilizar Aspose.Slides. Puede obtener una licencia temporal para evaluación.
### ¿Puedo personalizar el tamaño y la posición del fotograma del vídeo?
Sí, puede personalizar el tamaño y la posición configurando los parámetros apropiados al agregar el cuadro de video.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
