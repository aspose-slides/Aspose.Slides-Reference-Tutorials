---
title: Agregar texto en superíndice y subíndice en Java PowerPoint
linktitle: Agregar texto en superíndice y subíndice en Java PowerPoint
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a agregar texto en superíndice y subíndice en presentaciones de PowerPoint en Java utilizando Aspose.Slides para Java. Perfecto para mejorar tus diapositivas.
weight: 13
url: /es/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introducción
La creación de presentaciones de PowerPoint atractivas e informativas a menudo requiere el uso de funciones de formato como texto en superíndice y subíndice. Este tutorial lo guiará a través del proceso de incorporación de texto en superíndice y subíndice en sus presentaciones de PowerPoint en Java utilizando Aspose.Slides para Java.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
- Kit de desarrollo de Java (JDK) instalado en su sistema.
-  Aspose.Slides para la biblioteca Java. Puedes descargarlo desde[aquí](https://releases.aspose.com/slides/java/).
- Un entorno de desarrollo integrado (IDE) como IntelliJ IDEA o Eclipse configurado para el desarrollo de Java.
- Familiaridad básica con la programación Java y presentaciones de PowerPoint.

## Importar paquetes
Primero, importe los paquetes necesarios desde Aspose.Slides para Java:
```java
import com.aspose.slides.*;
```
## Paso 1: configurar la presentación
```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Paso 2: accede a la diapositiva
```java
// Obtenga la primera diapositiva
ISlide slide = presentation.getSlides().get_Item(0);
```
## Paso 3: crea un cuadro de texto
```java
// Cree una autoforma para que sirva como cuadro de texto
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## Paso 4: agregue texto en superíndice
```java
// Crea un párrafo para el texto principal.
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// Crear una parte para el texto en superíndice
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // Establecer escape para superíndice
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
//Agregue el párrafo principal con superíndice al cuadro de texto
textFrame.getParagraphs().add(mainParagraph);
```
## Paso 5: agregar texto de subíndice
```java
// Crear otro párrafo para texto con subíndice
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// Crear una porción para el texto del subíndice
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // Establecer escape para subíndice
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// Agregue el párrafo del subíndice al cuadro de texto
textFrame.getParagraphs().add(subscriptParagraph);
```
## Paso 6: guarde la presentación
```java
// guardar la presentación
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## Conclusión
En este tutorial, exploramos cómo mejorar sus presentaciones de PowerPoint en Java con texto en superíndice y subíndice usando Aspose.Slides para Java. Si sigue estos pasos, podrá crear diapositivas visualmente más atractivas e informativas que comuniquen su contenido de manera efectiva.

## Preguntas frecuentes
### ¿Qué es Aspose.Slides para Java?
Aspose.Slides para Java es una biblioteca sólida que permite a los desarrolladores crear, manipular y convertir presentaciones de PowerPoint mediante programación.
### ¿Dónde puedo encontrar más documentación sobre Aspose.Slides para Java?
 Se puede encontrar documentación detallada.[aquí](https://reference.aspose.com/slides/java/).
### ¿Cómo puedo obtener una licencia temporal de Aspose.Slides para Java?
 Puedes obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).
### ¿Puedo probar Aspose.Slides para Java gratis?
 Sí, puedes descargar una versión de prueba gratuita desde[aquí](https://releases.aspose.com/).
### ¿Dónde puedo obtener soporte para Aspose.Slides para Java?
 Para soporte y debates, visite el[Foro Aspose.Slides](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
