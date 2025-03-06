---
title: Manipulación de hipervínculos en Aspose.Slides
linktitle: Manipulación de hipervínculos en Aspose.Slides
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda a agregar y eliminar hipervínculos en Aspose.Slides para .NET. Mejore sus presentaciones con enlaces interactivos fácilmente.
weight: 10
url: /es/net/hyperlink-manipulation/hyperlink-manipulation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Los hipervínculos son elementos esenciales en las presentaciones, ya que proporcionan una forma conveniente de navegar entre diapositivas o acceder a recursos externos. Aspose.Slides para .NET ofrece potentes funciones para agregar y eliminar hipervínculos en las diapositivas de su presentación. En este tutorial, lo guiaremos a través del proceso de manipulación de hipervínculos usando Aspose.Slides para .NET. Cubriremos cómo agregar hipervínculos a una diapositiva y eliminar hipervínculos de una diapositiva. Entonces, ¡sumergámonos!

## Requisitos previos

Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

1.  Aspose.Slides para .NET: Debe tener instalada y configurada la biblioteca Aspose.Slides para .NET. Puedes encontrar la documentación.[aquí](https://reference.aspose.com/slides/net/) y descargarlo de[este enlace](https://releases.aspose.com/slides/net/).

2. Su directorio de documentos: necesita un directorio donde almacenará sus archivos de presentación. Asegúrese de especificar la ruta a este directorio en su código.

3. Conocimientos básicos de C#: este tutorial asume que tienes conocimientos básicos de programación en C#.

Ahora que tiene los requisitos previos implementados, pasemos a la guía paso a paso para la manipulación de hipervínculos usando Aspose.Slides para .NET.

## Agregar hipervínculos a una diapositiva

### Paso 1: Inicializar la presentación

Para comenzar, necesita inicializar una presentación usando Aspose.Slides. Puedes hacer esto con el siguiente código:

```csharp
using (Presentation presentation = new Presentation())
{
    // Tu código aquí
}
```

### Paso 2: agregar marco de texto

Ahora, agreguemos un marco de texto a una diapositiva. Este código crea una forma rectangular con texto:

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

### Paso 3: agregar hipervínculo

A continuación, agregará un hipervínculo al texto en la forma que creó. Así es como puedes hacerlo:

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

### Paso 4: guardar la presentación

Finalmente, guarde su presentación con el hipervínculo agregado:

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

¡Felicidades! Ha agregado con éxito un hipervínculo a una diapositiva usando Aspose.Slides para .NET.

## Eliminar hipervínculos de una diapositiva

### Paso 1: Inicializar la presentación

Para eliminar hipervínculos de una diapositiva, debe abrir una presentación existente:

```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Hyperlink.pptx");
```

### Paso 2: eliminar hipervínculos

Ahora, elimine todos los hipervínculos de la presentación usando el siguiente código:

```csharp
presentation.HyperlinkQueries.RemoveAllHyperlinks();
```

### Paso 3: guardar la presentación

Después de eliminar los hipervínculos, guarde la presentación:

```csharp
presentation.Save(dataDir + "RemovedHyperlink_out.pptx", SaveFormat.Pptx);
```

¡Y eso es! Ha eliminado con éxito los hipervínculos de una diapositiva usando Aspose.Slides para .NET.

En conclusión, Aspose.Slides para .NET proporciona una manera eficiente de manipular hipervínculos en sus presentaciones, permitiéndole crear diapositivas interactivas y atractivas. Ya sea que desee agregar hipervínculos a recursos externos o eliminarlos, Aspose.Slides simplifica el proceso y mejora sus capacidades de creación de presentaciones.

 Gracias por acompañarnos en este tutorial sobre manipulación de hipervínculos en Aspose.Slides para .NET. Si tiene alguna pregunta o necesita más ayuda, no dude en explorar la[Documentación de Aspose.Slides](https://reference.aspose.com/slides/net/) o comuníquese con la comunidad de Aspose en el[Foro de soporte](https://forum.aspose.com/).

---

## Conclusión

En este tutorial, aprendimos cómo manipular hipervínculos en presentaciones usando Aspose.Slides para .NET. Cubrimos tanto la adición como la eliminación de hipervínculos, permitiéndole crear presentaciones dinámicas e interactivas. Aspose.Slides simplifica el proceso, facilitando la mejora de sus diapositivas con hipervínculos a recursos externos.

¿Tiene más preguntas sobre cómo trabajar con Aspose.Slides u otros aspectos del diseño de presentaciones? Consulte las preguntas frecuentes a continuación para obtener más información.

## Preguntas frecuentes (Preguntas frecuentes)

### ¿Cuáles son las ventajas clave de utilizar Aspose.Slides para .NET?
Aspose.Slides para .NET ofrece una amplia gama de funciones para crear, manipular y convertir presentaciones. Proporciona un conjunto completo de herramientas para agregar contenido, animaciones e interacciones a sus diapositivas.

### ¿Puedo agregar hipervínculos a objetos que no sean texto en Aspose.Slides?
Sí, Aspose.Slides le permite agregar hipervínculos a varios objetos, incluidas formas, imágenes y texto, lo que le brinda flexibilidad para crear presentaciones interactivas.

### ¿Aspose.Slides es compatible con diferentes formatos de archivos de PowerPoint?
Absolutamente. Aspose.Slides admite varios formatos de PowerPoint, incluidos PPT, PPTX, PPS y más. Garantiza la compatibilidad con diferentes versiones de Microsoft PowerPoint.

### ¿Dónde puedo encontrar recursos adicionales y soporte para Aspose.Slides?
 Para obtener documentación detallada y soporte de la comunidad, visite el[Documentación de Aspose.Slides](https://reference.aspose.com/slides/net/) y el[Aspose foro de soporte](https://forum.aspose.com/).

### ¿Cómo puedo obtener una licencia temporal para Aspose.Slides?
 Si necesita una licencia temporal para Aspose.Slides, puede obtener una[aquí](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
