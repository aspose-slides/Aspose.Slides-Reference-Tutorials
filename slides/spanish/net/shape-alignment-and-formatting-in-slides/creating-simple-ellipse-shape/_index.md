---
title: Cree formas de elipse fácilmente con Aspose.Slides .NET
linktitle: Crear una forma de elipse simple en diapositivas de presentación con Aspose.Slides
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda a crear impresionantes formas de elipse en diapositivas de presentación usando Aspose.Slides para .NET. ¡Pasos sencillos para un diseño dinámico!
type: docs
weight: 11
url: /es/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/
---
## Introducción
En el dinámico mundo del diseño de presentaciones, la incorporación de formas como elipses puede agregar un toque de creatividad y profesionalismo. Aspose.Slides para .NET ofrece una poderosa solución para manipular archivos de presentación mediante programación. Este tutorial lo guiará a través del proceso de creación de una forma de elipse simple en diapositivas de presentación usando Aspose.Slides para .NET.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
- Aspose.Slides para .NET: asegúrese de haber instalado la biblioteca Aspose.Slides para .NET. Puedes descargarlo desde el[página de lanzamientos](https://releases.aspose.com/slides/net/).
- Entorno de desarrollo: configure un entorno de desarrollo .NET en su máquina.
## Importar espacios de nombres
En su proyecto .NET, comience importando los espacios de nombres necesarios:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Estos espacios de nombres proporcionan las clases y métodos esenciales necesarios para trabajar con diapositivas y formas de presentación.
## Paso 1: configurar la presentación
Comience creando una nueva presentación y accediendo a la primera diapositiva. Agregue el siguiente código para lograr esto:
```csharp
// La ruta al directorio de documentos.
string dataDir = "Your Document Directory";
// Cree un directorio si aún no está presente.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// Crear una instancia de la clase de presentación
using (Presentation pres = new Presentation())
{
    // Obtenga la primera diapositiva
    ISlide sld = pres.Slides[0];
```
Este código inicializa una nueva presentación y selecciona la primera diapositiva para su posterior manipulación.
## Paso 2: agregar forma de elipse
 Ahora, agreguemos una forma de elipse a la diapositiva usando el`AddAutoShape` método:
```csharp
// Agregar autoforma de tipo elipse
sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
Esta línea de código crea una forma de elipse en las coordenadas (50, 150) con un ancho de 150 unidades y una altura de 50 unidades.
## Paso 3: guarde la presentación
Finalmente, guarde la presentación modificada en el disco con un nombre de archivo específico usando el siguiente código:
```csharp
// Escriba el archivo PPTX en el disco
pres.Save(dataDir + "EllipseShp1_out.pptx", SaveFormat.Pptx);
```
Este paso garantiza que sus cambios persistan y que pueda ver la presentación resultante con la forma de elipse recién agregada.
## Conclusión
Congratulations! You've successfully created a simple ellipse shape in a presentation slide using Aspose.Slides for .NET. This tutorial provides a foundational understanding of working with shapes, setting up presentations, and saving the modified files.
---
## Preguntas frecuentes
### ¿Puedo personalizar aún más la forma de la elipse?
Sí, puede modificar varias propiedades de la forma de elipse, como el color, el tamaño y la posición, para cumplir con sus requisitos de diseño específicos.
### ¿Aspose.Slides es compatible con los últimos frameworks .NET?
Sí, Aspose.Slides se actualiza periódicamente para garantizar la compatibilidad con los últimos marcos .NET.
### ¿Dónde puedo encontrar más tutoriales y ejemplos para Aspose.Slides?
 Visita el[documentación](https://reference.aspose.com/slides/net/) para guías completas y ejemplos.
### ¿Cómo puedo obtener una licencia temporal para Aspose.Slides?
 Siga el[enlace de licencia temporal](https://purchase.aspose.com/temporary-license/) para solicitar una licencia temporal con fines de prueba.
### ¿Necesita ayuda o tiene preguntas específicas?
 Visita el[Foro de soporte de Aspose.Slides](https://forum.aspose.com/c/slides/11) para obtener ayuda de la comunidad y de expertos.