---
"description": "Aprenda a agregar texto en superíndice y subíndice en presentaciones de PowerPoint en Java con Aspose.Slides para Java. Ideal para mejorar sus diapositivas."
"linktitle": "Agregar texto en superíndice y subíndice en PowerPoint con Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Agregar texto en superíndice y subíndice en PowerPoint con Java"
"url": "/es/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Agregar texto en superíndice y subíndice en PowerPoint con Java

## Introducción
Crear presentaciones de PowerPoint atractivas e informativas suele requerir el uso de funciones de formato como superíndices y subíndices. Este tutorial le guiará en el proceso de incorporar superíndices y subíndices en sus presentaciones de PowerPoint en Java con Aspose.Slides para Java.
## Prerrequisitos
Antes de comenzar, asegúrese de tener lo siguiente:
- Java Development Kit (JDK) instalado en su sistema.
- Biblioteca Aspose.Slides para Java. Puedes descargarla desde [aquí](https://releases.aspose.com/slides/java/).
- Un entorno de desarrollo integrado (IDE) como IntelliJ IDEA o Eclipse configurado para el desarrollo de Java.
- Familiaridad básica con programación Java y presentaciones de PowerPoint.

## Importar paquetes
Primero, importe los paquetes necesarios de Aspose.Slides para Java:
```java
import com.aspose.slides.*;
```
## Paso 1: Configurar la presentación
```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Paso 2: Acceda a la diapositiva
```java
// Obtener la primera diapositiva
ISlide slide = presentation.getSlides().get_Item(0);
```
## Paso 3: Crear un cuadro de texto
```java
// Crea una autoforma que sirva como cuadro de texto
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## Paso 4: Agregar texto en superíndice
```java
// Crea un párrafo para el texto principal.
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// Crear una porción para el texto en superíndice
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // Escape establecido para superíndice
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
// Añade el párrafo principal con superíndice al cuadro de texto
textFrame.getParagraphs().add(mainParagraph);
```
## Paso 5: Agregar texto subíndice
```java
// Crear otro párrafo para el texto subíndice
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// Crear una porción para el texto del subíndice
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // Escape establecido para subíndice
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// Añade el párrafo subíndice al cuadro de texto
textFrame.getParagraphs().add(subscriptParagraph);
```
## Paso 6: Guardar la presentación
```java
// Guardar la presentación
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## Conclusión
En este tutorial, exploramos cómo mejorar sus presentaciones de PowerPoint en Java con superíndices y subíndices usando Aspose.Slides para Java. Siguiendo estos pasos, podrá crear diapositivas visualmente más atractivas e informativas que comuniquen su contenido eficazmente.

## Preguntas frecuentes
### ¿Qué es Aspose.Slides para Java?
Aspose.Slides para Java es una biblioteca sólida que permite a los desarrolladores crear, manipular y convertir presentaciones de PowerPoint mediante programación.
### ¿Dónde puedo encontrar más documentación sobre Aspose.Slides para Java?
La documentación detallada se puede encontrar [aquí](https://reference.aspose.com/slides/java/).
### ¿Cómo puedo obtener una licencia temporal de Aspose.Slides para Java?
Puedes obtener una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).
### ¿Puedo probar Aspose.Slides para Java gratis?
Sí, puedes descargar una versión de prueba gratuita desde [aquí](https://releases.aspose.com/).
### ¿Dónde puedo obtener soporte para Aspose.Slides para Java?
Para obtener ayuda y participar en debates, visite el sitio [Foro de Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}