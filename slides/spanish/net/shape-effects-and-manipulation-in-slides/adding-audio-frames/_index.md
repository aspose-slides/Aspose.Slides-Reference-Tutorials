---
title: Agregar marcos de audio a las diapositivas de la presentación usando Aspose.Slides
linktitle: Agregar marcos de audio a las diapositivas de la presentación usando Aspose.Slides
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: ¡Mejore las presentaciones con Aspose.Slides para .NET! Aprenda a agregar cuadros de audio sin problemas, atrayendo a su audiencia como nunca antes.
weight: 14
url: /es/net/shape-effects-and-manipulation-in-slides/adding-audio-frames/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introducción
En el dinámico mundo de las presentaciones, la incorporación de elementos de audio puede mejorar significativamente la experiencia general de su audiencia. Aspose.Slides para .NET permite a los desarrolladores integrar perfectamente fotogramas de audio en las diapositivas de la presentación, añadiendo una nueva capa de participación e interactividad. Esta guía paso a paso lo guiará a través del proceso de agregar marcos de audio a las diapositivas de una presentación usando Aspose.Slides para .NET.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
1.  Biblioteca Aspose.Slides para .NET: descargue e instale la biblioteca Aspose.Slides para .NET desde[enlace de descarga](https://releases.aspose.com/slides/net/).
2. Entorno de desarrollo: asegúrese de tener un entorno de desarrollo funcional para .NET, como Visual Studio.
3. Directorio de documentos: cree un directorio donde almacenará sus documentos y anote la ruta.
## Importar espacios de nombres
En su aplicación .NET, comience importando los espacios de nombres necesarios para acceder a la funcionalidad Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Paso 1: crear presentación y diapositiva
```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation())
{
    ISlide sld = pres.Slides[0];
    // Su código para la creación de diapositivas va aquí
}
```
## Paso 2: cargar el archivo de audio
```csharp
FileStream fstr = new FileStream(dataDir + "sampleaudio.wav", FileMode.Open, FileAccess.Read);
```
## Paso 3: agregar marco de audio
```csharp
IAudioFrame audioFrame = sld.Shapes.AddAudioFrameEmbedded(50, 150, 100, 100, fstr);
```
## Paso 4: configurar las propiedades de audio
```csharp
audioFrame.PlayAcrossSlides = true;
audioFrame.RewindAudio = true;
audioFrame.PlayMode = AudioPlayModePreset.Auto;
audioFrame.Volume = AudioVolumeMode.Loud;
```
## Paso 5: guardar la presentación
```csharp
pres.Save(dataDir + "AudioFrameEmbed_out.pptx", SaveFormat.Pptx);
```
Si sigue estos pasos, habrá integrado con éxito fotogramas de audio en su presentación utilizando Aspose.Slides para .NET.
## Conclusión
La incorporación de elementos de audio en sus presentaciones mejora la experiencia general del espectador, haciendo que su contenido sea más dinámico y atractivo. Aspose.Slides para .NET simplifica este proceso, permitiendo a los desarrolladores integrar perfectamente cuadros de audio con solo unas pocas líneas de código.
## Preguntas frecuentes
### ¿Aspose.Slides para .NET es compatible con diferentes formatos de audio?
Aspose.Slides para .NET admite varios formatos de audio, incluidos WAV, MP3 y más. Consulte la documentación para obtener una lista completa.
### ¿Puedo controlar la configuración de reproducción del cuadro de audio agregado?
Sí, Aspose.Slides brinda flexibilidad para configurar ajustes de reproducción como volumen, modo de reproducción y más.
### ¿Existe una versión de prueba disponible para Aspose.Slides para .NET?
 Sí, puede explorar las características de Aspose.Slides para .NET con el[prueba gratis](https://releases.aspose.com/).
### ¿Dónde puedo encontrar soporte para Aspose.Slides para .NET?
 Visita el[Foro Aspose.Slides](https://forum.aspose.com/c/slides/11) buscar ayuda y relacionarse con la comunidad.
### ¿Cómo compro Aspose.Slides para .NET?
 Puedes adquirir la biblioteca en[tienda aspose](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
