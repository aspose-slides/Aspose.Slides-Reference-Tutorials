---
"description": "Explora el poder de Aspose.Slides para .NET al cambiar fácilmente los datos de objetos OLE. Mejora tus presentaciones con contenido dinámico."
"linktitle": "Cambiar datos de objetos OLE en una presentación con Aspose.Slides"
"second_title": "API de procesamiento de PowerPoint Aspose.Slides .NET"
"title": "Cambiar datos de objetos OLE en una presentación con Aspose.Slides"
"url": "/es/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Cambiar datos de objetos OLE en una presentación con Aspose.Slides

## Introducción
Crear presentaciones de PowerPoint dinámicas e interactivas es un requisito común en el mundo digital actual. Una herramienta eficaz para lograrlo es Aspose.Slides para .NET, una robusta biblioteca que permite a los desarrolladores manipular y mejorar presentaciones de PowerPoint mediante programación. En este tutorial, profundizaremos en el proceso de modificar datos de objetos OLE (vinculación e incrustación de objetos) dentro de las diapositivas de una presentación mediante Aspose.Slides.
## Prerrequisitos
Antes de comenzar a trabajar con Aspose.Slides para .NET, asegúrese de tener los siguientes requisitos previos:
1. Entorno de desarrollo: configure un entorno de desarrollo con .NET instalado.
2. Biblioteca Aspose.Slides: Descargue e instale la biblioteca Aspose.Slides para .NET. Puede encontrarla [aquí](https://releases.aspose.com/slides/net/).
3. Comprensión básica: familiarícese con los conceptos básicos de programación en C# y presentaciones de PowerPoint.
## Importar espacios de nombres
En su proyecto C#, importe los espacios de nombres necesarios para utilizar las funcionalidades de Aspose.Slides:
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## Paso 1: Configura tu proyecto
Comience creando un nuevo proyecto de C# e importando la biblioteca Aspose.Slides. Asegúrese de que el proyecto esté configurado correctamente y de que tenga las dependencias necesarias.
## Paso 2: Acceder a la presentación y a la diapositiva
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## Paso 3: Localizar el objeto OLE
Recorra todas las formas en la diapositiva para encontrar el marco del objeto OLE:
```csharp
OleObjectFrame ole = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is OleObjectFrame)
    {
        ole = (OleObjectFrame)shape;
    }
}
```
## Paso 4: Leer y modificar los datos del libro de trabajo
```csharp
if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        // Lectura de datos de objetos en el libro de trabajo
        Workbook Wb = new Workbook(msln);
        using (MemoryStream msout = new MemoryStream())
        {
            // Modificar los datos del libro de trabajo
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            // Cambiar los datos del objeto de marco Ole
            IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
            ole.SetEmbeddedData(newData);
        }
    }
}
```
## Paso 5: Guardar la presentación
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## Conclusión
Siguiendo estos pasos, podrá modificar fácilmente los datos de objetos OLE en las diapositivas de una presentación con Aspose.Slides para .NET. Esto abre un mundo de posibilidades para crear presentaciones dinámicas y personalizadas, adaptadas a sus necesidades específicas.
## Preguntas frecuentes
### ¿Qué es Aspose.Slides para .NET?
Aspose.Slides para .NET es una potente biblioteca que permite a los desarrolladores trabajar con presentaciones de PowerPoint mediante programación, lo que permite una fácil manipulación y mejora.
### ¿Dónde puedo encontrar la documentación de Aspose.Slides?
La documentación de Aspose.Slides para .NET se puede encontrar [aquí](https://reference.aspose.com/slides/net/).
### ¿Cómo descargo Aspose.Slides para .NET?
Puede descargar la biblioteca desde la página de lanzamiento. [aquí](https://releases.aspose.com/slides/net/).
### ¿Hay una prueba gratuita disponible para Aspose.Slides?
Sí, puedes acceder a la prueba gratuita. [aquí](https://releases.aspose.com/).
### ¿Dónde puedo obtener soporte para Aspose.Slides para .NET?
Para obtener ayuda y participar en debates, visite el sitio [Foro de Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}