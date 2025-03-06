---
title: Aplicar efecto de rotación 3D en formas en PowerPoint
linktitle: Aplicar efecto de rotación 3D en formas en PowerPoint
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda cómo aplicar efectos de rotación 3D en formas en PowerPoint usando Aspose.Slides para Java con este completo tutorial paso a paso.
weight: 12
url: /es/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aplicar efecto de rotación 3D en formas en PowerPoint

## Introducción
¿Estás listo para llevar tus presentaciones de PowerPoint al siguiente nivel? Agregar efectos de rotación 3D puede hacer que tus diapositivas sean más dinámicas y atractivas. Si es un desarrollador experimentado o recién está comenzando, este tutorial paso a paso le mostrará cómo aplicar efectos de rotación 3D a formas en PowerPoint usando Aspose.Slides para Java. ¡Vamos a sumergirnos de lleno!
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente en su lugar:
1.  Kit de desarrollo de Java (JDK): asegúrese de tener JDK instalado en su sistema. Puedes descargarlo desde el[sitio web de oráculo](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides para Java: descargue la última versión de Aspose.Slides para Java desde[enlace de descarga](https://releases.aspose.com/slides/java/).
3. Entorno de desarrollo integrado (IDE): utilice un IDE como IntelliJ IDEA o Eclipse para codificar.
4.  Una licencia válida: si no tiene una licencia, puede obtener una[licencia temporal](https://purchase.aspose.com/temporary-license/) para probar las funciones.
## Importar paquetes
Primero, importemos los paquetes necesarios en su proyecto Java. Estas importaciones te ayudarán a manejar presentaciones y formas con Aspose.Slides.
```java
import com.aspose.slides.*;

```
## Paso 1: configura tu proyecto
Antes de profundizar en el código, configure el entorno de su proyecto. Asegúrese de haber agregado Aspose.Slides para Java a las dependencias de su proyecto.
Agregue Aspose.Slides a su proyecto:
1.  Descargue los archivos JAR de Aspose.Slides desde[pagina de descarga](https://releases.aspose.com/slides/java/).
2. Agregue estos archivos JAR a la ruta de compilación de su proyecto.
## Paso 2: crea una nueva presentación de PowerPoint
En este paso, crearemos una nueva presentación de PowerPoint.
```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Crear una instancia de la clase Presentación
Presentation pres = new Presentation();
```
Este fragmento de código inicializa un nuevo objeto de presentación donde agregaremos nuestras formas.
## Paso 3: agrega una forma de rectángulo
A continuación, agreguemos una forma de rectángulo a la primera diapositiva.
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
Este código agrega una forma de rectángulo en la posición y el tamaño especificados en la primera diapositiva.
## Paso 4: aplicar rotación 3D al rectángulo
Ahora, apliquemos un efecto de rotación 3D a la forma del rectángulo.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Aquí, configuramos la profundidad, los ángulos de rotación de la cámara, el tipo de cámara y el tipo de iluminación para darle a nuestro rectángulo una apariencia 3D.
## Paso 5: agrega una forma de línea
Agreguemos otra forma, esta vez una línea, a la diapositiva.
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
Este código coloca una forma de línea en la diapositiva.
## Paso 6: aplicar rotación 3D a la línea
Finalmente, aplicaremos un efecto de rotación 3D a la forma de la línea.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
De manera similar al rectángulo, configuramos las propiedades 3D para la forma de la línea.
## Paso 7: guarde la presentación
Después de agregar y configurar sus formas, guarde la presentación.
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
Este código guarda su presentación con el nombre de archivo especificado en el formato deseado.
## Conclusión
 ¡Felicidades! Ha aplicado con éxito efectos de rotación 3D a formas en una presentación de PowerPoint usando Aspose.Slides para Java. Si sigue estos pasos, podrá crear presentaciones dinámicas y visualmente atractivas. Para una mayor personalización y funciones más avanzadas, consulte la[Documentación de Aspose.Slides](https://reference.aspose.com/slides/java/).
## Preguntas frecuentes
### ¿Qué es Aspose.Slides para Java?
Aspose.Slides para Java es una potente API para crear, modificar y manipular presentaciones de PowerPoint mediante programación.
### ¿Puedo probar Aspose.Slides para Java gratis?
 Sí, puedes conseguir un[prueba gratis](https://releases.aspose.com/) o un[licencia temporal](https://purchase.aspose.com/temporary-license/) para probar las características.
### ¿A qué tipos de formas puedo agregar efectos 3D en Aspose.Slides?
Puede agregar efectos 3D a varias formas, como rectángulos, líneas, elipses y formas personalizadas.
### ¿Cómo obtengo soporte para Aspose.Slides para Java?
 Puedes visitar el[Foro de soporte](https://forum.aspose.com/c/slides/11) para obtener ayuda y discutir cualquier problema.
### ¿Puedo utilizar Aspose.Slides para Java en proyectos comerciales?
 Sí, pero necesitas comprar una licencia. Puedes comprar uno en[pagina de compra](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
