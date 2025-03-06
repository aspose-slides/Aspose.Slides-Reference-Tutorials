---
title: Agregar hipervínculos a diapositivas en .NET usando Aspose.Slides
linktitle: Agregar hipervínculo a la diapositiva
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda a agregar hipervínculos a diapositivas de PowerPoint con Aspose.Slides para .NET. Mejore sus presentaciones con elementos interactivos.
weight: 12
url: /es/net/hyperlink-manipulation/add-hyperlink/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar hipervínculos a diapositivas en .NET usando Aspose.Slides


En el mundo de las presentaciones digitales, la interactividad es clave. Agregar hipervínculos a sus diapositivas puede hacer que su presentación sea más atractiva e informativa. Aspose.Slides para .NET es una poderosa biblioteca que le permite crear, modificar y manipular presentaciones de PowerPoint mediante programación. En este tutorial, le mostraremos cómo agregar hipervínculos a sus diapositivas usando Aspose.Slides para .NET. 

## Requisitos previos

Antes de sumergirnos en la adición de hipervínculos a las diapositivas, asegúrese de cumplir con los siguientes requisitos previos:

1. Visual Studio: debe tener Visual Studio instalado en su computadora para escribir y ejecutar el código .NET.

2. Aspose.Slides para .NET: Es necesario tener instalada la biblioteca Aspose.Slides para .NET. Puedes descargarlo desde[aquí](https://releases.aspose.com/slides/net/).

3. Conocimientos básicos de C#: será beneficiosa la familiaridad con la programación en C#.

## Importar espacios de nombres

Para comenzar, necesita importar los espacios de nombres necesarios en su proyecto C#. En este caso, necesitará los siguientes espacios de nombres de la biblioteca Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

Ahora, dividamos el proceso de agregar hipervínculos a diapositivas en varios pasos.

## Paso 1: Inicializar la presentación

Primero, cree una nueva presentación usando Aspose.Slides. Así es como puedes hacerlo:

```csharp
using (Presentation presentation = new Presentation())
{
    // Tu código va aquí
}
```

Este código inicializa una nueva presentación de PowerPoint.

## Paso 2: agregar marco de texto

Ahora, agreguemos un marco de texto a su diapositiva. Este marco de texto servirá como elemento en el que se puede hacer clic en su diapositiva. 

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

El código anterior crea una forma automática rectangular y agrega un marco de texto con el texto "Aspose: API de formato de archivo".

## Paso 3: agregar hipervínculo

continuación, agreguemos un hipervínculo al marco de texto que ha creado. Esto hará que se pueda hacer clic en el texto.

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

En este paso, configuramos la URL del hipervínculo en "https://www.aspose.com/" y proporcionamos información sobre herramientas para obtener información adicional. También puede formatear la apariencia del hipervínculo, como se muestra arriba.

## Paso 4: guardar la presentación

Finalmente, guarde su presentación con el hipervínculo agregado.

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

Este código guarda la presentación como "presentación-out.pptx".

Ahora, ha agregado con éxito un hipervínculo a una diapositiva usando Aspose.Slides para .NET.

## Conclusión

En este tutorial, exploramos cómo agregar hipervínculos a diapositivas en presentaciones de PowerPoint usando Aspose.Slides para .NET. Si sigue estos pasos, puede hacer que sus presentaciones sean más interactivas y atractivas, proporcionando enlaces valiosos a recursos o información adicionales.

 Para obtener información y documentación más detallada, visite el[Aspose.Slides para la documentación de .NET](https://reference.aspose.com/slides/net/).

## Preguntas frecuentes

### 1. ¿Puedo agregar hipervínculos a otras formas además de los marcos de texto?

Sí, puede agregar hipervínculos a varias formas como rectángulos, imágenes y más usando Aspose.Slides para .NET.

### 2. ¿Cómo puedo eliminar un hipervínculo de una forma en una diapositiva de PowerPoint?

 Puede eliminar un hipervínculo de una forma configurando el`HyperlinkClick` propiedad a`null`.

### 3. ¿Puedo cambiar la URL del hipervínculo dinámicamente en mi código?

 ¡Absolutamente! Puede actualizar la URL de un hipervínculo en cualquier punto de su código modificando el`Hyperlink` propiedad.

### 4. ¿Qué otros elementos interactivos puedo agregar a las diapositivas de PowerPoint usando Aspose.Slides?

Aspose.Slides ofrece una amplia gama de funciones interactivas, incluidos botones de acción, elementos multimedia y animaciones.

### 5. ¿Aspose.Slides está disponible para otros lenguajes de programación?

Sí, Aspose.Slides está disponible para varios lenguajes de programación, incluidos Java y Python.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
