---
"description": "Aprende a ajustar la altura de fuente en presentaciones de PowerPoint usando Java con Aspose.Slides. Mejora el formato del texto en tus diapositivas fácilmente."
"linktitle": "Establecer valores de altura de fuente local en PowerPoint usando Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Establecer valores de altura de fuente local en PowerPoint usando Java"
"url": "/es/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Establecer valores de altura de fuente local en PowerPoint usando Java

## Introducción
En este tutorial, aprenderá a manipular la altura de fuente en diferentes niveles de presentaciones de PowerPoint con Aspose.Slides para Java. Controlar el tamaño de fuente es crucial para crear presentaciones visualmente atractivas y estructuradas. Analizaremos ejemplos paso a paso para ilustrar cómo configurar la altura de fuente para diferentes elementos de texto.
## Prerrequisitos
Antes de comenzar, asegúrese de tener lo siguiente:
- Kit de desarrollo de Java (JDK) instalado en su sistema
- Biblioteca Aspose.Slides para Java. Puedes descargarla. [aquí](https://releases.aspose.com/slides/java/).
- Una comprensión básica de programación Java y presentaciones de PowerPoint.
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
## Paso 2: Agregar una forma y un marco de texto
Agregue una forma automática con un marco de texto a la primera diapositiva:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## Paso 3: Crear porciones de texto
Definir porciones de texto con diferentes alturas de fuente:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## Paso 4: Establecer la altura de las fuentes
Establecer alturas de fuente en diferentes niveles:
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## Paso 5: Guardar la presentación
Guarde la presentación modificada en un archivo:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## Conclusión
Este tutorial muestra cómo ajustar la altura de fuente en diapositivas de PowerPoint mediante programación con Aspose.Slides para Java. Al manipular el tamaño de fuente en diferentes niveles (toda la presentación, párrafo y parte), puede lograr un control preciso del formato del texto en sus presentaciones.
## Preguntas frecuentes
### ¿Qué es Aspose.Slides para Java?
Aspose.Slides para Java es una potente API para manipular presentaciones de PowerPoint mediante programación.
### ¿Dónde puedo encontrar documentación de Aspose.Slides para Java?
Puede encontrar la documentación [aquí](https://reference.aspose.com/slides/java/).
### ¿Puedo probar Aspose.Slides para Java antes de comprarlo?
Sí, puedes obtener una prueba gratuita [aquí](https://releases.aspose.com/).
### ¿Cómo puedo obtener soporte para Aspose.Slides para Java?
Para obtener ayuda, visite el sitio [Foro de Aspose.Slides](https://forum.aspose.com/c/slides/11).
### ¿Dónde puedo comprar una licencia de Aspose.Slides para Java?
Puedes comprar una licencia [aquí](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}