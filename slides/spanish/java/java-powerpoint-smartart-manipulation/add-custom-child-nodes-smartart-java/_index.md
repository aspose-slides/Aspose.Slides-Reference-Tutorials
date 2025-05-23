---
"description": "Aprenda a agregar nodos secundarios personalizados a SmartArt en presentaciones de PowerPoint usando Java con Aspose.Slides. Mejore sus diapositivas con gráficos profesionales sin esfuerzo."
"linktitle": "Agregar nodos secundarios personalizados en SmartArt mediante Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Agregar nodos secundarios personalizados en SmartArt mediante Java"
"url": "/es/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Agregar nodos secundarios personalizados en SmartArt mediante Java

## Introducción
SmartArt es una potente función de PowerPoint que permite crear gráficos profesionales de forma rápida y sencilla. En este tutorial, aprenderemos a añadir nodos secundarios personalizados a SmartArt usando Java con Aspose.Slides.
## Prerrequisitos
Antes de comenzar, asegúrese de tener lo siguiente:
1. Kit de desarrollo de Java (JDK): asegúrese de tener Java instalado en su sistema.
2. Aspose.Slides para Java: Descargue e instale Aspose.Slides para Java desde [aquí](https://releases.aspose.com/slides/java/).

## Importar paquetes
Para comenzar, importe los paquetes necesarios en su proyecto Java:
```java
import com.aspose.slides.*;
```
## Paso 1: Cargar la presentación
Cargue la presentación de PowerPoint en la que desea agregar nodos secundarios personalizados al SmartArt:
```java
String dataDir = "Your Document Directory";
// Cargar la presentación deseada
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## Paso 2: Agregar SmartArt a la diapositiva
Ahora, agreguemos SmartArt a la diapositiva:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## Paso 3: Mover la forma SmartArt
Mueva la forma SmartArt a una nueva posición:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## Paso 4: Cambiar el ancho de la forma
Cambiar el ancho de la forma SmartArt:
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## Paso 5: Cambiar la altura de la forma
Cambiar la altura de la forma SmartArt:
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## Paso 6: Girar la forma
Girar la forma SmartArt:
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## Paso 7: Guardar la presentación
Por último, guarde la presentación modificada:
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## Conclusión
En este tutorial, aprendimos a agregar nodos secundarios personalizados a SmartArt usando Java con Aspose.Slides. Siguiendo estos pasos, podrá mejorar sus presentaciones con gráficos personalizados, haciéndolas más atractivas y profesionales.
## Preguntas frecuentes
### ¿Puedo agregar diferentes tipos de diseños SmartArt usando Aspose.Slides para Java?
Sí, Aspose.Slides para Java admite varios diseños SmartArt, lo que le permite elegir el que mejor se adapte a sus necesidades de presentación.
### ¿Aspose.Slides para Java es compatible con diferentes versiones de PowerPoint?
Aspose.Slides para Java está diseñado para funcionar sin problemas con diferentes versiones de PowerPoint, lo que garantiza la compatibilidad y la coherencia entre plataformas.
### ¿Puedo personalizar la apariencia de las formas SmartArt mediante programación?
¡Por supuesto! Con Aspose.Slides para Java, puedes personalizar programáticamente la apariencia, el tamaño, el color y el diseño de las formas SmartArt para adaptarlas a tus preferencias de diseño.
### ¿Aspose.Slides para Java proporciona documentación y soporte?
Sí, puede encontrar documentación completa y acceso a foros de soporte de la comunidad en el sitio web de Aspose.
### ¿Hay una versión de prueba disponible de Aspose.Slides para Java?
Sí, puede descargar una versión de prueba gratuita de Aspose.Slides para Java desde el sitio web para explorar sus características y capacidades antes de realizar una compra. [aquí](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}