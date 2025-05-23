---
"description": "Explora el poder de Aspose.Slides para .NET y conecta formas fácilmente en tus presentaciones. Mejora tus diapositivas con conectores dinámicos."
"linktitle": "Conexión de formas mediante conectores en la presentación"
"second_title": "API de procesamiento de PowerPoint Aspose.Slides .NET"
"title": "Aspose.Slides&#58; conecta formas sin problemas en .NET"
"url": "/es/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/"
"weight": 29
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides: conecta formas sin problemas en .NET

## Introducción
En el dinámico mundo de las presentaciones, la posibilidad de conectar formas mediante conectores añade un toque de sofisticación a las diapositivas. Aspose.Slides para .NET permite a los desarrolladores lograrlo sin problemas. Este tutorial le guiará a través del proceso, detallando cada paso para garantizar una comprensión clara.
## Prerrequisitos
Antes de sumergirnos en el tutorial, asegúrese de tener lo siguiente:
- Conocimientos básicos de C# y .NET framework.
- Aspose.Slides para .NET está instalado. Si no, descárguelo. [aquí](https://releases.aspose.com/slides/net/).
- Un entorno de desarrollo configurado.
## Importar espacios de nombres
En su código C#, comience importando los espacios de nombres necesarios:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. Configurar el directorio de documentos
Comience por definir el directorio para su documento:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Crear una instancia de la clase de presentación
Cree una instancia de la clase Presentación para representar su archivo PPTX:
```csharp
using (Presentation input = new Presentation())
{
    // Acceder a la colección de formas para la diapositiva seleccionada
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. Agregar formas a la diapositiva
Añade las formas necesarias a tu diapositiva, como Elipse y Rectángulo:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Agregar forma de conector
Incluir una forma de conector en la colección de formas de la diapositiva:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. Conecte formas con el conector
Especifique las formas que se conectarán mediante el conector:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. Redireccionar el conector
Llame al método de redireccionamiento para establecer la ruta más corta automática entre formas:
```csharp
connector.Reroute();
```
## 7. Guardar presentación
Guarde su presentación para ver las formas conectadas:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## Conclusión
¡Felicitaciones! Has conectado formas usando conectores en las diapositivas de tu presentación con Aspose.Slides para .NET. Mejora tus presentaciones con esta función avanzada y cautiva a tu audiencia.
## Preguntas frecuentes
### ¿Aspose.Slides para .NET es compatible con el último marco .NET?
Sí, Aspose.Slides para .NET se actualiza periódicamente para garantizar la compatibilidad con las últimas versiones de .NET Framework.
### ¿Puedo conectar más de dos formas usando un solo conector?
Por supuesto, puedes conectar múltiples formas extendiendo la lógica del conector en tu código.
### ¿Existen limitaciones en las formas que puedo conectar?
Aspose.Slides para .NET admite la conexión de varias formas, incluidas formas básicas, arte inteligente y formas personalizadas.
### ¿Cómo puedo personalizar la apariencia del conector?
Explore la documentación de Aspose.Slides para conocer métodos para personalizar la apariencia del conector, como el estilo de línea y el color.
### ¿Existe un foro comunitario para soporte de Aspose.Slides?
Sí, puedes encontrar ayuda y compartir tus experiencias en el [Foro de Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}