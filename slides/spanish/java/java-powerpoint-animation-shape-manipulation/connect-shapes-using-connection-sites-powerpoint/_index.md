---
"description": "Aprende a conectar formas en PowerPoint con Aspose.Slides para Java. Automatiza tus presentaciones fácilmente."
"linktitle": "Conectar formas mediante sitios de conexión en PowerPoint"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Conectar formas mediante sitios de conexión en PowerPoint"
"url": "/es/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Conectar formas mediante sitios de conexión en PowerPoint

## Introducción
En este tutorial, exploraremos cómo conectar formas mediante sitios de conexión en PowerPoint con Aspose.Slides para Java. Esta potente biblioteca nos permite manipular presentaciones de PowerPoint mediante programación, lo que hace que tareas como conectar formas sean fluidas y eficientes.
## Prerrequisitos
Antes de comenzar, asegúrese de tener lo siguiente:
1. Kit de desarrollo de Java (JDK): Asegúrese de tener Java instalado en su sistema. Puede descargarlo e instalarlo desde [sitio web](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2. Aspose.Slides para Java: Descargue e instale Aspose.Slides para Java desde [página de descarga](https://releases.aspose.com/slides/java/).
3. Entorno de desarrollo integrado (IDE): elija un IDE para el desarrollo de Java, como IntelliJ IDEA, Eclipse o NetBeans.

## Importar paquetes
Para comenzar, importe los paquetes necesarios en su proyecto Java:
```java
import com.aspose.slides.*;

```
## Paso 1: Acceder a la colección de formas
Acceda a la colección de formas de la diapositiva seleccionada:
```java
// La ruta al directorio de documentos.                    
String dataDir = "Your Document Directory";
// Crear una instancia de la clase de presentación que representa el archivo PPTX
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## Paso 2: Agregar la forma del conector
Agregue una forma de conector a la colección de formas de diapositiva:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## Paso 3: Agregar autoformas
Agregue formas automáticas como elipse y rectángulo:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Paso 4: Unir formas a los conectores
Une las formas al conector:
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Paso 5: Configuración del índice del sitio de conexión
Establezca el índice del sitio de conexión deseado para las formas:
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## Conclusión
En este tutorial, aprendimos a conectar formas mediante puntos de conexión en PowerPoint con Aspose.Slides para Java. Con este conocimiento, ahora puedes automatizar y personalizar tus presentaciones de PowerPoint fácilmente.
## Preguntas frecuentes
### ¿Se puede utilizar Aspose.Slides para Java para otras tareas de manipulación de PowerPoint?
Sí, Aspose.Slides para Java proporciona una amplia gama de funcionalidades para crear, editar y convertir presentaciones de PowerPoint.
### ¿Aspose.Slides para Java es de uso gratuito?
Aspose.Slides para Java es una biblioteca comercial, pero puedes explorar sus funciones con una prueba gratuita. Visita [aquí](https://releases.aspose.com/) Para empezar.
### ¿Puedo obtener soporte si encuentro algún problema al usar Aspose.Slides para Java?
Sí, puedes obtener ayuda en los foros de la comunidad de Aspose [aquí](https://forum.aspose.com/c/slides/11).
### ¿Hay licencias temporales disponibles para Aspose.Slides para Java?
Sí, hay licencias temporales disponibles para fines de prueba y evaluación. Puede obtener una [aquí](https://purchase.aspose.com/temporary-license/).
### ¿Dónde puedo comprar una licencia de Aspose.Slides para Java?
Puede comprar una licencia desde el sitio web de Aspose [aquí](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}