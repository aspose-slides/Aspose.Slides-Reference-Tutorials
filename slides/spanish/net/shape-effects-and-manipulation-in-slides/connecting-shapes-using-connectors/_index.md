---
title: Aspose.Slides conecte formas sin problemas en .NET
linktitle: Conectar formas usando conectores en una presentación
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Explore el poder de Aspose.Slides para .NET y conecte formas sin esfuerzo en sus presentaciones. Eleva tus diapositivas con conectores dinámicos.
weight: 29
url: /es/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides conecte formas sin problemas en .NET

## Introducción
En el dinámico mundo de las presentaciones, la capacidad de conectar formas mediante conectores agrega una capa de sofisticación a sus diapositivas. Aspose.Slides para .NET permite a los desarrolladores lograr esto sin problemas. Este tutorial lo guiará a través del proceso, desglosando cada paso para garantizar una comprensión clara.
## Requisitos previos
Antes de sumergirnos en el tutorial, asegúrese de tener lo siguiente:
- Conocimientos básicos de C# y .NET framework.
-  Aspose.Slides para .NET instalado. Si no, descárgalo[aquí](https://releases.aspose.com/slides/net/).
- Un entorno de desarrollo creado.
## Importar espacios de nombres
En su código C#, comience importando los espacios de nombres necesarios:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. Configurar el directorio de documentos
Comience definiendo el directorio de su documento:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Crear una instancia de clase de presentación
Cree una instancia de la clase Presentación para representar su archivo PPTX:
```csharp
using (Presentation input = new Presentation())
{
    // Accediendo a la colección de formas para la diapositiva seleccionada
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. Agrega formas a la diapositiva
Agrega las formas necesarias a tu diapositiva, como Elipse y Rectángulo:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Agregar forma de conector
Incluya una forma de conector en la colección de formas de la diapositiva:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. Conecta formas con conector
Especifique las formas que se conectarán mediante el conector:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. Redirigir el conector
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
¡Felicidades! Ha conectado formas exitosamente usando conectores en diapositivas de presentación usando Aspose.Slides para .NET. Mejore sus presentaciones con esta función avanzada y cautive a su audiencia.
## Preguntas frecuentes
### ¿Aspose.Slides para .NET es compatible con el último marco .NET?
Sí, Aspose.Slides para .NET se actualiza periódicamente para garantizar la compatibilidad con las últimas versiones de .NET Framework.
### ¿Puedo conectar más de dos formas usando un solo conector?
Por supuesto, puedes conectar varias formas ampliando la lógica del conector en tu código.
### ¿Existe alguna limitación en las formas que puedo conectar?
Aspose.Slides para .NET admite la conexión de varias formas, incluidas formas básicas, arte inteligente y formas personalizadas.
### ¿Cómo puedo personalizar la apariencia del conector?
Explore la documentación de Aspose.Slides para conocer métodos para personalizar la apariencia del conector, como el estilo y el color de la línea.
### ¿Existe un foro comunitario para soporte de Aspose.Slides?
 Sí, puedes encontrar ayuda y compartir tus experiencias en el[Foro Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
