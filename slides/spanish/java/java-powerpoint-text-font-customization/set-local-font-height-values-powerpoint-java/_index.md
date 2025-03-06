---
title: Establecer valores de altura de fuente local en PowerPoint usando Java
linktitle: Establecer valores de altura de fuente local en PowerPoint usando Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a ajustar la altura de las fuentes en presentaciones de PowerPoint usando Java con Aspose.Slides. Mejore el formato del texto en sus diapositivas sin esfuerzo.
weight: 17
url: /es/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introducción
En este tutorial, aprenderá cómo manipular las alturas de las fuentes en varios niveles dentro de presentaciones de PowerPoint usando Aspose.Slides para Java. Controlar el tamaño de fuente es crucial para crear presentaciones estructuradas y visualmente atractivas. Revisaremos ejemplos paso a paso para ilustrar cómo establecer alturas de fuente para diferentes elementos de texto.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
- Kit de desarrollo de Java (JDK) instalado en su sistema
-  Aspose.Slides para la biblioteca Java. Puedes descargarlo[aquí](https://releases.aspose.com/slides/java/).
- Una comprensión básica de la programación Java y presentaciones de PowerPoint.
## Importar paquetes
Asegúrese de incluir los paquetes Aspose.Slides necesarios en su archivo Java:
```java
import com.aspose.slides.*;
```
## Paso 1: Inicializar un objeto de presentación
Primero, cree un nuevo objeto de presentación de PowerPoint:
```java
Presentation pres = new Presentation();
```
## Paso 2: agregue una forma y un marco de texto
Agregue una forma automática con un marco de texto a la primera diapositiva:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## Paso 3: crear porciones de texto
Defina porciones de texto con diferentes alturas de fuente:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## Paso 4: Establecer alturas de fuente
Establezca alturas de fuente en diferentes niveles:
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## Paso 5: guarde la presentación
Guarde la presentación modificada en un archivo:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## Conclusión
Este tutorial demostró cómo ajustar la altura de las fuentes dentro de las diapositivas de PowerPoint mediante programación usando Aspose.Slides para Java. Al manipular los tamaños de fuente en diferentes niveles (en toda la presentación, párrafo y parte), puede lograr un control preciso sobre el formato del texto en sus presentaciones.
## Preguntas frecuentes
### ¿Qué es Aspose.Slides para Java?
Aspose.Slides para Java es una potente API para manipular presentaciones de PowerPoint mediante programación.
### ¿Dónde puedo encontrar documentación para Aspose.Slides para Java?
 Puedes encontrar la documentación.[aquí](https://reference.aspose.com/slides/java/).
### ¿Puedo probar Aspose.Slides para Java antes de comprarlo?
 Sí, puedes obtener una prueba gratuita.[aquí](https://releases.aspose.com/).
### ¿Cómo puedo obtener soporte para Aspose.Slides para Java?
 Para obtener ayuda, visite el[Foro Aspose.Slides](https://forum.aspose.com/c/slides/11).
### ¿Dónde puedo comprar una licencia de Aspose.Slides para Java?
 Puedes comprar una licencia[aquí](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
