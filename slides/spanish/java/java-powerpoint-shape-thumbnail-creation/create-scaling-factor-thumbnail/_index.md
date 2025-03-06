---
title: Crear miniatura del factor de escala
linktitle: Crear miniatura del factor de escala
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a crear miniaturas de factores de escala en Java usando Aspose.Slides para Java. Guía fácil de seguir con instrucciones paso a paso.
weight: 12
url: /es/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introducción
En este tutorial, lo guiaremos a través del proceso de creación de una miniatura de factor de escala usando Aspose.Slides para Java. Siga estas instrucciones paso a paso para lograr el resultado deseado.
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Kit de desarrollo de Java (JDK) instalado en su sistema.
- Biblioteca Aspose.Slides para Java descargada y configurada en su proyecto Java.
- Conocimientos básicos del lenguaje de programación Java.

## Importar paquetes
En primer lugar, importe los paquetes necesarios para trabajar con Aspose.Slides en su código Java. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

Ahora, dividamos el ejemplo proporcionado en varios pasos:
## Paso 1: configurar el directorio de documentos
Defina la ruta a su directorio de documentos donde se encuentra el archivo de presentación de PowerPoint.
```java
String dataDir = "Your Document Directory";
```
 Reemplazar`"Your Document Directory"` con la ruta a su directorio de documentos real.
## Paso 2: crear una instancia del objeto de presentación
Cree una instancia de la clase Presentación para representar el archivo de presentación de PowerPoint.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
 Asegúrese de reemplazar`"HelloWorld.pptx"` con el nombre de su archivo de presentación de PowerPoint.
## Paso 3: crear una imagen a escala completa
Genere una imagen a escala completa de la diapositiva deseada de la presentación.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
Este código recupera la miniatura de la primera forma en la primera diapositiva de la presentación.
## Paso 4: guarde la imagen
Guarde la imagen generada en el disco en formato PNG.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
 Asegúrese de reemplazar`"Scaling Factor Thumbnail_out.png"` con el nombre del archivo de salida deseado.

## Conclusión
En conclusión, ha creado con éxito una miniatura de factor de escala utilizando Aspose.Slides para Java. Si sigue los pasos proporcionados, podrá integrar fácilmente esta funcionalidad en sus aplicaciones Java.
## Preguntas frecuentes
### ¿Puedo usar Aspose.Slides para Java con cualquier IDE de Java?
Sí, Aspose.Slides para Java se puede utilizar con cualquier entorno de desarrollo integrado (IDE) de Java, como Eclipse, IntelliJ IDEA o NetBeans.
### ¿Hay una prueba gratuita disponible para Aspose.Slides para Java?
 Sí, puede aprovechar una prueba gratuita de Aspose.Slides para Java visitando el[sitio web](https://releases.aspose.com/).
### ¿Dónde puedo encontrar soporte para Aspose.Slides para Java?
 Puede encontrar soporte para Aspose.Slides para Java en el[Foro Aspose.Slides](https://forum.aspose.com/c/slides/11).
### ¿Cómo puedo comprar Aspose.Slides para Java?
 Puede comprar Aspose.Slides para Java desde el[pagina de compra](https://purchase.aspose.com/buy).
### ¿Necesito una licencia temporal para usar Aspose.Slides para Java?
 Sí, puede obtener una licencia temporal de la[página de licencia temporal](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
