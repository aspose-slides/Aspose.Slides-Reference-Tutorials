---
"description": "Aprenda a agregar marcos de imagen con altura de escala relativa en Aspose.Slides para .NET. Siga esta guía paso a paso para crear presentaciones impecables."
"linktitle": "Cómo agregar marcos de imagen con altura de escala relativa en Aspose.Slides"
"second_title": "API de procesamiento de PowerPoint Aspose.Slides .NET"
"title": "Tutorial para añadir marcos de fotos con Aspose.Slides .NET"
"url": "/es/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tutorial para añadir marcos de fotos con Aspose.Slides .NET

## Introducción
Aspose.Slides para .NET es una potente biblioteca que permite a los desarrolladores crear, manipular y convertir presentaciones de PowerPoint en sus aplicaciones .NET sin esfuerzo. En este tutorial, profundizaremos en el proceso de agregar marcos de imagen con altura de escala relativa usando Aspose.Slides para .NET. Sigue esta guía paso a paso para mejorar tus habilidades de creación de presentaciones.
## Prerrequisitos
Antes de comenzar, asegúrese de tener lo siguiente:
- Conocimientos básicos del lenguaje de programación C#.
- Visual Studio o cualquier otro entorno de desarrollo C# preferido instalado.
- Se agregó la biblioteca Aspose.Slides para .NET a su proyecto.
## Importar espacios de nombres
Comience importando los espacios de nombres necesarios a su código C#. Este paso garantiza el acceso a las clases y funcionalidades de la biblioteca Aspose.Slides.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Paso 1: Configura tu proyecto
Empieza creando un nuevo proyecto de C# en tu entorno de desarrollo preferido. Asegúrate de añadir la biblioteca Aspose.Slides para .NET a tu proyecto haciendo referencia a ella.
## Paso 2: Cargar la presentación y la imagen
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    // Cargar imagen para agregarla a la colección de imágenes de la presentación
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // ...
}
```
En este paso, creamos un nuevo objeto de presentación y cargamos la imagen que queremos agregar a la presentación.
## Paso 3: Agregar marco de imagen a la diapositiva
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
Ahora, añade un marco de imagen a la primera diapositiva de la presentación. Ajusta los parámetros como el tipo de forma, la posición y las dimensiones según tus necesidades.
## Paso 4: Establecer el ancho y la altura de la escala relativa
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
Establezca la altura y el ancho de la escala relativa del marco de imagen para lograr el efecto de escala deseado.
## Paso 5: Guardar la presentación
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
Por último, guarde la presentación con el marco de imagen agregado en el formato de salida especificado.
## Conclusión
¡Felicitaciones! Has aprendido a agregar marcos de imagen con altura de escala relativa usando Aspose.Slides para .NET. Experimenta con diferentes imágenes, posiciones y escalas para crear presentaciones visualmente atractivas y adaptadas a tus necesidades.
## Preguntas frecuentes
### ¿Puedo usar Aspose.Slides para .NET con otros lenguajes de programación?
Aspose.Slides admite principalmente lenguajes .NET, pero puede explorar otros productos Aspose para comprobar la compatibilidad con diferentes plataformas.
### ¿Dónde puedo encontrar documentación detallada de Aspose.Slides para .NET?
Consulte la [documentación](https://reference.aspose.com/slides/net/) para obtener información completa y ejemplos.
### ¿Hay una prueba gratuita disponible para Aspose.Slides para .NET?
Sí, puedes conseguir uno [prueba gratuita](https://releases.aspose.com/) para evaluar las capacidades de la biblioteca.
### ¿Cómo puedo obtener soporte para Aspose.Slides para .NET?
Visita el [Foro de Aspose.Slides](https://forum.aspose.com/c/slides/11) buscar ayuda de la comunidad y de los expertos de Aspose.
### ¿Dónde puedo comprar Aspose.Slides para .NET?
Puede comprar Aspose.Slides para .NET en [página de compra](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}