---
title: Conecte formas usando sitios de conexión en PowerPoint
linktitle: Conecte formas usando sitios de conexión en PowerPoint
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda cómo conectar formas en PowerPoint usando Aspose.Slides para Java. Automatiza tus presentaciones sin esfuerzo.
weight: 19
url: /es/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Conecte formas usando sitios de conexión en PowerPoint

## Introducción
En este tutorial, exploraremos cómo conectar formas usando sitios de conexión en PowerPoint usando Aspose.Slides para Java. Esta poderosa biblioteca nos permite manipular presentaciones de PowerPoint mediante programación, haciendo que tareas como conectar formas sean fluidas y eficientes.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
1.  Kit de desarrollo de Java (JDK): asegúrese de tener Java instalado en su sistema. Puedes descargarlo e instalarlo desde[sitio web](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides para Java: descargue e instale Aspose.Slides para Java desde[pagina de descarga](https://releases.aspose.com/slides/java/).
3. Entorno de desarrollo integrado (IDE): elija un IDE para el desarrollo de Java, como IntelliJ IDEA, Eclipse o NetBeans.

## Importar paquetes
Para comenzar, importe los paquetes necesarios a su proyecto Java:
```java
import com.aspose.slides.*;

```
## Paso 1: acceder a la colección de formas
Accede a la colección de formas para la diapositiva seleccionada:
```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Crear una instancia de la clase de presentación que representa el archivo PPTX
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## Paso 2: agregar forma de conector
Agregue una forma de conector a la colección de formas de diapositivas:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## Paso 3: agregar autoformas
Agregue formas automáticas como elipse y rectángulo:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Paso 4: unir formas a conectores
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
En este tutorial, aprendimos cómo conectar formas usando sitios de conexión en PowerPoint usando Aspose.Slides para Java. Con este conocimiento, ahora puedes automatizar y personalizar tus presentaciones de PowerPoint con facilidad.
## Preguntas frecuentes
### ¿Se puede utilizar Aspose.Slides para Java para otras tareas de manipulación de PowerPoint?
Sí, Aspose.Slides para Java proporciona una amplia gama de funcionalidades para crear, editar y convertir presentaciones de PowerPoint.
### ¿Aspose.Slides para Java es de uso gratuito?
 Aspose.Slides para Java es una biblioteca comercial, pero puedes explorar sus funciones con una prueba gratuita. Visita[aquí](https://releases.aspose.com/) Para empezar.
### ¿Puedo obtener asistencia si encuentro algún problema al utilizar Aspose.Slides para Java?
 Sí, puede obtener soporte en los foros de la comunidad Aspose.[aquí](https://forum.aspose.com/c/slides/11).
### ¿Hay licencias temporales disponibles para Aspose.Slides para Java?
 Sí, hay licencias temporales disponibles para fines de prueba y evaluación. Puedes obtener uno[aquí](https://purchase.aspose.com/temporary-license/).
### ¿Dónde puedo comprar una licencia de Aspose.Slides para Java?
Puede comprar una licencia desde el sitio web de Aspose[aquí](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
