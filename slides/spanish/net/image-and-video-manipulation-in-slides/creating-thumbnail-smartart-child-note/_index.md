---
title: Creación de miniaturas para notas secundarias SmartArt en Aspose.Slides
linktitle: Creación de miniaturas para notas secundarias SmartArt en Aspose.Slides
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda a crear miniaturas cautivadoras de notas secundarias SmartArt utilizando Aspose.Slides para .NET. ¡Mejora tus presentaciones con imágenes dinámicas!
type: docs
weight: 15
url: /es/net/image-and-video-manipulation-in-slides/creating-thumbnail-smartart-child-note/
---
## Introducción
En el ámbito de las presentaciones dinámicas, Aspose.Slides para .NET se destaca como una herramienta poderosa que brinda a los desarrolladores la capacidad de manipular y mejorar presentaciones de PowerPoint mediante programación. Una característica interesante es la capacidad de generar miniaturas para SmartArt Child Notes, agregando una capa de atractivo visual a sus presentaciones. Esta guía paso a paso lo guiará a través del proceso de creación de miniaturas para SmartArt Child Notes usando Aspose.Slides para .NET.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
-  Aspose.Slides para .NET: asegúrese de tener la biblioteca Aspose.Slides integrada en su proyecto .NET. Si no, descárgalo del[página de lanzamientos](https://releases.aspose.com/slides/net/).
- Entorno de desarrollo: configure un entorno de desarrollo .NET que funcione y tenga conocimientos básicos de programación en C#.
- Presentación de muestra: cree u obtenga una presentación de PowerPoint que contenga SmartArt con notas secundarias para realizar pruebas.
## Importar espacios de nombres
Comience importando los espacios de nombres necesarios a su proyecto C#. Estos espacios de nombres brindan acceso a las clases y métodos necesarios para trabajar con Aspose.Slides.
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides.SmartArt;
using Aspose.Slides;
```
## Paso 1: crear una instancia de la clase de presentación
 Comience por crear una instancia del`Presentation` clase, que representa el archivo PPTX con el que trabajará.
```csharp
string dataDir = "Your Documents Directory";
Presentation pres = new Presentation();
```
## Paso 2: agregue SmartArt
 Ahora, agregue SmartArt a una diapositiva dentro de la presentación. En este ejemplo, estamos usando el`BasicCycle` disposición.
```csharp
ISmartArt smart = pres.Slides[0].Shapes.AddSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Paso 3: obtener la referencia del nodo
Para trabajar con un nodo específico en el SmartArt, obtenga su referencia usando su índice.
```csharp
ISmartArtNode node = smart.Nodes[1];
```
## Paso 4: obtener miniatura
Recupere la imagen en miniatura de la nota secundaria dentro del nodo SmartArt.
```csharp
Bitmap bmp = node.Shapes[0].GetThumbnail();
```
## Paso 5: guardar miniatura
Guarde la imagen en miniatura generada en un directorio específico.
```csharp
bmp.Save(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg", ImageFormat.Jpeg);
```
Repita estos pasos para cada nodo SmartArt de su presentación, personalizando el diseño y los estilos según sea necesario.
## Conclusión
En conclusión, Aspose.Slides para .NET permite a los desarrolladores crear presentaciones atractivas con facilidad. La capacidad de generar miniaturas para SmartArt Child Notes mejora el atractivo visual de sus presentaciones, brindando una experiencia de usuario dinámica e interactiva.
## Preguntas frecuentes
### P: ¿Puedo personalizar el tamaño y el formato de la miniatura generada?
R: Sí, puedes ajustar las dimensiones y el formato de la miniatura modificando los parámetros correspondientes en el código.
### P: ¿Aspose.Slides admite otros diseños SmartArt?
R: ¡Absolutamente! Aspose.Slides ofrece una variedad de diseños SmartArt, permitiéndole elegir el que mejor se adapte a sus necesidades de presentación.
### P: ¿Hay una licencia temporal disponible para realizar pruebas?
 R: Sí, puede obtener una licencia temporal de[aquí](https://purchase.aspose.com/temporary-license/) para pruebas y evaluación.
### P: ¿Dónde puedo buscar ayuda o conectarme con la comunidad Aspose.Slides?
 R: Visita el[Foro Aspose.Slides](https://forum.aspose.com/c/slides/11) para interactuar con la comunidad, hacer preguntas y encontrar soluciones.
### P: ¿Puedo comprar Aspose.Slides para .NET?
 R: ¡Ciertamente! Explora las opciones de compra[aquí](https://purchase.aspose.com/buy) para desbloquear todo el potencial de Aspose.Slides en sus proyectos.