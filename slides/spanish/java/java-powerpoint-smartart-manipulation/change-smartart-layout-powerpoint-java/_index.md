---
title: Cambiar el diseño de SmartArt en PowerPoint con Java
linktitle: Cambiar el diseño de SmartArt en PowerPoint con Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a manipular diseños SmartArt en presentaciones de PowerPoint usando Java con Aspose.Slides para Java.
type: docs
weight: 19
url: /es/java/java-powerpoint-smartart-manipulation/change-smartart-layout-powerpoint-java/
---
## Introducción
En este tutorial, exploraremos cómo manipular diseños SmartArt en presentaciones de PowerPoint usando Java. SmartArt es una característica poderosa de PowerPoint que permite a los usuarios crear gráficos visualmente atractivos para diversos fines, como ilustrar procesos, jerarquías, relaciones y más.
## Requisitos previos
Antes de sumergirnos en el tutorial, asegúrese de tener lo siguiente:
1. Entorno de desarrollo de Java: asegúrese de tener instalado el kit de desarrollo de Java (JDK) en su sistema.
2.  Biblioteca Aspose.Slides: descargue e instale la biblioteca Aspose.Slides para Java desde[aquí](https://releases.aspose.com/slides/java/).
3. Comprensión básica de Java: será útil estar familiarizado con los fundamentos del lenguaje de programación Java.
4. Entorno de desarrollo integrado (IDE): elija un IDE de su preferencia, como Eclipse o IntelliJ IDEA.

## Importar paquetes
Para comenzar, importe los paquetes necesarios a su proyecto Java:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
## Paso 1: configure el entorno de su proyecto Java
Asegúrese de que su proyecto Java esté configurado correctamente en el IDE elegido. Cree un nuevo proyecto Java e incluya la biblioteca Aspose.Slides en las dependencias de su proyecto.
## Paso 2: crea una nueva presentación
Cree una instancia de un nuevo objeto de presentación para crear una nueva presentación de PowerPoint.
```java
Presentation presentation = new Presentation();
```
## Paso 3: agregue un gráfico SmartArt
Agregue un gráfico SmartArt a su presentación. Especifique la posición y las dimensiones del gráfico SmartArt en la diapositiva.
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicBlockList);
```
## Paso 4: cambiar el diseño de SmartArt
Cambie el diseño del gráfico SmartArt al tipo de diseño que desee.
```java
smart.setLayout(SmartArtLayoutType.BasicProcess);
```
## Paso 5: guardar la presentación
Guarde la presentación modificada en un directorio específico de su sistema.
```java
presentation.save(dataDir + "ChangeSmartArtLayout_out.pptx", SaveFormat.Pptx);
```

## Conclusión
Manipular diseños SmartArt en presentaciones de PowerPoint usando Java es un proceso sencillo con Aspose.Slides para Java. Siguiendo este tutorial, podrá modificar fácilmente los gráficos SmartArt para adaptarlos a sus necesidades de presentación.
## Preguntas frecuentes
### ¿Puedo personalizar la apariencia de los gráficos SmartArt usando Aspose.Slides para Java?
Sí, puedes personalizar varios aspectos de los gráficos SmartArt, como colores, estilos y efectos.
### ¿Aspose.Slides es compatible con diferentes versiones de PowerPoint?
Aspose.Slides admite presentaciones de PowerPoint creadas en varias versiones de PowerPoint, lo que garantiza la compatibilidad entre diferentes plataformas.
### ¿Aspose.Slides ofrece soporte para otros lenguajes de programación?
Sí, Aspose.Slides está disponible para múltiples lenguajes de programación, incluidos .NET, Python y JavaScript.
### ¿Puedo crear gráficos SmartArt desde cero usando Aspose.Slides?
Por supuesto, puede crear gráficos SmartArt mediante programación o modificar los existentes para satisfacer sus necesidades.
### ¿Existe un foro comunitario donde pueda buscar ayuda con respecto a Aspose.Slides?
 Sí, puedes visitar el foro de Aspose.Slides.[aquí](https://forum.aspose.com/c/slides/11) para hacer preguntas e interactuar con la comunidad.