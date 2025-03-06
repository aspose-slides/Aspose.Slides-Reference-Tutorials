---
title: Agregar nodo asistente a SmartArt en Java PowerPoint
linktitle: Agregar nodo asistente a SmartArt en Java PowerPoint
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda cómo agregar un nodo asistente a SmartArt en presentaciones de PowerPoint Java usando Aspose.Slides. Mejore sus habilidades de edición de PowerPoint.
weight: 17
url: /es/java/java-powerpoint-smartart-manipulation/add-assistant-node-smartart-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introducción
En este tutorial, lo guiaremos a través del proceso de agregar un nodo asistente a SmartArt en presentaciones de PowerPoint Java usando Aspose.Slides.
## Requisitos previos
Antes de comenzar, asegúrese de tener implementados los siguientes requisitos previos:
1.  Kit de desarrollo de Java (JDK): asegúrese de tener Java instalado en su sistema. Puede descargar e instalar el último JDK desde[aquí](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides para Java: descargue e instale la biblioteca Aspose.Slides para Java desde[este enlace](https://releases.aspose.com/slides/java/).

## Importar paquetes
Para empezar, importe los paquetes necesarios en su código Java:
```java
import com.aspose.slides.*;
```
## Paso 1: configurar la presentación
Comience creando una instancia de presentación usando la ruta a su archivo de PowerPoint:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "AssistantNode.pptx");
```
## Paso 2: atravesar formas
Recorre todas las formas dentro de la primera diapositiva de la presentación:
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes())
```
## Paso 3: busque formas SmartArt
Comprueba si la forma es de tipo SmartArt:
```java
if (shape instanceof ISmartArt)
```
## Paso 4: atravesar los nodos SmartArt
Recorra todos los nodos de la forma SmartArt:
```java
for (ISmartArtNode node : smart.getAllNodes())
```
## Paso 5: busque el nodo asistente
Compruebe si el nodo es un nodo asistente:
```java
if (node.isAssistant())
```
## Paso 6: configure el nodo asistente en Normal
Si el nodo es un nodo asistente, configúrelo como un nodo normal:
```java
node.setAssistant(false);
```
## Paso 7: guardar la presentación
Guarde la presentación modificada:
```java
pres.save(dataDir + "ChangeAssistantNode_out.pptx", SaveFormat.Pptx);
```

## Conclusión
¡Felicidades! Ha agregado con éxito un nodo asistente a SmartArt en su presentación de PowerPoint Java usando Aspose.Slides.

## Preguntas frecuentes
### ¿Puedo agregar varios nodos asistentes a un SmartArt en la presentación?
Sí, puedes agregar varios nodos asistentes repitiendo el proceso para cada nodo.
### ¿Este tutorial funciona tanto para PowerPoint como para plantillas de PowerPoint?
Sí, puedes aplicar este tutorial tanto a presentaciones como a plantillas de PowerPoint.
### ¿Aspose.Slides es compatible con todas las versiones de PowerPoint?
Aspose.Slides admite versiones de PowerPoint desde 97-2003 hasta la última versión.
### ¿Puedo personalizar la apariencia del nodo asistente?
Sí, puede personalizar la apariencia utilizando varias propiedades y métodos proporcionados por Aspose.Slides.
### ¿Existe algún límite para la cantidad de nodos en un SmartArt?
SmartArt en PowerPoint admite una gran cantidad de nodos, pero se recomienda mantenerlo razonable para una mejor legibilidad.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
