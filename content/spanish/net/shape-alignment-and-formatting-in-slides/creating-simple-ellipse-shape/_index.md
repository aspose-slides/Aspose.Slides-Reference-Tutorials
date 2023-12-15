---
title: Crear una forma de elipse simple en diapositivas de presentación con Aspose.Slides
linktitle: Crear una forma de elipse simple en diapositivas de presentación con Aspose.Slides
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda a crear una forma de elipse simple en diapositivas de presentación usando Aspose.Slides para .NET. Esta guía paso a paso proporciona código fuente e instrucciones para agregar, personalizar y guardar formas de elipse.
type: docs
weight: 11
url: /es/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/
---

## Introducción a la creación de formas de elipse simples en diapositivas de presentación

Si está buscando mejorar las diapositivas de su presentación agregando formas visualmente atractivas, Aspose.Slides para .NET proporciona una solución poderosa para lograrlo. En esta guía paso a paso, lo guiaremos a través del proceso de creación de una forma de elipse simple en las diapositivas de su presentación usando Aspose.Slides para .NET.

## Requisitos previos

Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Visual Studio o cualquier otro entorno de desarrollo .NET instalado.
-  Aspose.Slides para la biblioteca .NET. Puedes descargarlo desde[aquí](https://releases.aspose.com/slides/net/).

## Configurando su proyecto

1. Cree un nuevo proyecto de Visual Studio o abra uno existente.
2. Agregue una referencia a la biblioteca Aspose.Slides para .NET en su proyecto.

## Creando una presentación

Para comenzar, creemos una nueva presentación donde agregaremos nuestra forma de elipse.

```csharp
using Aspose.Slides;

// Crear una nueva presentación
Presentation presentation = new Presentation();
```

## Agregar una forma de elipse

Ahora que tenemos nuestra presentación lista, agreguemos una forma de elipse a una diapositiva.

```csharp
// Accede a la primera diapositiva de la presentación.
ISlide slide = presentation.Slides[0];

// Definir dimensiones y posición de elipse
float x = 100;   // coordenada x
float y = 100;   // Coordenada Y
float width = 200;  // Ancho
float height = 100; // Altura

// Agrega la forma de elipse a la diapositiva.
IAutoShape ellipseShape = slide.Shapes.AddAutoShape(ShapeType.Ellipse, x, y, width, height);
```

## Personalizando la elipse

Puedes personalizar la apariencia de la forma de elipse usando varias propiedades.

```csharp
// Establecer el color de relleno de la elipse.
ellipseShape.FillFormat.SolidFillColor.Color = Color.Blue;

//Establecer el color y el ancho del contorno
ellipseShape.LineFormat.FillFormat.SolidFillColor.Color = Color.Red;
ellipseShape.LineFormat.Width = 2;

// Agregar un marco de texto a la elipse
ITextFrame textFrame = ellipseShape.TextFrame;
textFrame.Text = "Hello, Aspose.Slides!";
```

## Guardar la presentación

Después de agregar y personalizar la forma de elipse, es hora de guardar la presentación.

```csharp
// guardar la presentación
presentation.Save("EllipsePresentation.pptx", SaveFormat.Pptx);
```

## Conclusión

¡Felicidades! Ha creado con éxito una forma de elipse simple en las diapositivas de su presentación usando Aspose.Slides para .NET. Esta guía cubrió el proceso de configurar su proyecto, crear una presentación, agregar una forma de elipse, personalizar su apariencia y guardar la presentación final.

## Preguntas frecuentes

### ¿Cómo puedo cambiar la posición de la forma de elipse?

 Puedes modificar el`x` y`y` coordenadas al agregar la forma de elipse para ajustar su posición en la diapositiva.

### ¿Puedo cambiar el color del contorno de la elipse?

 Sí, puedes configurar el color del contorno usando el`LineFormat.FillFormat.SolidFillColor.Color` propiedad.

### ¿Es posible agregar texto dentro de la elipse?

 ¡Absolutamente! Puedes agregar texto a la forma de elipse usando el`TextFrame.Text` propiedad.

### ¿Qué otras formas puedo crear usando Aspose.Slides para .NET?

Aspose.Slides para .NET admite varias formas, incluidos rectángulos, líneas, flechas y más.

### ¿Dónde puedo encontrar más información sobre Aspose.Slides para .NET?

Para obtener documentación detallada y ejemplos, consulte la[Aspose.Slides para la documentación de .NET](https://reference.aspose.com/slides/net/).