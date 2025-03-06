---
title: Agregar desplazamiento de estiramiento para relleno de imágenes en presentaciones de PowerPoint
linktitle: Agregar desplazamiento de estiramiento para relleno de imágenes en diapositivas
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda cómo mejorar las presentaciones de PowerPoint con Aspose.Slides para .NET. Siga una guía paso a paso para agregar un desplazamiento de estiramiento para el relleno de la imagen.
weight: 18
url: /es/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introducción
En el dinámico mundo de las presentaciones, los elementos visuales desempeñan un papel fundamental a la hora de captar la atención de la audiencia. Aspose.Slides para .NET permite a los desarrolladores mejorar sus presentaciones de PowerPoint proporcionando un sólido conjunto de funciones. Una de esas características es la capacidad de agregar un desplazamiento de estiramiento para el relleno de la imagen, lo que permite diapositivas creativas y visualmente atractivas.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
1.  Aspose.Slides para la biblioteca .NET: descargue e instale la biblioteca desde[Aspose.Slides para la documentación de .NET](https://reference.aspose.com/slides/net/).
2. Entorno de desarrollo: asegúrese de tener configurado un entorno de desarrollo .NET que funcione.
Ahora comencemos con la guía paso a paso.
## Importar espacios de nombres
En primer lugar, importe los espacios de nombres necesarios para aprovechar la funcionalidad Aspose.Slides dentro de su aplicación .NET.
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Paso 1: configura tu proyecto
Cree un nuevo proyecto .NET en su entorno de desarrollo preferido. Asegúrese de que se haga referencia correctamente a Aspose.Slides para .NET.
## Paso 2: Inicializar la clase de presentación
 Instanciar el`Presentation` clase para representar el archivo de PowerPoint.
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Tu código va aquí
}
```
## Paso 3: obtenga la primera diapositiva
Recupere la primera diapositiva de la presentación para trabajar.
```csharp
ISlide sld = pres.Slides[0];
```
## Paso 4: crear una instancia de la clase ImageEx
 Crear una instancia del`ImageEx`clase para manejar la imagen que desea agregar a la diapositiva.
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx = pres.Images.AddImage(img);
```
## Paso 5: agregar marco de imagen
 Utilice el`AddPictureFrame` Método para agregar un marco de imagen a la diapositiva. Especifique las dimensiones y la posición del marco.
```csharp
sld.Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 150, imgx.Width, imgx.Height, imgx);
```
## Paso 6: guarde la presentación
Guarde la presentación modificada en el disco.
```csharp
pres.Save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```
¡Eso es todo! Ha agregado con éxito un desplazamiento de extensión para diapositivas de relleno de imágenes usando Aspose.Slides para .NET.
## Conclusión
Mejorar sus presentaciones de PowerPoint ahora es más fácil que nunca con Aspose.Slides para .NET. Siguiendo este tutorial, habrá aprendido cómo incorporar el desplazamiento de estiramiento para el relleno de imágenes, aportando un nuevo nivel de creatividad a sus diapositivas.
## Preguntas frecuentes
### ¿Puedo usar Aspose.Slides para .NET en mis aplicaciones web?
Sí, Aspose.Slides para .NET es adecuado tanto para aplicaciones web como de escritorio.
### ¿Hay una prueba gratuita disponible para Aspose.Slides para .NET?
 Sí, puedes descargar una prueba gratuita desde[aquí](https://releases.aspose.com/).
### ¿Cómo puedo obtener soporte para Aspose.Slides para .NET?
 Visita el[Foro Aspose.Slides](https://forum.aspose.com/c/slides/11) para el apoyo de la comunidad.
### ¿Dónde puedo encontrar la documentación completa de Aspose.Slides para .NET?
 Referirse a[documentación](https://reference.aspose.com/slides/net/) para obtener información detallada.
### ¿Puedo comprar Aspose.Slides para .NET?
 Sí, puedes comprar el producto.[aquí](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
