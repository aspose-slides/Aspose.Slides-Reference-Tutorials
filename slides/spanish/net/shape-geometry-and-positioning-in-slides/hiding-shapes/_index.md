---
title: Ocultar formas en PowerPoint con Aspose.Slides .NET Tutorial
linktitle: Ocultar formas en diapositivas de presentación con Aspose.Slides
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda a ocultar formas en diapositivas de PowerPoint usando Aspose.Slides para .NET. Personalice presentaciones mediante programación con esta guía paso a paso.
weight: 21
url: /es/net/shape-geometry-and-positioning-in-slides/hiding-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ocultar formas en PowerPoint con Aspose.Slides .NET Tutorial

## Introducción
En el dinámico mundo de las presentaciones, la personalización es clave. Aspose.Slides para .NET proporciona una poderosa solución para manipular presentaciones de PowerPoint mediante programación. Un requisito común es la capacidad de ocultar formas específicas dentro de una diapositiva. Este tutorial lo guiará a través del proceso de ocultar formas en diapositivas de presentación usando Aspose.Slides para .NET.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
-  Aspose.Slides para .NET: asegúrese de tener instalada la biblioteca Aspose.Slides. Puedes descargarlo[aquí](https://releases.aspose.com/slides/net/).
- Entorno de desarrollo: configure su entorno de desarrollo preferido para .NET.
- Conocimientos básicos de C#: familiarícese con C# ya que los ejemplos de código proporcionados están en este lenguaje.
## Importar espacios de nombres
Para comenzar a trabajar con Aspose.Slides, importe los espacios de nombres necesarios en su proyecto C#. Esto garantiza que tenga acceso a las clases y métodos necesarios.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
Ahora, dividamos el código de ejemplo en varios pasos para una comprensión clara y concisa.
## Paso 1: configura tu proyecto
Cree un nuevo proyecto de C# y asegúrese de incluir la biblioteca Aspose.Slides.
## Paso 2: crea una presentación
 Instanciar el`Presentation` clase, que representa el archivo de PowerPoint. Agregue una diapositiva y obtenga una referencia a ella.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## Paso 3: agregue formas a la diapositiva
Agregue formas automáticas a la diapositiva, como rectángulos y lunas, con dimensiones específicas.
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## Paso 4: Ocultar formas basadas en texto alternativo
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
## Paso 5: guarde la presentación
Guarde la presentación modificada en el disco en formato PPTX.
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## Conclusión
Congratulations! You've successfully hidden shapes in your presentation using Aspose.Slides for .NET. This opens up a world of possibilities for creating dynamic and customized slides programmatically.
---
## Preguntas frecuentes
### ¿Aspose.Slides es compatible con .NET Core?
Sí, Aspose.Slides es compatible con .NET Core, lo que brinda flexibilidad en su entorno de desarrollo.
### ¿Puedo ocultar formas según condiciones distintas al texto alternativo?
¡Absolutamente! Puede personalizar la lógica de ocultación en función de varios atributos como el tipo de forma, el color o la posición.
### ¿Dónde puedo encontrar documentación adicional de Aspose.Slides?
 Explora la documentación[aquí](https://reference.aspose.com/slides/net/)para obtener información detallada y ejemplos.
### ¿Hay licencias temporales disponibles para Aspose.Slides?
 Sí, puedes obtener una licencia temporal.[aquí](https://purchase.aspose.com/temporary-license/)con fines de prueba.
### ¿Cómo puedo obtener apoyo de la comunidad para Aspose.Slides?
 Únase a la comunidad Aspose.Slides en el[foro](https://forum.aspose.com/c/slides/11) para discusiones y ayuda.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
