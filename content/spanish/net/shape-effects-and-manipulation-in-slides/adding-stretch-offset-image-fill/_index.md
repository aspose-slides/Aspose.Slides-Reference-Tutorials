---
title: Agregar desplazamiento de estiramiento para relleno de imagen en diapositivas con Aspose.Slides
linktitle: Agregar desplazamiento de estiramiento para relleno de imágenes en diapositivas
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda cómo mejorar las diapositivas de su presentación usando Aspose.Slides para .NET. Esta guía paso a paso cubre cómo agregar un desplazamiento de estiramiento para el relleno de la imagen, crear imágenes dinámicas y optimizar el diseño.
type: docs
weight: 18
url: /es/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/
---

En las presentaciones modernas, los elementos visuales desempeñan un papel crucial a la hora de transmitir mensajes de forma eficaz. Aspose.Slides, una potente API para trabajar con archivos de presentación en .NET, ofrece una función llamada "Stretch Offset" que le permite controlar con precisión cómo se rellenan las imágenes dentro de las formas. Este artículo lo guiará a través del proceso de agregar desplazamiento de estiramiento para el relleno de imágenes en diapositivas de presentación usando Aspose.Slides para .NET.

## Introducción al desplazamiento de estiramiento

Stretch Offset es una técnica valiosa cuando necesita personalizar cómo se muestran las imágenes dentro de las formas. Le permite controlar la posición y alineación de la imagen dentro de una forma, lo que permite diseños de diapositivas creativos y visualmente atractivos. Al utilizar la API Aspose.Slides, puede implementar mediante programación el desplazamiento de estiramiento y darle vida a sus presentaciones.

## Configurar su entorno de desarrollo

 Antes de profundizar en la implementación, asegúrese de tener Aspose.Slides para .NET instalado en su entorno de desarrollo. Puede descargarlo desde el sitio web de Aspose.[enlace de descarga](https://releases.aspose.com/slides/net/)Una vez descargado, siga las instrucciones de instalación para configurar la API para su proyecto.

## Agregar una imagen a una diapositiva

Para demostrar la función de desplazamiento de estiramiento, comencemos agregando una imagen a una diapositiva usando Aspose.Slides. El siguiente fragmento de código muestra cómo lograr esto:

```csharp
// Crear una instancia de un objeto de presentación
Presentation presentation = new Presentation();

// Accede a la primera diapositiva
ISlide slide = presentation.Slides[0];

// Definir la ruta del archivo de imagen
string imagePath = "path_to_your_image.jpg";

// Agregar una imagen a la diapositiva
byte[] imageBytes = File.ReadAllBytes(imagePath);
IPictureFillFormat pictureFill = slide.Shapes.AddPictureFrame(ShapeType.Rectangle, 100, 100, 400, 300).FillFormat.PictureFillFormat;
pictureFill.Picture.Image = presentation.Images.AddImage(imageBytes);

// guardar la presentación
presentation.Save("output.pptx", SaveFormat.Pptx);
```

## Aplicar compensación de estiramiento a imágenes

 Ahora que tenemos una imagen agregada a una diapositiva, exploremos cómo aplicarle un desplazamiento de estiramiento. El desplazamiento del estiramiento está controlado por dos propiedades:`StretchX` y`StretchY`. Estas propiedades determinan el desplazamiento de la imagen dentro de la forma horizontal y verticalmente, respectivamente.

Así es como puedes implementar el desplazamiento de estiramiento usando Aspose.Slides:

```csharp
// Accede al formato de relleno de imagen.
IPictureFillFormat pictureFill = slide.Shapes[0].FillFormat.PictureFillFormat;

// Aplicar compensación de estiramiento
pictureFill.StretchX = 0.5; // Desplazamiento horizontal del 50%
pictureFill.StretchY = -0.2; // Desplazamiento vertical de -20%
```

En este ejemplo, hemos establecido un desplazamiento horizontal del 50 % y un desplazamiento vertical del -20 %. El valor negativo para el desplazamiento vertical mueve la imagen hacia arriba dentro de la forma.

## Ajustar los valores de compensación de estiramiento

 Encontrar los valores de compensación de estiramiento perfectos puede requerir algo de prueba y error para lograr el efecto visual deseado. Ajustar los valores de`StretchX` y`StretchY` para adaptarse a sus preferencias de diseño y alineación. Experimente con valores positivos y negativos para ver cómo cambia la ubicación de la imagen.

## Usar compensación de estiramiento con diferentes formas

 El desplazamiento de estiramiento se puede aplicar a varios tipos de formas, incluidos rectángulos, elipses y más. El método de acceso a la`PictureFillFormat` permanece consistente en todas las formas. Siéntete libre de explorar y experimentar con diferentes formas para crear composiciones de diapositivas únicas.

## Técnicas y consejos avanzados

- Combine el desplazamiento elástico con otras funciones de formato para diseños complejos.
- Utilice el desplazamiento de estiramiento para enfatizar partes específicas de una imagen dentro de una forma.
-  Utilice el`PictureFillFormat.TileAsTexture`propiedad para colocar imágenes en mosaico dentro de formas en lugar de estirarlas.

## Conclusión

La incorporación de desplazamiento elástico para el relleno de imágenes en las diapositivas de presentación utilizando Aspose.Slides abre un mundo de posibilidades creativas. Con un control preciso sobre el posicionamiento de la imagen, puede mejorar el impacto visual de sus presentaciones. Si sigue los pasos descritos en este artículo, aprenderá cómo aprovechar esta función de manera efectiva.

## Preguntas frecuentes

### ¿Cómo puedo descargar Aspose.Slides para .NET?

 Puede descargar Aspose.Slides para .NET desde el sitio web de Aspose[enlace de descarga](https://releases.aspose.com/slides/net/).

### ¿Puedo utilizar el desplazamiento estirado con cualquier tipo de imagen?

Sí, el desplazamiento extendido se puede aplicar a imágenes de varios formatos, incluidos JPG, PNG y más.

###  ¿Qué pasa si configuro ambos?`StretchX` and `StretchY` to the same value?

Establecer ambas propiedades en el mismo valor mantiene la relación de aspecto de la imagen mientras cambia su posición dentro de la forma.

### ¿El desplazamiento de estiramiento es compatible con las animaciones?

Sí, el desplazamiento extendido funciona perfectamente con animaciones de diapositivas, lo que le permite crear presentaciones dinámicas.

### ¿Cómo puedo acceder a opciones avanzadas de compensación de estiramiento?

Explore la documentación de Aspose.Slides para obtener información detallada sobre técnicas y propiedades avanzadas de compensación de estiramiento.