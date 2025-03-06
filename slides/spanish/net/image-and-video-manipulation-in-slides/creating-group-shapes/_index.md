---
title: Aspose.Slides creación de formas de grupo en .NET
linktitle: Crear formas de grupo en diapositivas de presentación con Aspose.Slides
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda a crear formas de grupo en PowerPoint con Aspose.Slides para .NET. Siga nuestra guía paso a paso para presentaciones visualmente atractivas.
type: docs
weight: 11
url: /es/net/image-and-video-manipulation-in-slides/creating-group-shapes/
---
## Introducción
Si busca mejorar el atractivo visual de las diapositivas de su presentación y organizar el contenido de manera más eficiente, incorporar formas grupales es una solución poderosa. Aspose.Slides para .NET proporciona una manera perfecta de crear y manipular formas de grupo en sus presentaciones de PowerPoint. En este tutorial, recorreremos el proceso de creación de formas grupales usando Aspose.Slides, dividiéndolo en pasos fáciles de seguir.
## Requisitos previos
Antes de sumergirnos en el tutorial, asegúrese de tener lo siguiente:
-  Aspose.Slides para .NET: asegúrese de tener instalada la biblioteca Aspose.Slides. Puedes descargarlo desde el[sitio web](https://releases.aspose.com/slides/net/).
- Entorno de desarrollo: configure un entorno de trabajo con un IDE compatible con .NET, como Visual Studio.
- Conocimientos básicos de C#: familiarícese con los conceptos básicos del lenguaje de programación C#.
## Importar espacios de nombres
En su proyecto C#, comience importando los espacios de nombres necesarios:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Paso 1: crear una instancia de la clase de presentación

 Crear una instancia del`Presentation` class y especifique el directorio donde se almacenan sus documentos:

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // Continúe con los siguientes pasos dentro de este bloque de uso
}
```

## Paso 2: acceda a la primera diapositiva

Recupere la primera diapositiva de la presentación:

```csharp
ISlide sld = pres.Slides[0];
```

## Paso 3: acceder a la colección de formas

Accede a la colección de formas en la diapositiva:

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## Paso 4: agregar una forma de grupo

Agregue una forma de grupo a la diapositiva:

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## Paso 5: agregar formas dentro de la forma del grupo

Complete la forma del grupo con formas individuales:

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## Paso 6: Agregar un marco de forma de grupo

Defina el marco para toda la forma del grupo:

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## Paso 7: guarde la presentación

Guarde la presentación modificada en su directorio especificado:

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

Repita estos pasos en su aplicación C# para crear con éxito formas de grupo en las diapositivas de su presentación usando Aspose.Slides.

## Conclusión
En este tutorial, exploramos el proceso de creación de formas grupales con Aspose.Slides para .NET. Si sigue estos pasos, podrá mejorar el atractivo visual y la organización de sus presentaciones de PowerPoint.
## Preguntas frecuentes
### ¿Aspose.Slides es compatible con la última versión de .NET?
 Sí, Aspose.Slides se actualiza periódicamente para admitir las últimas versiones de .NET. Comprobar el[documentación](https://reference.aspose.com/slides/net/) para detalles de compatibilidad.
### ¿Puedo probar Aspose.Slides antes de comprarlo?
 ¡Absolutamente! Puedes descargar una versión de prueba gratuita.[aquí](https://releases.aspose.com/).
### ¿Dónde puedo encontrar soporte para consultas relacionadas con Aspose.Slides?
Visita las diapositivas de Aspose[foro](https://forum.aspose.com/c/slides/11) para apoyo y debates de la comunidad.
### ¿Cómo obtengo una licencia temporal para Aspose.Slides?
 Puedes obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).
### ¿Dónde puedo comprar una licencia completa para Aspose.Slides?
 Puede comprar una licencia en el[pagina de compra](https://purchase.aspose.com/buy).
