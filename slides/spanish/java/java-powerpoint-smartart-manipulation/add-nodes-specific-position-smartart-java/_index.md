---
title: Agregar nodos en una posición específica en SmartArt usando Java
linktitle: Agregar nodos en una posición específica en SmartArt usando Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Descubra cómo agregar nodos en posiciones específicas en SmartArt usando Java con Aspose.Slides. Cree presentaciones dinámicas sin esfuerzo.
weight: 16
url: /es/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar nodos en una posición específica en SmartArt usando Java

## Introducción
En este tutorial, lo guiaremos a través del proceso de agregar nodos en posiciones específicas en SmartArt usando Java con Aspose.Slides. SmartArt es una característica de PowerPoint que le permite crear diagramas y cuadros visualmente atractivos.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
1. Kit de desarrollo de Java (JDK) instalado en su sistema.
2.  Descarga la biblioteca Aspose.Slides para Java. Puedes descargarlo desde[aquí](https://releases.aspose.com/slides/java/).
3. Conocimientos básicos del lenguaje de programación Java.

## Importar paquetes
Primero, importemos los paquetes necesarios en nuestro código Java:
```java
import com.aspose.slides.*;
import java.io.File;
```
## Paso 1: crear una instancia de presentación
Comience creando una instancia de la clase Presentación:
```java
Presentation pres = new Presentation();
```
## Paso 2: acceda a la diapositiva de presentación
Accede a la diapositiva donde deseas agregar el SmartArt:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Paso 3: agregar forma SmartArt
Agregue una forma SmartArt a la diapositiva:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## Paso 4: acceda al nodo SmartArt
Acceda al nodo SmartArt en el índice deseado:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Paso 5: agregar un nodo secundario en una posición específica
Agregue un nuevo nodo secundario en una posición específica en el nodo principal:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## Paso 6: agregue texto al nodo
Establezca el texto para el nodo recién agregado:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## Paso 7: guarde la presentación
Guarde la presentación modificada:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Conclusión
En este tutorial, aprendió cómo agregar nodos en posiciones específicas en SmartArt usando Java con Aspose.Slides. Si sigue estos pasos, puede manipular formas SmartArt mediante programación para crear presentaciones dinámicas.
## Preguntas frecuentes
### ¿Puedo agregar varios nodos a la vez?
Sí, puede agregar varios nodos mediante programación iterando sobre las posiciones deseadas.
### ¿Aspose.Slides es compatible con todas las versiones de PowerPoint?
Aspose.Slides admite varios formatos de PowerPoint, lo que garantiza la compatibilidad con la mayoría de las versiones.
### ¿Puedo personalizar la apariencia de los nodos SmartArt?
Sí, puedes personalizar la apariencia de los nodos, incluido su tamaño, color y estilo.
### ¿Aspose.Slides ofrece soporte para otros lenguajes de programación?
Sí, Aspose.Slides proporciona bibliotecas para múltiples lenguajes de programación, incluidos .NET y Python.
### ¿Existe una versión de prueba disponible para Aspose.Slides?
 Sí, puedes descargar una versión de prueba gratuita desde[aquí](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
