---
title: Tutorial para agregar marcos de fotos con Aspose.Slides .NET
linktitle: Agregar marcos de fotos con altura de escala relativa en Aspose.Slides
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda a agregar marcos de cuadros con altura de escala relativa en Aspose.Slides para .NET. Siga esta guía paso a paso para realizar presentaciones perfectas.
weight: 17
url: /es/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introducción
Aspose.Slides para .NET es una poderosa biblioteca que permite a los desarrolladores crear, manipular y convertir presentaciones de PowerPoint en sus aplicaciones .NET sin esfuerzo. En este tutorial, profundizaremos en el proceso de agregar marcos de fotos con altura de escala relativa usando Aspose.Slides para .NET. Siga esta guía paso a paso para mejorar sus habilidades de creación de presentaciones.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
- Conocimientos básicos del lenguaje de programación C#.
- Visual Studio o cualquier otro entorno de desarrollo C# preferido instalado.
- Biblioteca Aspose.Slides para .NET agregada a su proyecto.
## Importar espacios de nombres
Comience importando los espacios de nombres necesarios en su código C#. Este paso garantiza que tenga acceso a las clases y funcionalidades proporcionadas por la biblioteca Aspose.Slides.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Paso 1: configura tu proyecto
Comience creando un nuevo proyecto de C# en su entorno de desarrollo preferido. Asegúrese de agregar la biblioteca Aspose.Slides para .NET a su proyecto haciendo referencia a ella.
## Paso 2: cargar la presentación y la imagen
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    //Cargar imagen para agregar a la colección de imágenes de presentación
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // ...
}
```
En este paso, creamos un nuevo objeto de presentación y cargamos la imagen que queremos agregar a la presentación.
## Paso 3: agregue un marco de imagen a la diapositiva
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
Ahora, agregue un marco de imagen a la primera diapositiva de la presentación. Ajuste los parámetros como el tipo de forma, la posición y las dimensiones según sus requisitos.
## Paso 4: Establecer el ancho y alto de la escala relativa
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
Establezca la altura y el ancho de escala relativos del marco de la imagen para lograr el efecto de escala deseado.
## Paso 5: guardar la presentación
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
Finalmente, guarde la presentación con el marco de imagen agregado en el formato de salida especificado.
## Conclusión
¡Felicidades! Ha aprendido con éxito cómo agregar marcos de imágenes con altura de escala relativa usando Aspose.Slides para .NET. Experimente con diferentes imágenes, posiciones y escalas para crear presentaciones visualmente atractivas adaptadas a sus necesidades.
## Preguntas frecuentes
### ¿Puedo usar Aspose.Slides para .NET con otros lenguajes de programación?
Aspose.Slides admite principalmente lenguajes .NET, pero puede explorar otros productos Aspose para comprobar su compatibilidad con diferentes plataformas.
### ¿Dónde puedo encontrar documentación detallada para Aspose.Slides para .NET?
 Referirse a[documentación](https://reference.aspose.com/slides/net/) para obtener información completa y ejemplos.
### ¿Hay una prueba gratuita disponible para Aspose.Slides para .NET?
 Sí, puedes conseguir un[prueba gratis](https://releases.aspose.com/) evaluar las capacidades de la biblioteca.
### ¿Cómo puedo obtener soporte para Aspose.Slides para .NET?
 Visita el[Foro Aspose.Slides](https://forum.aspose.com/c/slides/11) buscar ayuda de la comunidad y de los expertos de Aspose.
### ¿Dónde puedo comprar Aspose.Slides para .NET?
 Puede comprar Aspose.Slides para .NET desde el[pagina de compra](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
