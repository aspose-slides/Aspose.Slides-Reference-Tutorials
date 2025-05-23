---
"description": "Aprenda a crear formas de grupo en PowerPoint con Aspose.Slides para .NET. Siga nuestra guía paso a paso para crear presentaciones visualmente atractivas."
"linktitle": "Creación de formas de grupo en diapositivas de presentación con Aspose.Slides"
"second_title": "API de procesamiento de PowerPoint Aspose.Slides .NET"
"title": "Aspose.Slides - Creación de formas de grupo en .NET"
"url": "/es/net/image-and-video-manipulation-in-slides/creating-group-shapes/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - Creación de formas de grupo en .NET

## Introducción
Si busca mejorar el aspecto visual de las diapositivas de su presentación y organizar el contenido de forma más eficiente, incorporar formas de grupo es una solución eficaz. Aspose.Slides para .NET ofrece una forma sencilla de crear y manipular formas de grupo en sus presentaciones de PowerPoint. En este tutorial, le guiaremos paso a paso para crear formas de grupo con Aspose.Slides.
## Prerrequisitos
Antes de sumergirnos en el tutorial, asegúrese de tener lo siguiente:
- Aspose.Slides para .NET: Asegúrese de tener instalada la biblioteca Aspose.Slides. Puede descargarla desde [sitio web](https://releases.aspose.com/slides/net/).
- Entorno de desarrollo: configure un entorno de trabajo con un IDE compatible con .NET, como Visual Studio.
- Conocimientos básicos de C#: Familiarícese con los conceptos básicos del lenguaje de programación C#.
## Importar espacios de nombres
En su proyecto de C#, comience importando los espacios de nombres necesarios:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Paso 1: Crear una instancia de la clase de presentación

Crear una instancia de la `Presentation` clase y especifique el directorio donde se almacenan sus documentos:

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // Continúe con los siguientes pasos dentro de este bloque de uso
}
```

## Paso 2: Acceda a la primera diapositiva

Recuperar la primera diapositiva de la presentación:

```csharp
ISlide sld = pres.Slides[0];
```

## Paso 3: Acceder a la colección de formas

Acceda a la colección de formas en la diapositiva:

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## Paso 4: Agregar una forma de grupo

Agregar una forma de grupo a la diapositiva:

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## Paso 5: Agregar formas dentro de la forma de grupo

Rellene la forma del grupo con formas individuales:

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## Paso 6: Agregar marco de forma de grupo

Define el marco para toda la forma del grupo:

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## Paso 7: Guardar la presentación

Guarde la presentación modificada en el directorio especificado:

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

Repita estos pasos en su aplicación C# para crear con éxito formas de grupo en sus diapositivas de presentación usando Aspose.Slides.

## Conclusión
En este tutorial, exploramos el proceso de creación de formas de grupo con Aspose.Slides para .NET. Siguiendo estos pasos, podrá mejorar el aspecto visual y la organización de sus presentaciones de PowerPoint.
## Preguntas frecuentes
### ¿Es Aspose.Slides compatible con la última versión de .NET?
Sí, Aspose.Slides se actualiza periódicamente para ser compatible con las últimas versiones de .NET. Consulta la [documentación](https://reference.aspose.com/slides/net/) para obtener detalles de compatibilidad.
### ¿Puedo probar Aspose.Slides antes de comprarlo?
¡Claro! Puedes descargar una versión de prueba gratuita. [aquí](https://releases.aspose.com/).
### ¿Dónde puedo encontrar ayuda para las consultas relacionadas con Aspose.Slides?
Visita Aspose.Slides [foro](https://forum.aspose.com/c/slides/11) Para apoyo y debates de la comunidad.
### ¿Cómo obtengo una licencia temporal para Aspose.Slides?
Puedes obtener una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).
### ¿Dónde puedo comprar una licencia completa para Aspose.Slides?
Puede comprar una licencia en [página de compra](https://purchase.aspose.com/buy).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}