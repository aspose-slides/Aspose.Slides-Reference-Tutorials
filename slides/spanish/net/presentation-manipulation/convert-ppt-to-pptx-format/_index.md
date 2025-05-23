---
"description": "Aprenda a convertir fácilmente archivos PPT a PPTX con Aspose.Slides para .NET. Guía paso a paso con ejemplos de código para una transformación de formato fluida."
"linktitle": "Convertir formato PPT a PPTX"
"second_title": "API de procesamiento de PowerPoint Aspose.Slides .NET"
"title": "Convertir formato PPT a PPTX"
"url": "/es/net/presentation-manipulation/convert-ppt-to-pptx-format/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Convertir formato PPT a PPTX


Si alguna vez has necesitado convertir archivos de PowerPoint del antiguo formato PPT al nuevo formato PPTX usando .NET, estás en el lugar indicado. En este tutorial paso a paso, te guiaremos en el proceso usando la API de Aspose.Slides para .NET. Con esta potente biblioteca, podrás realizar estas conversiones fácilmente. ¡Comencemos!

## Prerrequisitos

Antes de sumergirnos en el código, asegúrese de tener la siguiente configuración:

- Visual Studio: asegúrese de tener Visual Studio instalado y listo para el desarrollo .NET.
- Aspose.Slides para .NET: Descargue e instale la biblioteca Aspose.Slides para .NET desde [aquí](https://releases.aspose.com/slides/net/).

## Configuración del proyecto

1. Crear un nuevo proyecto: abra Visual Studio y cree un nuevo proyecto C#.

2. Agregar referencia a Aspose.Slides: Haga clic con el botón derecho en su proyecto en el Explorador de soluciones, seleccione "Administrar paquetes NuGet" y busque "Aspose.Slides". Instale el paquete.

3. Importar espacios de nombres requeridos:

```csharp
using Aspose.Slides;
```

## Conversión de PPT a PPTX

Ahora que tenemos nuestro proyecto configurado, escribamos el código para convertir un archivo PPT a PPTX.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

string srcFileName = dataDir + "Conversion PPT to PPTX.ppt";
string destFileName = dataDir + "Conversion PPT to PPTX.pptx";

// Crear una instancia de un objeto de presentación que represente un archivo PPT
Presentation pres = new Presentation(srcFileName);

// Guardar la presentación en formato PPTX
pres.Save(outPath, SaveFormat.Pptx);
```

En este fragmento de código:

- `dataDir` debe reemplazarse con la ruta del directorio donde se encuentra su archivo PPT.
- `outPath` debe reemplazarse con el directorio donde desea guardar el archivo PPTX convertido.
- `srcFileName` es el nombre de su archivo PPT de entrada.
- `destFileName` es el nombre deseado para el archivo PPTX de salida.

## Conclusión

¡Felicitaciones! Has convertido correctamente una presentación de PowerPoint de formato PPT a PPTX con la API de Aspose.Slides para .NET. Esta potente biblioteca simplifica tareas complejas como esta, optimizando tu experiencia de desarrollo en .NET.

Si aún no lo has hecho, [Descargar Aspose.Slides para .NET](https://releases.aspose.com/slides/net/) y explorar más a fondo sus capacidades.

Para más tutoriales y consejos, visita nuestra [documentación](https://reference.aspose.com/slides/net/).

## Preguntas frecuentes

### 1. ¿Qué es Aspose.Slides para .NET?
Aspose.Slides para .NET es una biblioteca .NET que permite a los desarrolladores crear, manipular y convertir presentaciones de PowerPoint mediante programación.

### 2. ¿Puedo convertir otros formatos a PPTX usando Aspose.Slides para .NET?
Sí, Aspose.Slides para .NET admite varios formatos, incluidos PPT, PPTX, ODP y más.

### 3. ¿Aspose.Slides para .NET es gratuito?
No, es una biblioteca comercial, pero puedes explorar una [prueba gratuita](https://releases.aspose.com/) para evaluar sus características.

### 4. ¿Existen otros formatos de documentos compatibles con Aspose.Slides para .NET?
Sí, Aspose.Slides para .NET también admite trabajar con documentos de Word, hojas de cálculo de Excel y otros formatos de archivos.

### 5. ¿Dónde puedo obtener soporte o hacer preguntas sobre Aspose.Slides para .NET?
Puede encontrar respuestas a sus preguntas y buscar apoyo en el [Foros de Aspose.Slides](https://forum.aspose.com/).



{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}