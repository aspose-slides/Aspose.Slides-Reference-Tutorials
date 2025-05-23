---
"description": "Aprenda a agregar y eliminar hipervínculos en Aspose.Slides para .NET. Mejore sus presentaciones con enlaces interactivos fácilmente."
"linktitle": "Manipulación de hipervínculos en Aspose.Slides"
"second_title": "API de procesamiento de PowerPoint Aspose.Slides .NET"
"title": "Manipulación de hipervínculos en Aspose.Slides"
"url": "/es/net/hyperlink-manipulation/hyperlink-manipulation/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Manipulación de hipervínculos en Aspose.Slides


Los hipervínculos son elementos esenciales en las presentaciones, ya que facilitan la navegación entre diapositivas o el acceso a recursos externos. Aspose.Slides para .NET ofrece potentes funciones para añadir y eliminar hipervínculos en las diapositivas de tus presentaciones. En este tutorial, te guiaremos en el proceso de manipulación de hipervínculos con Aspose.Slides para .NET. Analizaremos cómo añadir y eliminar hipervínculos a una diapositiva. ¡Comencemos!

## Prerrequisitos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

1. Aspose.Slides para .NET: Debe tener instalada y configurada la biblioteca Aspose.Slides para .NET. Puede encontrar la documentación. [aquí](https://reference.aspose.com/slides/net/) y descargarlo desde [este enlace](https://releases.aspose.com/slides/net/).

2. Directorio de documentos: Necesita un directorio donde guardará los archivos de su presentación. Asegúrese de especificar la ruta de este directorio en su código.

3. Conocimientos básicos de C#: este tutorial asume que tienes un conocimiento básico de programación en C#.

Ahora que ya tienes los requisitos previos establecidos, pasemos a la guía paso a paso para la manipulación de hipervínculos usando Aspose.Slides para .NET.

## Cómo agregar hipervínculos a una diapositiva

### Paso 1: Inicializar la presentación

Para empezar, necesitas inicializar una presentación con Aspose.Slides. Puedes hacerlo con el siguiente código:

```csharp
using (Presentation presentation = new Presentation())
{
    // Tu código aquí
}
```

### Paso 2: Agregar marco de texto

Ahora, agreguemos un marco de texto a una diapositiva. Este código crea una forma rectangular con texto:

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

### Paso 3: Agregar hipervínculo

A continuación, agregará un hipervínculo al texto en la forma que creó. Así es como puede hacerlo:

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

### Paso 4: Guardar la presentación

Por último, guarde su presentación con el hipervínculo agregado:

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

¡Felicitaciones! Has añadido correctamente un hipervínculo a una diapositiva con Aspose.Slides para .NET.

## Cómo eliminar hipervínculos de una diapositiva

### Paso 1: Inicializar la presentación

Para eliminar hipervínculos de una diapositiva, debe abrir una presentación existente:

```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Hyperlink.pptx");
```

### Paso 2: Eliminar hipervínculos

Ahora, elimine todos los hipervínculos de la presentación utilizando el siguiente código:

```csharp
presentation.HyperlinkQueries.RemoveAllHyperlinks();
```

### Paso 3: Guardar la presentación

Después de eliminar los hipervínculos, guarde la presentación:

```csharp
presentation.Save(dataDir + "RemovedHyperlink_out.pptx", SaveFormat.Pptx);
```

¡Listo! Has eliminado correctamente los hipervínculos de una diapositiva con Aspose.Slides para .NET.

En conclusión, Aspose.Slides para .NET ofrece una forma eficiente de manipular hipervínculos en sus presentaciones, permitiéndole crear diapositivas interactivas y atractivas. Tanto si desea añadir hipervínculos a recursos externos como eliminarlos, Aspose.Slides simplifica el proceso y mejora sus capacidades de creación de presentaciones.

Gracias por acompañarnos en este tutorial sobre la manipulación de hipervínculos en Aspose.Slides para .NET. Si tiene alguna pregunta o necesita más ayuda, no dude en explorar... [Documentación de Aspose.Slides](https://reference.aspose.com/slides/net/) o comuníquese con la comunidad Aspose en [foro de soporte](https://forum.aspose.com/).

---

## Conclusión

En este tutorial, aprendimos a manipular hipervínculos en presentaciones con Aspose.Slides para .NET. Abordamos la adición y eliminación de hipervínculos, lo que te permite crear presentaciones dinámicas e interactivas. Aspose.Slides simplifica el proceso, facilitando la mejora de tus diapositivas con hipervínculos a recursos externos.

¿Tienes más preguntas sobre cómo trabajar con Aspose.Slides u otros aspectos del diseño de presentaciones? Consulta las preguntas frecuentes a continuación para obtener más información.

## Preguntas frecuentes

### ¿Cuáles son las principales ventajas de utilizar Aspose.Slides para .NET?
Aspose.Slides para .NET ofrece una amplia gama de funciones para crear, manipular y convertir presentaciones. Ofrece un completo conjunto de herramientas para añadir contenido, animaciones e interacciones a las diapositivas.

### ¿Puedo agregar hipervínculos a otros objetos que no sean texto en Aspose.Slides?
Sí, Aspose.Slides le permite agregar hipervínculos a varios objetos, incluidas formas, imágenes y texto, lo que le brinda flexibilidad para crear presentaciones interactivas.

### ¿Aspose.Slides es compatible con diferentes formatos de archivos de PowerPoint?
Por supuesto. Aspose.Slides es compatible con varios formatos de PowerPoint, como PPT, PPTX, PPS y más. Garantiza la compatibilidad con diferentes versiones de Microsoft PowerPoint.

### ¿Dónde puedo encontrar recursos adicionales y soporte para Aspose.Slides?
Para obtener documentación detallada y soporte de la comunidad, visite el sitio [Documentación de Aspose.Slides](https://reference.aspose.com/slides/net/) y el [Foro de soporte de Aspose](https://forum.aspose.com/).

### ¿Cómo puedo obtener una licencia temporal para Aspose.Slides?
Si necesita una licencia temporal para Aspose.Slides, puede obtener una [aquí](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}