---
title: Agregar desplazamiento de estiramiento a la izquierda para el marco de imagen en Aspose.Slides
linktitle: Agregar desplazamiento de estiramiento a la izquierda para el marco de imagen en Aspose.Slides
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda cómo agregar un desplazamiento elástico hacia la izquierda para un marco de imagen en PowerPoint usando Aspose.Slides para .NET. Guía paso a paso con ejemplo de código fuente completo.
type: docs
weight: 14
url: /es/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/
---

## Introducción a Aspose.Slides para .NET

Aspose.Slides para .NET es una biblioteca completa que permite a los desarrolladores de .NET trabajar con presentaciones de PowerPoint sin la necesidad de Microsoft Office. Proporciona una amplia gama de funciones, que incluyen la creación, edición y manipulación de diapositivas, formas, texto, imágenes y más.

## Requisitos previos

Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

1. Visual Studio instalado en su máquina.
2. Conocimientos básicos de C# y .NET framework.
3.  Aspose.Slides para la biblioteca .NET. Puedes descargarlo desde[aquí](https://releases.aspose.com/slides/net/).

## Configurando el proyecto

Comencemos configurando un nuevo proyecto de C# en Visual Studio:

1. Abra Visual Studio.
2. Haga clic en "Crear un nuevo proyecto".
3. Seleccione "Aplicación de consola (.NET Framework/Core)".
4. Elija un nombre y una ubicación adecuados para su proyecto.
5. Haga clic en "Crear".

A continuación, agregue una referencia a la biblioteca Aspose.Slides para .NET en su proyecto. Haga clic derecho en "Referencias" en el Explorador de soluciones, elija "Administrar paquetes NuGet", busque "Aspose.Slides" e instale el paquete.

## Agregar desplazamiento de estiramiento a la izquierda para el marco de imagen

Para agregar un desplazamiento de estiramiento a la izquierda de un marco de imagen usando Aspose.Slides para .NET, siga estos pasos:

1.  Cargue el archivo de presentación usando`Presentation` clase.
2. Localice la diapositiva que contiene el marco de imagen que desea modificar.
3. Acceda a la forma del marco de la imagen iterando a través de las formas en la diapositiva.
4.  Aplique el desplazamiento de estiramiento hacia la izquierda usando el`PictureFrame` clase.

## Código de ejemplo

```csharp
using Aspose.Slides;
using Aspose.Slides.ShapeManagers;

namespace PictureFrameStretchOffsetExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Cargar la presentación
            using (Presentation presentation = new Presentation("sample.pptx"))
            {
                // Obtenga la primera diapositiva
                ISlide slide = presentation.Slides[0];

                // Iterar a través de las formas en la diapositiva.
                foreach (IShape shape in slide.Shapes)
                {
                    if (shape is IPictureFrame)
                    {
                        IPictureFrame pictureFrame = (IPictureFrame)shape;

                        // Aplicar desplazamiento de estiramiento hacia la izquierda
                        pictureFrame.PictureFormat.StretchOffsetX = -10;
                    }
                }

                // Guardar la presentación modificada
                presentation.Save("output.pptx", SaveFormat.Pptx);
            }
        }
    }
}
```

En este ejemplo, cargamos una presentación, iteramos a través de las formas en la primera diapositiva y, si encontramos una forma de marco de imagen, aplicamos un desplazamiento de estiramiento de -10 hacia la izquierda.

## Probar la aplicación

Para probar la aplicación, siga estos pasos:

1. Asegúrese de tener una presentación de PowerPoint de muestra (`sample.pptx`) con al menos un marco de imagen.
2. Ejecute la aplicación.
3.  La presentación modificada con el desplazamiento de estiramiento agregado se guardará como`output.pptx`.

## Conclusión

En este tutorial, aprendió cómo agregar un desplazamiento de estiramiento hacia la izquierda para un marco de imagen en Aspose.Slides usando .NET. Aspose.Slides para .NET proporciona un potente conjunto de herramientas para manipular mediante programación presentaciones de PowerPoint, lo que permite a los desarrolladores crear presentaciones de diapositivas dinámicas y personalizadas sin problemas.

## Preguntas frecuentes

### ¿Cómo puedo instalar Aspose.Slides para .NET?

 Puede descargar Aspose.Slides para .NET desde el sitio web[aquí](https://releases.aspose.com/slides/net/).

### ¿Puedo usar Aspose.Slides para otras tareas de manipulación de PowerPoint?

¡Absolutamente! Aspose.Slides para .NET ofrece una amplia gama de funciones, incluida la creación, edición y conversión de presentaciones de PowerPoint. Puede explorar su documentación para obtener más detalles y ejemplos.

### ¿Aspose.Slides es compatible con diferentes formatos de PowerPoint?

Sí, Aspose.Slides admite varios formatos de PowerPoint, incluidos PPTX, PPT, POTX y más. También admite la conversión entre diferentes formatos.

### ¿Cómo puedo personalizar otras propiedades de las formas en una presentación?

Puede acceder y modificar varias propiedades de las formas, incluido el texto, la posición, el tamaño, el formato y más, utilizando la biblioteca Aspose.Slides. Consulte la documentación para obtener información completa y ejemplos.

### ¿Puedo utilizar Aspose.Slides con otros lenguajes de programación?

Sí, Aspose.Slides proporciona bibliotecas para varios lenguajes de programación, incluidos Java, Python y más. Puede elegir el que se adapte a su entorno de desarrollo.