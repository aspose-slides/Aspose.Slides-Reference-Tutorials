---
title: Creando formas rectangulares con Aspose.Slides para .NET
linktitle: Crear una forma de rectángulo simple en diapositivas de presentación usando Aspose.Slides
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Explore el mundo de las presentaciones dinámicas de PowerPoint con Aspose.Slides para .NET. Aprenda a crear atractivas formas rectangulares en diapositivas con esta guía paso a paso.
weight: 12
url: /es/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introducción
Si busca mejorar sus aplicaciones .NET con presentaciones de PowerPoint dinámicas y visualmente atractivas, Aspose.Slides para .NET es su solución preferida. En este tutorial, lo guiaremos a través del proceso de creación de una forma de rectángulo simple en diapositivas de presentación usando Aspose.Slides para .NET.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de tener los siguientes requisitos previos:
- Visual Studio: asegúrese de tener Visual Studio instalado en su máquina de desarrollo.
-  Aspose.Slides para .NET: descargue e instale la biblioteca Aspose.Slides para .NET desde[aquí](https://releases.aspose.com/slides/net/).
- Conocimientos básicos de C#: la familiaridad con el lenguaje de programación C# es esencial.
## Importar espacios de nombres
En su proyecto C#, comience importando los espacios de nombres necesarios para acceder a las funcionalidades de Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Paso 1: configurar el proyecto
Comience creando un nuevo proyecto de C# en Visual Studio. Asegúrese de que se haga referencia correctamente a Aspose.Slides para .NET en su proyecto.
## Paso 2: inicializar el objeto de presentación
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Su código para los próximos pasos irá aquí.
}
```
## Paso 3: obtenga la primera diapositiva
```csharp
ISlide sld = pres.Slides[0];
```
## Paso 4: agregar autoforma de rectángulo
```csharp
sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
Este código agrega una forma de rectángulo en las coordenadas (50, 150) con un ancho de 150 y una altura de 50.
## Paso 5: guarde la presentación
```csharp
pres.Save(dataDir + "RectShp1_out.pptx", SaveFormat.Pptx);
```
Este paso guarda la presentación con la forma de rectángulo agregada en el directorio especificado.
## Conclusión
¡Felicidades! Ha creado con éxito una forma de rectángulo simple en una diapositiva de presentación usando Aspose.Slides para .NET. Esto es solo el comienzo: Aspose.Slides ofrece una amplia gama de funciones para personalizar y mejorar aún más sus presentaciones.
## Preguntas frecuentes
### ¿Puedo usar Aspose.Slides para .NET en entornos Windows y Linux?
Sí, Aspose.Slides para .NET es independiente de la plataforma y se puede utilizar tanto en entornos Windows como Linux.
### ¿Hay una prueba gratuita disponible para Aspose.Slides para .NET?
 Sí, puedes obtener una prueba gratuita.[aquí](https://releases.aspose.com/).
### ¿Cómo puedo obtener soporte para Aspose.Slides para .NET?
 Visita el[Foro Aspose.Slides](https://forum.aspose.com/c/slides/11) para el apoyo de la comunidad.
### ¿Puedo comprar una licencia temporal de Aspose.Slides para .NET?
 Sí, puedes comprar una licencia temporal.[aquí](https://purchase.aspose.com/temporary-license/).
### ¿Dónde puedo encontrar la documentación de Aspose.Slides para .NET?
 Consulte la documentación.[aquí](https://reference.aspose.com/slides/net/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
