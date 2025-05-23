---
"description": "Aprenda a ocultar formas en diapositivas de PowerPoint con Aspose.Slides para .NET. Personalice sus presentaciones mediante programación con esta guía paso a paso."
"linktitle": "Ocultar formas en diapositivas de presentación con Aspose.Slides"
"second_title": "API de procesamiento de PowerPoint Aspose.Slides .NET"
"title": "Tutorial de Aspose.Slides .NET para ocultar formas en PowerPoint"
"url": "/es/net/shape-geometry-and-positioning-in-slides/hiding-shapes/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tutorial de Aspose.Slides .NET para ocultar formas en PowerPoint

## Introducción
En el dinámico mundo de las presentaciones, la personalización es clave. Aspose.Slides para .NET ofrece una potente solución para manipular presentaciones de PowerPoint mediante programación. Un requisito común es la posibilidad de ocultar formas específicas dentro de una diapositiva. Este tutorial le guiará en el proceso de ocultar formas en las diapositivas de una presentación con Aspose.Slides para .NET.
## Prerrequisitos
Antes de sumergirse en el tutorial, asegúrese de tener los siguientes requisitos previos:
- Aspose.Slides para .NET: Asegúrate de tener instalada la biblioteca Aspose.Slides. Puedes descargarla. [aquí](https://releases.aspose.com/slides/net/).
- Entorno de desarrollo: configure su entorno de desarrollo preferido para .NET.
- Conocimientos básicos de C#: Familiarícese con C# ya que los ejemplos de código proporcionados están en este lenguaje.
## Importar espacios de nombres
Para empezar a trabajar con Aspose.Slides, importe los espacios de nombres necesarios en su proyecto de C#. Esto garantiza el acceso a las clases y métodos necesarios.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
Ahora, dividamos el código de ejemplo en varios pasos para una comprensión clara y concisa.
## Paso 1: Configura tu proyecto
Cree un nuevo proyecto C# y asegúrese de incluir la biblioteca Aspose.Slides.
## Paso 2: Crear una presentación
Instanciar el `Presentation` Clase que representa el archivo de PowerPoint. Agrega una diapositiva y obtén una referencia a ella.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## Paso 3: Agregar formas a la diapositiva
Agregue autoformas a la diapositiva, como rectángulos y lunas, con dimensiones específicas.
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## Paso 4: Ocultar formas según texto alternativo
Especifique un texto alternativo y oculte las formas que coincidan con este texto.
```csharp
String alttext = "User Defined";
int iCount = sld.Shapes.Count;
for (int i = 0; i < iCount; i++)
{
    AutoShape ashp = (AutoShape)sld.Shapes[i];
    if (String.Compare(ashp.AlternativeText, alttext, StringComparison.Ordinal) == 0)
    {
        ashp.Hidden = true;
    }
}
```
## Paso 5: Guardar la presentación
Guarde la presentación modificada en el disco en formato PPTX.
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## Conclusión
¡Felicitaciones! Has ocultado formas en tu presentación con Aspose.Slides para .NET. Esto abre un mundo de posibilidades para crear diapositivas dinámicas y personalizadas mediante programación.
---
## Preguntas frecuentes
### ¿Es Aspose.Slides compatible con .NET Core?
Sí, Aspose.Slides es compatible con .NET Core, lo que proporciona flexibilidad en su entorno de desarrollo.
### ¿Puedo ocultar formas en función de condiciones distintas al texto alternativo?
¡Por supuesto! Puedes personalizar la lógica de ocultación según diversos atributos, como el tipo de forma, el color o la posición.
### ¿Dónde puedo encontrar documentación adicional de Aspose.Slides?
Explorar la documentación [aquí](https://reference.aspose.com/slides/net/) para obtener información detallada y ejemplos.
### ¿Hay licencias temporales disponibles para Aspose.Slides?
Sí, puedes obtener una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/) para fines de prueba.
### ¿Cómo puedo obtener soporte de la comunidad para Aspose.Slides?
Únase a la comunidad Aspose.Slides en [foro](https://forum.aspose.com/c/slides/11) Para discusiones y asistencia.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}