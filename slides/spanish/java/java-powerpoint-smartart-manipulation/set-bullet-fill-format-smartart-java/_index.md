---
title: Establecer formato de relleno de viñetas en SmartArt usando Java
linktitle: Establecer formato de relleno de viñetas en SmartArt usando Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a configurar el formato de relleno de viñetas en SmartArt usando Java con Aspose.Slides. Guía paso a paso para una manipulación eficaz de la presentación.
weight: 18
url: /es/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Establecer formato de relleno de viñetas en SmartArt usando Java

## Introducción
En el ámbito de la programación Java, la manipulación eficiente de presentaciones es un requisito común, especialmente cuando se trata de elementos SmartArt. Aspose.Slides para Java surge como una poderosa herramienta para este tipo de tareas, ofreciendo una variedad de funcionalidades para manejar presentaciones programáticamente. En este tutorial, profundizaremos en el proceso de configuración del formato de relleno de viñetas en SmartArt usando Java con Aspose.Slides, paso a paso.
## Requisitos previos
Antes de embarcarnos en este tutorial, asegúrese de tener implementados los siguientes requisitos previos:
### Kit de desarrollo de Java (JDK)
 Necesita tener JDK instalado en su sistema. Puedes descargarlo desde el[sitio web](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) y siga las instrucciones de instalación.
### Aspose.Slides para Java
 Descargue e instale Aspose.Slides para Java desde[enlace de descarga](https://releases.aspose.com/slides/java/). Siga las instrucciones de instalación proporcionadas en la documentación de su sistema operativo específico.

## Importar paquetes
Para comenzar, importe los paquetes necesarios a su proyecto Java:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#Dividamos el ejemplo proporcionado en varios pasos para comprender claramente cómo configurar el formato de relleno de viñetas en SmartArt usando Java con Aspose.Slides.
## Paso 1: crear un objeto de presentación
```java
Presentation presentation = new Presentation();
```
En primer lugar, cree una nueva instancia de la clase Presentación, que representa una presentación de PowerPoint.
## Paso 2: agregue SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
A continuación, agregue una forma SmartArt a la diapositiva. Esta línea de código inicializa una nueva forma SmartArt con dimensiones y diseño especificados.
## Paso 3: acceda al nodo SmartArt
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Ahora, acceda al primer nodo (o cualquier nodo deseado) dentro de la forma SmartArt para modificar sus propiedades.
## Paso 4: establecer el formato de relleno con viñetas
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
Aquí comprobamos si se admite el formato de relleno con viñetas. Si es así, cargamos un archivo de imagen y lo configuramos como relleno de viñetas para el nodo SmartArt.
## Paso 5: guardar la presentación
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
Finalmente, guarde la presentación modificada en una ubicación específica.

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo configurar el formato de relleno de viñetas en SmartArt usando Java con Aspose.Slides. Esta capacidad abre un mundo de posibilidades para presentaciones dinámicas y visualmente atractivas en aplicaciones Java.
## Preguntas frecuentes
### ¿Puedo usar Aspose.Slides para Java para crear presentaciones desde cero?
¡Absolutamente! Aspose.Slides proporciona API integrales para crear, modificar y manipular presentaciones completamente a través de código.
### ¿Aspose.Slides es compatible con diferentes versiones de PowerPoint?
Sí, Aspose.Slides garantiza la compatibilidad con varias versiones de Microsoft PowerPoint, lo que permite una integración perfecta en su flujo de trabajo.
### ¿Puedo personalizar elementos SmartArt más allá del formato de relleno con viñetas?
De hecho, Aspose.Slides le permite personalizar todos los aspectos de las formas SmartArt, incluido el diseño, el estilo, el contenido y más.
### ¿Existe una versión de prueba disponible para Aspose.Slides para Java?
 Sí, puedes explorar las funciones de Aspose.Slides con una prueba gratuita. Simplemente descárgalo desde[sitio web](https://releases.aspose.com/slides/java/) y empezar a explorar.
### ¿Dónde puedo encontrar soporte para Aspose.Slides para Java?
 Para cualquier consulta o ayuda, puede visitar el foro Aspose.Slides en[este enlace](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
