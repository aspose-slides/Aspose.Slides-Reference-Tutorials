---
title: Crear miniatura de nota secundaria SmartArt
linktitle: Crear miniatura de nota secundaria SmartArt
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a crear miniaturas de notas secundarias SmartArt en Java con Aspose.Slides, mejorando sus presentaciones de PowerPoint sin esfuerzo.
weight: 15
url: /es/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear miniatura de nota secundaria SmartArt

## Introducción
En este tutorial, exploraremos cómo crear miniaturas de notas secundarias SmartArt en Java usando Aspose.Slides. Aspose.Slides es una poderosa API de Java que permite a los desarrolladores trabajar con presentaciones de PowerPoint mediante programación, permitiéndoles crear, modificar y manipular diapositivas con facilidad.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
1. Kit de desarrollo de Java (JDK) instalado en su sistema.
2.  Biblioteca Aspose.Slides para Java descargada y configurada en su proyecto. Puedes descargar la biblioteca desde[aquí](https://releases.aspose.com/slides/java/).

## Importar paquetes
Asegúrese de importar los paquetes necesarios en su clase Java:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.ISmartArtNode;
import com.aspose.slides.Presentation;
import com.aspose.slides.SmartArtLayoutType;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Paso 1: configura tu proyecto
Asegúrese de tener un proyecto Java configurado y configurado con la biblioteca Aspose.Slides.
## Paso 2: crea una presentación
 Instanciar el`Presentation` clase para representar el archivo PPTX:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## Paso 3: agregue SmartArt
Agregue SmartArt a la diapositiva de su presentación:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Paso 4: obtener una referencia de nodo
Obtenga la referencia de un nodo utilizando su índice:
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
## Paso 5: obtener miniatura
Recupere la imagen en miniatura del nodo SmartArt:
```java
BufferedImage bmp = node.getShapes().get_Item(0).getThumbnail();
```
## Paso 6: guardar miniatura
Guarde la imagen en miniatura en un archivo:
```java
ImageIO.write(bmp, "jpeg", new File(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg"));
```
Repita estos pasos para cada nodo SmartArt según sea necesario en su presentación.

## Conclusión
En este tutorial, aprendimos cómo crear miniaturas de notas secundarias SmartArt en Java usando Aspose.Slides. Con este conocimiento, puede mejorar sus presentaciones de PowerPoint mediante programación, agregando elementos visualmente atractivos con facilidad.
## Preguntas frecuentes
### ¿Puedo usar Aspose.Slides para manipular archivos de PowerPoint existentes?
Sí, Aspose.Slides le permite modificar archivos de PowerPoint existentes, incluida la adición, eliminación o edición de diapositivas y su contenido.
### ¿Aspose.Slides admite la exportación de diapositivas a diferentes formatos de archivo?
¡Absolutamente! Aspose.Slides admite la exportación de diapositivas a varios formatos, incluidos PDF, imágenes y HTML, entre otros.
### ¿Aspose.Slides es adecuado para la automatización de PowerPoint a nivel empresarial?
Sí, Aspose.Slides está diseñado para manejar tareas de automatización de PowerPoint a nivel empresarial de manera eficiente y confiable.
### ¿Puedo crear diagramas SmartArt complejos mediante programación con Aspose.Slides?
¡Ciertamente! Aspose.Slides proporciona soporte integral para crear y manipular diagramas SmartArt de diversas complejidades.
### ¿Aspose.Slides ofrece soporte técnico para desarrolladores?
 Sí, Aspose.Slides proporciona soporte técnico dedicado a los desarrolladores a través de su[foro](https://forum.aspose.com/c/slides/11) y otros canales.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
