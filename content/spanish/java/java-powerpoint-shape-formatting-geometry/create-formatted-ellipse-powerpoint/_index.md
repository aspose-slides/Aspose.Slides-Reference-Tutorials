---
title: Crear elipse formateada en PowerPoint
linktitle: Crear elipse formateada en PowerPoint
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda cómo crear una elipse formateada en PowerPoint usando Aspose.Slides para Java con nuestra guía detallada paso a paso.
type: docs
weight: 17
url: /es/java/java-powerpoint-shape-formatting-geometry/create-formatted-ellipse-powerpoint/
---
## Introducción
Bienvenido a este completo tutorial sobre cómo crear una elipse formateada en PowerPoint usando Aspose.Slides para Java. Aspose.Slides es una poderosa biblioteca que permite a los desarrolladores manipular archivos de PowerPoint mediante programación. Ya sea que esté automatizando la generación de diapositivas o mejorando presentaciones con formas personalizadas, esta guía lo guiará en cada paso, asegurándole que pueda agregar una elipse perfectamente formateada a sus diapositivas con facilidad. ¡Profundicemos y veamos cómo podemos lograrlo!
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1. Kit de desarrollo de Java (JDK): asegúrese de tener instalado JDK 1.6 o superior.
2.  Aspose.Slides para Java: descargue la última versión desde[Aspose.Slides para Java](https://releases.aspose.com/slides/java/).
3. Entorno de desarrollo integrado (IDE): utilice un IDE como IntelliJ IDEA o Eclipse.
4. Conocimientos básicos de Java: se requiere familiaridad con la programación Java.
## Importar paquetes
Para comenzar a usar Aspose.Slides, necesita importar los paquetes necesarios. Así es como puedes hacerlo:
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.io.File;
```
## Paso 1: configure su directorio de proyectos
Primero, necesita un directorio para almacenar sus archivos de PowerPoint.
### Crear directorio
```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Cree un directorio si aún no está presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
 Asegúrese de reemplazar`"Your Document Directory"` con la ruta real donde desea almacenar sus archivos.
## Paso 2: Inicialice la presentación
Ahora, cree una instancia de la clase Presentación, que representa el archivo de PowerPoint.
```java
// Crear una instancia de la clase de presentación que representa el PPTX
Presentation pres = new Presentation();
```
## Paso 3: obtenga la primera diapositiva
A continuación, obtenga la primera diapositiva de la presentación donde agregará la elipse.
```java
// Obtenga la primera diapositiva
ISlide sld = pres.getSlides().get_Item(0);
```
## Paso 4: agrega una forma de elipse
Agregue una forma automática del tipo elipse a la diapositiva.
```java
// Agregar autoforma de tipo elipse
IShape shp = sld.getShapes().addAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
 Aquí,`50, 150, 150, 50` son las coordenadas y el tamaño de la elipse (posición x, posición y, ancho, alto).
## Paso 5: aplicar formato a la elipse
Ahora, aplica algo de formato a la elipse. Estableceremos un color de relleno sólido y un color de línea.
### Establecer color de relleno
```java
// Aplicar algo de formato a la forma de elipse.
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
### Establecer color y ancho de línea
```java
// Aplicar algo de formato a la línea de Elipse.
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
## Paso 6: guarde la presentación
Finalmente, guarde la presentación en su directorio especificado.
```java
// Escriba el archivo PPTX en el disco
pres.save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
## Paso 7: Deseche el objeto de presentación
Deseche el objeto de presentación para liberar recursos.
```java
finally {
    if (pres != null) pres.dispose();
}
```
## Conclusión
¡Felicidades! Ha creado con éxito una elipse formateada en una presentación de PowerPoint utilizando Aspose.Slides para Java. Este tutorial lo guió a través de la configuración de su proyecto, agregando una elipse, aplicando formato y guardando su presentación. Con estas habilidades, ahora puede mejorar sus diapositivas de PowerPoint mediante programación, haciendo que sus presentaciones sean más dinámicas y visualmente atractivas.
## Preguntas frecuentes
### ¿Qué es Aspose.Slides para Java?
Aspose.Slides para Java es una poderosa biblioteca que permite a los desarrolladores crear, modificar y administrar presentaciones de PowerPoint mediante programación.
### ¿Puedo usar Aspose.Slides para Java con cualquier IDE?
Sí, puede utilizar Aspose.Slides para Java con cualquier IDE de Java como IntelliJ IDEA, Eclipse o NetBeans.
### ¿Necesito una licencia para Aspose.Slides?
 Sí, Aspose.Slides es un producto comercial y necesita una licencia para su funcionalidad completa. Puedes obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).
### ¿Dónde puedo encontrar más documentación sobre Aspose.Slides para Java?
Puede encontrar documentación detallada en Aspose.Slides para Java[página de documentación](https://reference.aspose.com/slides/java/).
### ¿Hay soporte disponible para Aspose.Slides?
 Sí, Aspose ofrece soporte a través de su[foro](https://forum.aspose.com/c/slides/11).