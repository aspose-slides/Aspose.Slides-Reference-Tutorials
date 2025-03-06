---
title: Crear marco de zoom en PowerPoint
linktitle: Crear marco de zoom en PowerPoint
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a crear atractivos marcos de zoom en PowerPoint usando Aspose.Slides para Java. Siga nuestra guía para agregar elementos interactivos a sus presentaciones.
weight: 17
url: /es/java/java-powerpoint-shape-thumbnail-creation/create-zoom-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introducción
Crear presentaciones atractivas de PowerPoint es un arte y, a veces, las adiciones más pequeñas pueden marcar una gran diferencia. Una de esas características es el Zoom Frame, que le permite ampliar diapositivas o imágenes específicas, creando una presentación dinámica e interactiva. En este tutorial, lo guiaremos a través del proceso de creación de un marco de zoom en PowerPoint usando Aspose.Slides para Java.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de tener lo siguiente:
- Kit de desarrollo de Java (JDK) instalado en su sistema.
-  Aspose.Slides para la biblioteca Java. Puedes descargarlo desde[aquí](https://releases.aspose.com/slides/java/).
- Un entorno de desarrollo integrado (IDE) como IntelliJ IDEA o Eclipse.
- Conocimientos básicos de programación Java.
## Importar paquetes
Para empezar, necesita importar los paquetes necesarios en su proyecto Java. Estas importaciones proporcionarán acceso a las funcionalidades de Aspose.Slides necesarias para este tutorial.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;
```
## Paso 1: configurar la presentación
Primero, necesitamos crear una nueva presentación y agregarle un par de diapositivas.
```java
// Nombre del archivo de salida
String resultPath = "ZoomFramePresentation.pptx";
// Ruta a la imagen de origen
String imagePath = "Your Document Directory/aspose-logo.jpg";
Presentation pres = new Presentation();
try {
    // Agregar nuevas diapositivas a la presentación
    ISlide slide2 = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
    ISlide slide3 = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
```
## Paso 2: personalizar los fondos de las diapositivas
Queremos que nuestras diapositivas sean visualmente distintas agregando colores de fondo.
### Configuración del fondo para la segunda diapositiva
```java
    // Crea un fondo para la segunda diapositiva.
    slide2.getBackground().setType(BackgroundType.OwnBackground);
    slide2.getBackground().getFillFormat().setFillType(FillType.Solid);
    slide2.getBackground().getFillFormat().getSolidFillColor().setColor(Color.CYAN);
    // Crea un cuadro de texto para la segunda diapositiva.
    IAutoShape autoshape = slide2.getShapes().addAutoShape(ShapeType.Rectangle, 100, 200, 500, 200);
    autoshape.getTextFrame().setText("Second Slide");
```
### Configuración del fondo para la tercera diapositiva
```java
    // Crea un fondo para la tercera diapositiva.
    slide3.getBackground().setType(BackgroundType.OwnBackground);
    slide3.getBackground().getFillFormat().setFillType(FillType.Solid);
    slide3.getBackground().getFillFormat().getSolidFillColor().setColor(Color.DARK_GRAY);
    // Crea un cuadro de texto para la tercera diapositiva.
    autoshape = slide3.getShapes().addAutoShape(ShapeType.Rectangle, 100, 200, 500, 200);
    autoshape.getTextFrame().setText("Third Slide");
```
## Paso 3: agregar marcos de zoom
Ahora, agreguemos Zoom Frames a la presentación. Agregaremos un marco de zoom con una vista previa de diapositiva y otro con una imagen personalizada.
### Agregar marco de zoom con vista previa de diapositiva
```java
    // Agregue objetos ZoomFrame con vista previa de diapositivas
    IZoomFrame zoomFrame1 = pres.getSlides().get_Item(0).getShapes().addZoomFrame(20, 20, 250, 200, slide2);
```
### Agregar marco de zoom con imagen personalizada
```java
    // Agregue objetos ZoomFrame con una imagen personalizada
    byte[] imageBytes = Files.readAllBytes(Paths.get(imagePath));
    IPPImage image = pres.getImages().addImage(imageBytes);
    IZoomFrame zoomFrame2 = pres.getSlides().get_Item(0).getShapes().addZoomFrame(200, 250, 250, 100, slide3, image);
```
## Paso 4: Personalizar los marcos de zoom
Para que nuestros Zoom Frames se destaquen, personalizaremos su apariencia.
### Personalizando el segundo cuadro de zoom
```java
    // Establecer un formato de marco de zoom para el objeto zoomFrame2
    zoomFrame2.getLineFormat().setWidth(5);
    zoomFrame2.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    zoomFrame2.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.MAGENTA);
    zoomFrame2.getLineFormat().setDashStyle(LineDashStyle.DashDot);
```
### Ocultar el fondo para el primer cuadro de zoom
```java
    // No mostrar el fondo del objeto zoomFrame1
    zoomFrame1.setShowBackground(false);
```
## Paso 5: guardar la presentación
Finalmente, guardamos nuestra presentación en la ruta especificada.
```java
    // guardar la presentación
    pres.save(resultPath, SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Conclusión
Crear marcos de zoom en PowerPoint usando Aspose.Slides para Java puede mejorar significativamente la interactividad y la participación de sus presentaciones. Si sigue los pasos descritos en este tutorial, puede agregar fácilmente vistas previas de diapositivas e imágenes personalizadas como marcos de zoom, personalizándolos para que se ajusten al tema de su presentación. ¡Feliz presentación!
## Preguntas frecuentes
### ¿Qué es Aspose.Slides para Java?
Aspose.Slides para Java es una potente API para crear y manipular presentaciones de PowerPoint mediante programación.
### ¿Cómo instalo Aspose.Slides para Java?
 Puede descargar Aspose.Slides para Java desde el[sitio web](https://releases.aspose.com/slides/java/) y agréguelo a las dependencias de su proyecto.
### ¿Puedo personalizar la apariencia de Zoom Frames?
Sí, Aspose.Slides le permite personalizar varias propiedades de Zoom Frames, como el estilo de línea, el color y la visibilidad del fondo.
### ¿Es posible agregar imágenes a Zoom Frames?
¡Absolutamente! Puede agregar imágenes personalizadas a Zoom Frames leyendo archivos de imágenes y agregándolos a la presentación.
### ¿Dónde puedo encontrar más ejemplos y documentación?
 Puede encontrar documentación completa y ejemplos en el[Página de documentación de Aspose.Slides para Java](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
