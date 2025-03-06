---
title: Cambiar texto en el nodo SmartArt usando Java
linktitle: Cambiar texto en el nodo SmartArt usando Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Descubra cómo actualizar el texto del nodo SmartArt en PowerPoint usando Java con Aspose.Slides, mejorando la personalización de la presentación.
weight: 22
url: /es/java/java-powerpoint-smartart-manipulation/change-text-smartart-node-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introducción
SmartArt en PowerPoint es una característica poderosa para crear diagramas visualmente atractivos. Aspose.Slides para Java proporciona soporte integral para manipular elementos SmartArt mediante programación. En este tutorial, lo guiaremos a través del proceso de cambiar texto en un nodo SmartArt usando Java.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
- Kit de desarrollo de Java (JDK) instalado en su sistema.
- Biblioteca Aspose.Slides para Java descargada y referenciada en su proyecto Java.
- Conocimientos básicos de programación Java.

## Importar paquetes
Primero, importe los paquetes necesarios para acceder a la funcionalidad Aspose.Slides dentro de su código Java.
```java
import com.aspose.slides.*;
```
Dividamos el ejemplo en varios pasos:
## Paso 1: inicializar el objeto de presentación
```java
Presentation presentation = new Presentation();
```
 Crear una nueva instancia del`Presentation` clase para trabajar con una presentación de PowerPoint.
## Paso 2: agregue SmartArt a la diapositiva
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
 Agrega SmartArt a la primera diapositiva. En este ejemplo, estamos usando el`BasicCycle` disposición.
## Paso 3: acceda al nodo SmartArt
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
Obtenga una referencia al segundo nodo raíz del SmartArt.
## Paso 4: establecer texto en el nodo
```java
node.getTextFrame().setText("Second root node");
```
Establezca el texto para el nodo SmartArt seleccionado.
## Paso 5: guardar la presentación
```java
presentation.save(dataDir + "ChangeText_On_SmartArt_Node_out.pptx", SaveFormat.Pptx);
```
Guarde la presentación modificada en una ubicación especificada.

## Conclusión
En este tutorial, hemos demostrado cómo cambiar texto en un nodo SmartArt usando Java y Aspose.Slides. Con este conocimiento, puede manipular dinámicamente elementos SmartArt en sus presentaciones de PowerPoint, mejorando su atractivo visual y claridad.
## Preguntas frecuentes
### ¿Puedo cambiar el diseño del SmartArt después de agregarlo a la diapositiva?
 Sí, puedes cambiar el diseño accediendo al`SmartArt.setAllNodes(LayoutType)` método.
### ¿Aspose.Slides es compatible con Java 11?
Sí, Aspose.Slides para Java es compatible con Java 11 y versiones más recientes.
### ¿Puedo personalizar la apariencia de los nodos SmartArt mediante programación?
Ciertamente, puede modificar varias propiedades como el color, el tamaño y la forma utilizando la API Aspose.Slides.
### ¿Aspose.Slides admite otros tipos de diseños SmartArt?
Sí, Aspose.Slides admite una amplia gama de diseños SmartArt, lo que le permite elegir el que mejor se adapte a sus necesidades de presentación.
### ¿Dónde puedo encontrar más recursos y soporte para Aspose.Slides?
 Puedes visitar el[Documentación de Aspose.Slides](https://reference.aspose.com/slides/java/) para obtener referencias detalladas de API y tutoriales. Además, puede buscar ayuda del[Foro Aspose.Slides](https://forum.aspose.com/c/slides/11) o considere comprar un[licencia temporal](https://purchase.aspose.com/temporary-license/) para apoyo profesional.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
