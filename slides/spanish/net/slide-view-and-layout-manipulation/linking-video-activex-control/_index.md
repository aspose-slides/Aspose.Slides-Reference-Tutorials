---
"description": "Aprenda a vincular vídeos a diapositivas de PowerPoint con Aspose.Slides para .NET. Esta guía paso a paso incluye el código fuente y consejos para crear presentaciones interactivas y atractivas con vídeos vinculados."
"linktitle": "Vincular vídeo mediante el control ActiveX"
"second_title": "API de procesamiento de PowerPoint Aspose.Slides .NET"
"title": "Vincular vídeo mediante un control ActiveX en PowerPoint"
"url": "/es/net/slide-view-and-layout-manipulation/linking-video-activex-control/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Vincular vídeo mediante un control ActiveX en PowerPoint

Cómo vincular un vídeo mediante un control ActiveX en una presentación usando Aspose.Slides para .NET

En Aspose.Slides para .NET, puede vincular un vídeo a una diapositiva de una presentación mediante programación mediante el control ActiveX. Esto le permite crear presentaciones interactivas donde el contenido del vídeo se puede reproducir directamente dentro de la diapositiva. En esta guía paso a paso, le guiaremos por el proceso de vincular un vídeo a una diapositiva de una presentación con Aspose.Slides para .NET.

## Prerrequisitos:
- Visual Studio (o cualquier otro entorno de desarrollo .NET)
- Biblioteca Aspose.Slides para .NET. Puede descargarla desde [aquí](https://releases.aspose.com/slides/net/).

## Paso 1: Crear un nuevo proyecto
Cree un nuevo proyecto en su entorno de desarrollo .NET preferido (por ejemplo, Visual Studio) y agregue referencias a la biblioteca Aspose.Slides para .NET.

## Paso 2: Importar los espacios de nombres necesarios
En su proyecto, importe los espacios de nombres necesarios para trabajar con Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## Paso 3: Cargar la presentación
Cargue la presentación de PowerPoint donde desea agregar el vídeo vinculado:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Tu código para agregar el video vinculado irá aquí
}
```

## Paso 4: Agregar control ActiveX
Crear una instancia de la `IOleObjectFrame` Interfaz para agregar el control ActiveX a la diapositiva:

```csharp
ISlide slide = presentation.Slides[0]; // Elige la diapositiva donde quieres agregar el vídeo
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

En el código anterior, añadimos a la diapositiva un marco de control ActiveX de 640x480. Especificamos el ProgID del control ActiveX ShockwaveFlash, que se utiliza habitualmente para incrustar vídeos.

## Paso 5: Establecer las propiedades del control ActiveX
Establezca las propiedades del control ActiveX para especificar la fuente de vídeo vinculada:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // Reemplazar con la ruta del archivo de video real
oleObjectFrame.AlternativeText = "Linked Video";
```

Reemplazar `"YourVideoPathHere"` con la ruta real a su archivo de vídeo. El `AlternativeText` La propiedad proporciona una descripción del vídeo vinculado.

## Paso 6: Guardar la presentación
Guardar la presentación modificada:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## Preguntas frecuentes:

### ¿Cómo puedo especificar el tamaño y la posición del vídeo vinculado en la diapositiva?
Puede ajustar las dimensiones y la posición del marco de control ActiveX utilizando los parámetros de la `AddOleObjectFrame` método. Los cuatro argumentos numéricos representan las coordenadas X e Y de la esquina superior izquierda y el ancho y la altura del marco, respectivamente.

### ¿Puedo vincular vídeos de diferentes formatos utilizando este enfoque?
Sí, puedes vincular vídeos de varios formatos siempre que tengas el control ActiveX adecuado para ese formato. Por ejemplo, el control ActiveX ShockwaveFlash que se usa en esta guía es compatible con vídeos Flash (SWF). Para otros formatos, podrías necesitar usar diferentes ProgID.

### ¿Existe un límite para el tamaño del vídeo vinculado?
El tamaño del video vinculado podría afectar el tamaño general y el rendimiento de la presentación. Se recomienda optimizar los videos para su reproducción web antes de vincularlos a la presentación.

### Conclusión:
Siguiendo los pasos de esta guía, podrá vincular fácilmente un vídeo mediante un control ActiveX en una presentación con Aspose.Slides para .NET. Esta función le permite crear presentaciones atractivas e interactivas que incorporan contenido multimedia de forma fluida.

Para obtener más detalles y opciones avanzadas, puede consultar la [Documentación de Aspose.Slides para .NET](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}