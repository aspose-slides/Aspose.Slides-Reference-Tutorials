---
title: Cambiar el estilo de forma SmartArt en PowerPoint con Java
linktitle: Cambiar el estilo de forma SmartArt en PowerPoint con Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a cambiar los estilos SmartArt en presentaciones de PowerPoint usando Java con Aspose.Slides para Java. Impulsa tus presentaciones.
weight: 23
url: /es/java/java-powerpoint-smartart-manipulation/change-smartart-shape-style-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introducción
En el mundo del desarrollo de Java, la creación de presentaciones potentes suele ser un requisito. Ya sea para presentaciones comerciales, fines educativos o simplemente para compartir información, las presentaciones de PowerPoint son un medio común. Sin embargo, en ocasiones los estilos y formatos predeterminados proporcionados por PowerPoint pueden no satisfacer completamente nuestras necesidades. Aquí es donde entra en juego Aspose.Slides para Java.
Aspose.Slides para Java es una biblioteca sólida que permite a los desarrolladores de Java trabajar con presentaciones de PowerPoint mediante programación. Proporciona una amplia gama de funciones, incluida la capacidad de manipular formas, estilos, animaciones y mucho más. En este tutorial, nos centraremos en una tarea específica: cambiar el estilo de forma SmartArt en presentaciones de PowerPoint usando Java.
## Requisitos previos
Antes de sumergirse en el tutorial, hay algunos requisitos previos que debe cumplir:
1. Kit de desarrollo de Java (JDK): asegúrese de tener JDK instalado en su sistema. Puede descargar e instalar la última versión desde el sitio web de Oracle.
2. Biblioteca Aspose.Slides para Java: deberá descargar e incluir la biblioteca Aspose.Slides para Java en su proyecto. Puedes encontrar el enlace de descarga.[aquí](https://releases.aspose.com/slides/java/).
3. Entorno de desarrollo integrado (IDE): elija su IDE preferido para el desarrollo de Java. IntelliJ IDEA, Eclipse o NetBeans son opciones populares.

## Importar paquetes
Antes de comenzar a codificar, importemos los paquetes necesarios a nuestro proyecto Java. Estos paquetes nos permitirán trabajar con las funcionalidades de Aspose.Slides sin problemas.
```java
import com.aspose.slides.*;
```
## Paso 1: Cargue la presentación
Primero, necesitamos cargar la presentación de PowerPoint que queremos modificar.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "AccessSmartArtShape.pptx");
```
## Paso 2: atravesar formas
A continuación, recorreremos cada forma dentro de la primera diapositiva de la presentación.
```java
for (IShape shape : presentation.getSlides().get_Item(0).getShapes())
```
## Paso 3: Verifique el tipo de SmartArt
Para cada forma, comprobaremos si es una forma SmartArt.
```java
if (shape instanceof ISmartArt)
```
## Paso 4: Transmitir a SmartArt
 Si la forma es un SmartArt, la enviaremos al`ISmartArt` interfaz.
```java
ISmartArt smart = (ISmartArt) shape;
```
## Paso 5: Verifique y cambie el estilo
Luego verificaremos el estilo actual del SmartArt y lo cambiaremos si es necesario.
```java
if (smart.getQuickStyle() == SmartArtQuickStyleType.SimpleFill)
{
    smart.setQuickStyle(SmartArtQuickStyleType.Cartoon);
}
```
## Paso 6: guardar la presentación
Finalmente, guardaremos la presentación modificada en un archivo nuevo.
```java
presentation.save(dataDir + "ChangeSmartArtStyle_out.pptx", SaveFormat.Pptx);
```

## Conclusión
En este tutorial, aprendimos cómo cambiar el estilo de forma SmartArt en presentaciones de PowerPoint usando Java y la biblioteca Aspose.Slides para Java. Siguiendo la guía paso a paso, podrá personalizar fácilmente la apariencia de las formas SmartArt para que se adapten mejor a sus necesidades de presentación.
## Preguntas frecuentes
### ¿Puedo usar Aspose.Slides para Java con otras bibliotecas de Java?
Sí, Aspose.Slides para Java se puede integrar perfectamente con otras bibliotecas de Java para mejorar la funcionalidad de sus aplicaciones.
### ¿Hay una prueba gratuita disponible para Aspose.Slides para Java?
 Sí, puede aprovechar una prueba gratuita de Aspose.Slides para Java desde[aquí](https://releases.aspose.com/).
### ¿Cómo puedo obtener soporte para Aspose.Slides para Java?
 Puede obtener soporte para Aspose.Slides para Java visitando el[foro](https://forum.aspose.com/c/slides/11).
### ¿Puedo comprar una licencia temporal de Aspose.Slides para Java?
 Sí, puede adquirir una licencia temporal de Aspose.Slides para Java en[aquí](https://purchase.aspose.com/temporary-license/).
### ¿Dónde puedo encontrar documentación detallada para Aspose.Slides para Java?
 Puede encontrar documentación detallada para Aspose.Slides para Java[aquí](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
