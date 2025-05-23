---
"description": "Aprenda a agregar hipervínculos a diapositivas de PowerPoint con Aspose.Slides para .NET. Mejore sus presentaciones con elementos interactivos."
"linktitle": "Agregar hipervínculo a la diapositiva"
"second_title": "API de procesamiento de PowerPoint Aspose.Slides .NET"
"title": "Cómo agregar hipervínculos a diapositivas en .NET mediante Aspose.Slides"
"url": "/es/net/hyperlink-manipulation/add-hyperlink/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Cómo agregar hipervínculos a diapositivas en .NET mediante Aspose.Slides


En el mundo de las presentaciones digitales, la interactividad es clave. Añadir hipervínculos a las diapositivas puede hacer que la presentación sea más atractiva e informativa. Aspose.Slides para .NET es una potente biblioteca que permite crear, modificar y manipular presentaciones de PowerPoint mediante programación. En este tutorial, le mostraremos cómo añadir hipervínculos a sus diapositivas con Aspose.Slides para .NET. 

## Prerrequisitos

Antes de comenzar a agregar hipervínculos a las diapositivas, asegúrese de tener los siguientes requisitos previos:

1. Visual Studio: debe tener Visual Studio instalado en su computadora para escribir y ejecutar el código .NET.

2. Aspose.Slides para .NET: Necesita tener instalada la biblioteca Aspose.Slides para .NET. Puede descargarla desde [aquí](https://releases.aspose.com/slides/net/).

3. Conocimientos básicos de C#: será beneficioso estar familiarizado con la programación en C#.

## Importar espacios de nombres

Para comenzar, debe importar los espacios de nombres necesarios en su proyecto de C#. En este caso, necesitará los siguientes espacios de nombres de la biblioteca Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

Ahora, vamos a dividir el proceso de agregar hipervínculos a las diapositivas en varios pasos.

## Paso 1: Inicializar la presentación

Primero, crea una nueva presentación con Aspose.Slides. Así es como puedes hacerlo:

```csharp
using (Presentation presentation = new Presentation())
{
    // Tu código va aquí
}
```

Este código inicializa una nueva presentación de PowerPoint.

## Paso 2: Agregar marco de texto

Ahora, agreguemos un marco de texto a la diapositiva. Este marco servirá como elemento clicable. 

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

El código anterior crea una forma automática rectangular y agrega un marco de texto con el texto "Aspose: API de formato de archivo".

## Paso 3: Agregar hipervínculo

A continuación, agreguemos un hipervínculo al marco de texto que creaste. Esto permitirá hacer clic en el texto.

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

En este paso, configuramos la URL del hipervínculo como "https://www.aspose.com/" y proporcionamos una descripción emergente con información adicional. También puede cambiar el formato del hipervínculo, como se muestra arriba.

## Paso 4: Guardar la presentación

Por último, guarde su presentación con el hipervínculo agregado.

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

Este código guarda la presentación como "presentation-out.pptx".

Ahora ha agregado exitosamente un hipervínculo a una diapositiva usando Aspose.Slides para .NET.

## Conclusión

En este tutorial, hemos explorado cómo agregar hipervínculos a las diapositivas de PowerPoint con Aspose.Slides para .NET. Siguiendo estos pasos, podrá hacer que sus presentaciones sean más interactivas y atractivas, proporcionando valiosos enlaces a recursos o información adicional.

Para obtener información y documentación más detallada, visite el sitio web [Documentación de Aspose.Slides para .NET](https://reference.aspose.com/slides/net/).

## Preguntas frecuentes

### 1. ¿Puedo agregar hipervínculos a otras formas además de marcos de texto?

Sí, puede agregar hipervínculos a varias formas como rectángulos, imágenes y más usando Aspose.Slides para .NET.

### 2. ¿Cómo puedo eliminar un hipervínculo de una forma en una diapositiva de PowerPoint?

Puede eliminar un hipervínculo de una forma configurando el `HyperlinkClick` propiedad a `null`.

### 3. ¿Puedo cambiar la URL del hipervínculo dinámicamente en mi código?

¡Por supuesto! Puedes actualizar la URL de un hipervínculo en cualquier punto del código modificando el `Hyperlink` propiedad.

### 4. ¿Qué otros elementos interactivos puedo agregar a las diapositivas de PowerPoint usando Aspose.Slides?

Aspose.Slides ofrece una amplia gama de funciones interactivas, incluidos botones de acción, elementos multimedia y animaciones.

### 5. ¿Aspose.Slides está disponible para otros lenguajes de programación?

Sí, Aspose.Slides está disponible para varios lenguajes de programación, incluidos Java y Python.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}