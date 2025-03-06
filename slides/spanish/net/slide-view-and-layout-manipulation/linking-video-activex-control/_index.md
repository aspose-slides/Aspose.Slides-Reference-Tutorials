---
title: Vincular vídeo a través del control ActiveX en PowerPoint
linktitle: Vinculación de vídeo a través del control ActiveX
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda cómo vincular videos a diapositivas de PowerPoint usando Aspose.Slides para .NET. Esta guía paso a paso incluye código fuente y consejos para crear presentaciones interactivas y atractivas con vídeos vinculados.
weight: 12
url: /es/net/slide-view-and-layout-manipulation/linking-video-activex-control/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

Vincular un video a través del control ActiveX en una presentación usando Aspose.Slides para .NET

En Aspose.Slides para .NET, puede vincular mediante programación un video a una diapositiva de presentación usando el control ActiveX. Esto le permite crear presentaciones interactivas donde el contenido del video se puede reproducir directamente dentro de la diapositiva. En esta guía paso a paso, lo guiaremos a través del proceso de vincular un video a una diapositiva de presentación usando Aspose.Slides para .NET.

## Requisitos previos:
- Visual Studio (o cualquier otro entorno de desarrollo .NET)
-  Aspose.Slides para la biblioteca .NET. Puedes descargarlo desde[aquí](https://releases.aspose.com/slides/net/).

## Paso 1: crear un nuevo proyecto
Cree un nuevo proyecto en su entorno de desarrollo .NET preferido (por ejemplo, Visual Studio) y agregue referencias a la biblioteca Aspose.Slides para .NET.

## Paso 2: importar los espacios de nombres necesarios
En su proyecto, importe los espacios de nombres necesarios para trabajar con Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## Paso 3: cargar la presentación
Cargue la presentación de PowerPoint donde desea agregar el video vinculado:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Su código para agregar el video vinculado irá aquí
}
```

## Paso 4: agregue el control ActiveX
 Crear una instancia del`IOleObjectFrame` interfaz para agregar el control ActiveX a la diapositiva:

```csharp
ISlide slide = presentation.Slides[0]; // Elige la diapositiva donde quieres agregar el video.
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

En el código anterior, agregamos un marco de control ActiveX de dimensiones 640x480 a la diapositiva. Estamos especificando el ProgID para el control ShockwaveFlash ActiveX, que se usa comúnmente para incrustar videos.

## Paso 5: establecer las propiedades del control ActiveX
Configure las propiedades del control ActiveX para especificar la fuente de video vinculada:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // Reemplazar con la ruta real del archivo de video
oleObjectFrame.AlternativeText = "Linked Video";
```

 Reemplazar`"YourVideoPathHere"` con la ruta real a su archivo de video. El`AlternativeText` La propiedad proporciona una descripción del vídeo vinculado.

## Paso 6: guardar la presentación
Guarde la presentación modificada:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## Preguntas frecuentes:

### ¿Cómo puedo especificar el tamaño y la posición del vídeo vinculado en la diapositiva?
Puede ajustar las dimensiones y la posición del marco de control ActiveX utilizando los parámetros del`AddOleObjectFrame` método. Los cuatro argumentos numéricos representan las coordenadas X e Y de la esquina superior izquierda y el ancho y alto del marco, respectivamente.

### ¿Puedo vincular vídeos de diferentes formatos usando este enfoque?
Sí, puedes vincular vídeos de varios formatos siempre que esté disponible el control ActiveX adecuado para ese formato. Por ejemplo, el control ShockwaveFlash ActiveX utilizado en esta guía es adecuado para vídeos Flash (SWF). Para otros formatos, es posible que necesite utilizar ProgID diferentes.

### ¿Existe un límite para el tamaño del vídeo vinculado?
El tamaño del vídeo vinculado puede afectar el tamaño general y el rendimiento de su presentación. Se recomienda optimizar sus videos para la reproducción web antes de vincularlos a la presentación.

### Conclusión:
Si sigue los pasos descritos en esta guía, puede vincular fácilmente un vídeo a través del control ActiveX en una presentación utilizando Aspose.Slides para .NET. Esta función le permite crear presentaciones atractivas e interactivas que incorporan contenido multimedia a la perfección.

 Para obtener más detalles y opciones avanzadas, puede consultar el[Aspose.Slides para la documentación de .NET](https://reference.aspose.com/slides/net/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
