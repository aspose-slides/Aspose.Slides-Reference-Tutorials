---
"description": "Aprende a crear elipses impactantes en tus presentaciones con Aspose.Slides para .NET. ¡Pasos sencillos para un diseño dinámico!"
"linktitle": "Crear una elipse simple en diapositivas de presentación con Aspose.Slides"
"second_title": "API de procesamiento de PowerPoint Aspose.Slides .NET"
"title": "Cree una forma elipse fácilmente con Aspose.Slides .NET"
"url": "/es/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Cree una forma elipse fácilmente con Aspose.Slides .NET

## Introducción
En el dinámico mundo del diseño de presentaciones, incorporar formas como elipses puede aportar un toque de creatividad y profesionalismo. Aspose.Slides para .NET ofrece una potente solución para manipular archivos de presentación mediante programación. Este tutorial le guiará en el proceso de creación de una elipse simple en diapositivas de presentación con Aspose.Slides para .NET.
## Prerrequisitos
Antes de sumergirse en el tutorial, asegúrese de tener los siguientes requisitos previos:
- Aspose.Slides para .NET: Asegúrese de tener instalada la biblioteca Aspose.Slides para .NET. Puede descargarla desde [página de lanzamientos](https://releases.aspose.com/slides/net/).
- Entorno de desarrollo: configure un entorno de desarrollo .NET en su máquina.
## Importar espacios de nombres
En su proyecto .NET, comience importando los espacios de nombres necesarios:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Estos espacios de nombres proporcionan las clases y los métodos esenciales necesarios para trabajar con diapositivas y formas de presentaciones.
## Paso 1: Configurar la presentación
Comience creando una nueva presentación y accediendo a la primera diapositiva. Agregue el siguiente código para lograrlo:
```csharp
// La ruta al directorio de documentos.
string dataDir = "Your Document Directory";
// Crear directorio si aún no está presente.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// Crear una instancia de la clase Presentación
using (Presentation pres = new Presentation())
{
    // Obtener la primera diapositiva
    ISlide sld = pres.Slides[0];
```
Este código inicializa una nueva presentación y selecciona la primera diapositiva para una mayor manipulación.
## Paso 2: Agregar forma de elipse
Ahora, agreguemos una forma de elipse a la diapositiva usando el `AddAutoShape` método:
```csharp
// Añadir autoforma de tipo elipse
sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
Esta línea de código crea una forma de elipse en las coordenadas (50, 150) con un ancho de 150 unidades y una altura de 50 unidades.
## Paso 3: Guardar la presentación
Por último, guarde la presentación modificada en el disco con un nombre de archivo específico utilizando el siguiente código:
```csharp
// Escribe el archivo PPTX en el disco
pres.Save(dataDir + "EllipseShp1_out.pptx", SaveFormat.Pptx);
```
Este paso garantiza que los cambios se mantengan y que pueda ver la presentación resultante con la forma de elipse recién agregada.
## Conclusión
¡Felicitaciones! Has creado con éxito una elipse simple en una diapositiva de presentación con Aspose.Slides para .NET. Este tutorial proporciona los fundamentos del trabajo con formas, la configuración de presentaciones y el guardado de los archivos modificados.
---
## Preguntas frecuentes
### ¿Puedo personalizar aún más la forma de la elipse?
Sí, puede modificar varias propiedades de la forma de elipse, como el color, el tamaño y la posición, para satisfacer sus requisitos de diseño específicos.
### ¿Aspose.Slides es compatible con los últimos frameworks .NET?
Sí, Aspose.Slides se actualiza periódicamente para garantizar la compatibilidad con los últimos marcos .NET.
### ¿Dónde puedo encontrar más tutoriales y ejemplos para Aspose.Slides?
Visita el [documentación](https://reference.aspose.com/slides/net/) para guías completas y ejemplos.
### ¿Cómo puedo obtener una licencia temporal para Aspose.Slides?
Sigue el [enlace de licencia temporal](https://purchase.aspose.com/temporary-license/) para solicitar una licencia temporal para fines de prueba.
### ¿Necesita ayuda o tiene preguntas específicas?
Visita el [Foro de soporte de Aspose.Slides](https://forum.aspose.com/c/slides/11) para obtener ayuda de la comunidad y de los expertos.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}