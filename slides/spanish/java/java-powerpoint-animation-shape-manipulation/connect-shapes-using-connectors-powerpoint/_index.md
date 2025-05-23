---
"description": "Aprende a conectar formas usando conectores en presentaciones de PowerPoint con Aspose.Slides para Java. Tutorial paso a paso para principiantes."
"linktitle": "Conectar formas usando conectores en PowerPoint"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Conectar formas usando conectores en PowerPoint"
"url": "/es/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Conectar formas usando conectores en PowerPoint

## Introducción
En este tutorial, exploraremos cómo conectar formas mediante conectores en presentaciones de PowerPoint con Aspose.Slides para Java. Sigue estas instrucciones paso a paso para conectar formas de forma eficiente y crear diapositivas visualmente atractivas.
## Prerrequisitos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Conocimientos básicos del lenguaje de programación Java.
- Instale Java Development Kit (JDK) en su sistema.
- He descargado y configurado Aspose.Slides para Java. Si aún no lo has instalado, puedes descargarlo desde [aquí](https://releases.aspose.com/slides/java/).
- Un editor de código como Eclipse o IntelliJ IDEA.

## Importar paquetes
Primero, importe los paquetes necesarios para trabajar con Aspose.Slides en su proyecto Java.
```java
import com.aspose.slides.*;

```
## Paso 1: Crear una instancia de la clase de presentación
Instanciar el `Presentation` clase, que representa el archivo PPTX en el que estás trabajando.
```java
// La ruta al directorio de documentos.                    
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## Paso 2: Acceder a la colección de formas
Acceda a la colección de formas de la diapositiva seleccionada donde desee agregar formas y conectores.
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## Paso 3: Agregar formas
Añade las formas necesarias a la diapositiva. En este ejemplo, añadiremos una elipse y un rectángulo.
```java
// Añadir autoforma Elipse
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// Añadir autoforma Rectángulo
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## Paso 4: Agregar conector
Agregue una forma de conector a la colección de formas de diapositiva.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## Paso 5: Unir las formas a los conectores
Conecte las formas al conector.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Paso 6: Redireccionar el conector
Llame a reroute para establecer la ruta automática más corta entre formas.
```java
connector.reroute();
```
## Paso 7: Guardar la presentación
Guarde la presentación después de conectar las formas usando conectores.
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
Por último, no olvides eliminar el objeto Presentación.
```java
if (input != null) input.dispose();
```
Ahora ha conectado formas exitosamente usando conectores en PowerPoint usando Aspose.Slides para Java.

## Conclusión
En este tutorial, aprendimos a conectar formas mediante conectores en presentaciones de PowerPoint con Aspose.Slides para Java. Siguiendo estos sencillos pasos, podrá mejorar sus presentaciones con diagramas y diagramas de flujo visualmente atractivos.
## Preguntas frecuentes
### ¿Puedo personalizar la apariencia de los conectores en Aspose.Slides para Java?
Sí, puede personalizar varias propiedades de los conectores, como el color, el estilo de línea y el grosor, para adaptarlos a sus necesidades de presentación.
### ¿Aspose.Slides para Java es compatible con todas las versiones de PowerPoint?
Aspose.Slides para Java admite varios formatos de PowerPoint, incluidos PPTX, PPT y ODP.
### ¿Puedo conectar más de dos formas con un solo conector?
Sí, puedes conectar múltiples formas usando conectores complejos proporcionados por Aspose.Slides para Java.
### ¿Aspose.Slides para Java ofrece soporte para agregar texto a las formas?
Por supuesto, puedes agregar texto fácilmente a formas y conectores mediante programación usando Aspose.Slides para Java.
### ¿Hay un foro comunitario o un canal de soporte disponible para los usuarios de Aspose.Slides para Java?
Sí, puede encontrar recursos útiles, hacer preguntas e interactuar con otros usuarios en el foro de Aspose.Slides. [aquí](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}