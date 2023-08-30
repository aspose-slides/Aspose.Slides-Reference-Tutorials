---
title: Agregar hipervínculo a la diapositiva
linktitle: Agregar hipervínculo a la diapositiva
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda cómo agregar hipervínculos a diapositivas en PowerPoint usando Aspose.Slides para .NET. Mejore las presentaciones con contenido interactivo.
type: docs
weight: 12
url: /es/net/hyperlink-manipulation/add-hyperlink/
---

## Introducción a Aspose.Slides para .NET

Aspose.Slides para .NET es una biblioteca completa que permite a los desarrolladores crear, modificar y manipular presentaciones de PowerPoint sin depender de Microsoft Office. Proporciona una amplia gama de funciones, incluida la adición y administración de hipervínculos en diapositivas.

## Requisitos previos

Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Visual Studio instalado en su sistema.
-  Aspose.Slides para la biblioteca .NET. Puedes descargarlo desde[aquí](https://downloads.aspose.com/slides/net).

## Agregar un hipervínculo a un texto en una diapositiva

1. Cree un nuevo proyecto de C# en Visual Studio.
2. Agregue una referencia a la DLL Aspose.Slides en su proyecto.
3. Utilice el siguiente código para agregar un hipervínculo a un texto en una diapositiva:

```csharp
using Aspose.Slides;

// Cargar la presentación
Presentation presentation = new Presentation("presentation.pptx");

// Acceder a una diapositiva
ISlide slide = presentation.Slides[0];

// Acceder a un cuadro de texto
ITextFrame textFrame = slide.Shapes[0] as ITextFrame;

// Agregue una porción de texto con un hipervínculo
textFrame.Paragraphs[0].Portions[0].Text = "Visit our website!";
textFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new HyperlinkInfo("https://www.ejemplo.com", HyperlinkAction.MouseClick);
```

## Agregar un hipervínculo a una forma en una diapositiva

1. Siga los pasos anteriores para crear un nuevo proyecto C# y agregar la referencia Aspose.Slides.
2. Utilice el siguiente código para agregar un hipervínculo a una forma en una diapositiva:

```csharp
using Aspose.Slides;

// Cargar la presentación
Presentation presentation = new Presentation("presentation.pptx");

// Acceder a una diapositiva
ISlide slide = presentation.Slides[0];

// Acceder a una forma
IShape shape = slide.Shapes[1];

// Agregar un hipervínculo a la forma
shape.HyperlinkClick = new HyperlinkInfo("https://www.ejemplo.com", HyperlinkAction.MouseClick);
```

## Agregar un hipervínculo a una diapositiva

1. Siga los pasos iniciales para configurar su proyecto C# y hacer referencia a la biblioteca Aspose.Slides.
2. Utilice el siguiente código para agregar un hipervínculo a una diapositiva:

```csharp
using Aspose.Slides;

// Cargar la presentación
Presentation presentation = new Presentation("presentation.pptx");

// Acceder a una diapositiva
ISlide slide = presentation.Slides[2];

// Agregar un hipervínculo a la diapositiva
slide.HyperlinkClick = new HyperlinkInfo("https://www.ejemplo.com", HyperlinkAction.MouseClick);
```

## Agregar hipervínculos externos

Además de los hipervínculos internos, también puedes agregar hipervínculos externos a tus diapositivas. Utilice el mismo enfoque que el anterior, pero proporcione la URL externa como destino del hipervínculo.

## Modificar y eliminar hipervínculos

Para modificar un hipervínculo existente o eliminarlo, puede acceder a las propiedades del hipervínculo del elemento de diapositiva respectivo y realizar los cambios necesarios.

## Conclusión

Agregar hipervínculos a las diapositivas usando Aspose.Slides para .NET es un proceso sencillo que puede mejorar enormemente la interactividad de sus presentaciones. Ya sea que desee vincular recursos externos o crear navegación dentro de sus diapositivas, Aspose.Slides proporciona las herramientas que necesita para realizar estas tareas de manera eficiente.

## Preguntas frecuentes

### ¿Cómo elimino un hipervínculo de una parte del texto?

 Para eliminar un hipervínculo de una parte del texto, simplemente puede configurar el`HyperlinkClick` propiedad a`null` por esa porción.

### ¿Puedo agregar hipervínculos a formas que no sean cuadros de texto?

Sí, puede agregar hipervínculos a varias formas, incluidas imágenes y formas personalizadas, utilizando el`HyperlinkClick` propiedad.

### ¿Aspose.Slides es compatible con diferentes formatos de PowerPoint?

Sí, Aspose.Slides admite varios formatos de PowerPoint, incluidos PPTX, PPT y más.

### ¿Cómo puedo probar los hipervínculos en mi presentación?

Puede ejecutar la presentación en un visor o editor de PowerPoint para probar la funcionalidad de los hipervínculos.

### ¿Dónde puedo descargar la biblioteca Aspose.Slides para .NET?

 Puede descargar la biblioteca Aspose.Slides para .NET desde el sitio web de Aspose:[Descargar Aspose.Slides para .NET](https://releases.aspose.com/slides/net).