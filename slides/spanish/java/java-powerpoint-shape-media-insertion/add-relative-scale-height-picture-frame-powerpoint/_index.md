---
title: Agregar marco de imagen de altura de escala relativa en PowerPoint
linktitle: Agregar marco de imagen de altura de escala relativa en PowerPoint
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a agregar marcos de imágenes de altura de escala relativa en presentaciones de PowerPoint usando Aspose.Slides para Java, mejorando su contenido visual.
weight: 15
url: /es/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introducción
En este tutorial, aprenderá cómo agregar un marco de imagen con una altura de escala relativa en presentaciones de PowerPoint usando Aspose.Slides para Java.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
1. Kit de desarrollo de Java (JDK) instalado en su sistema.
2. Biblioteca Aspose.Slides para Java descargada y agregada a su proyecto Java.

## Importar paquetes
Para comenzar, importe los paquetes necesarios en su proyecto Java:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Paso 1: configura tu proyecto
Primero, asegúrese de tener un directorio configurado para su proyecto y de que su entorno Java esté configurado correctamente.
## Paso 2: crear una instancia del objeto de presentación
Cree un nuevo objeto de presentación usando Aspose.Slides:
```java
Presentation presentation = new Presentation();
```
## Paso 3: cargar la imagen que se agregará
Cargue la imagen que desea agregar a la presentación:
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## Paso 4: agregue un marco de imagen a la diapositiva
Agregue un marco de imagen a una diapositiva de la presentación:
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## Paso 5: Establecer el ancho y alto de la escala relativa
Establezca el ancho y alto de la escala relativa para el marco de la imagen:
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## Paso 6: guardar la presentación
Guarde la presentación con el marco de imagen agregado:
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## Conclusión
Siguiendo estos pasos, puede agregar fácilmente un marco de imagen con una altura de escala relativa en presentaciones de PowerPoint usando Aspose.Slides para Java. Experimente con diferentes valores de escala para lograr la apariencia deseada para sus imágenes.

## Preguntas frecuentes
### ¿Puedo agregar varios marcos de fotos a una sola diapositiva usando este método?
Sí, puedes agregar varios marcos de imágenes a una diapositiva repitiendo el proceso para cada imagen.
### ¿Aspose.Slides para Java es compatible con todas las versiones de PowerPoint?
Aspose.Slides para Java es compatible con varias versiones de PowerPoint, lo que garantiza flexibilidad en la creación de presentaciones.
### ¿Puedo personalizar la posición y el tamaño del marco de la imagen?
 Por supuesto, puedes ajustar los parámetros de posición y tamaño en el`addPictureFrame` método que se ajuste a sus necesidades.
### ¿Aspose.Slides para Java admite otros formatos de imagen además de JPEG?
Sí, Aspose.Slides para Java admite varios formatos de imagen, incluidos PNG, GIF, BMP y más.
### ¿Existe un foro comunitario o un canal de soporte disponible para los usuarios de Aspose.Slides?
Sí, puede visitar el foro Aspose.Slides si tiene preguntas, debates o ayuda con respecto a la biblioteca.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
