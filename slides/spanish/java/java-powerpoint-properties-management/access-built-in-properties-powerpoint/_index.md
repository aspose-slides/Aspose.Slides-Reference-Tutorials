---
title: Acceda a las propiedades integradas en PowerPoint
linktitle: Acceda a las propiedades integradas en PowerPoint
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda cómo acceder a las propiedades integradas en PowerPoint usando Aspose.Slides para Java. Este tutorial lo guiará a través de la recuperación del autor, la fecha de creación y más.
weight: 10
url: /es/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introducción
En este tutorial, exploraremos cómo acceder a las propiedades integradas en presentaciones de PowerPoint usando Aspose.Slides para Java. Aspose.Slides es una poderosa biblioteca que permite a los desarrolladores de Java trabajar con presentaciones de PowerPoint mediante programación, permitiendo tareas como leer y modificar propiedades sin problemas.
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1.  Kit de desarrollo de Java (JDK): asegúrese de tener JDK instalado en su sistema. Puedes descargarlo desde[aquí](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides para Java: Descargue e instale Aspose.Slides para Java desde[este enlace](https://releases.aspose.com/slides/java/).

## Importar paquetes
Primero, necesita importar los paquetes necesarios a su proyecto Java. Agregue la siguiente declaración de importación al comienzo de su archivo Java:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## Paso 1: configurar el objeto de presentación
Comience configurando el objeto Presentación para representar la presentación de PowerPoint con la que desea trabajar. Así es como puedes hacerlo:
```java
// La ruta al directorio que contiene el archivo de presentación.
String dataDir = "path_to_your_presentation_directory/";
// Crear una instancia de la clase de presentación
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## Paso 2: acceda a las propiedades del documento
Después de configurar el objeto Presentación, puede acceder a las propiedades integradas de la presentación utilizando la interfaz IDocumentProperties. Así es como puede recuperar varias propiedades:
### Categoría
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### Estado actual
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### Fecha de creación
```java
System.out.println("Creation Date : " + documentProperties.getCreatedTime());
```
### Autor
```java
System.out.println("Author : " + documentProperties.getAuthor());
```
### Descripción
```java
System.out.println("Description : " + documentProperties.getComments());
```
### Palabras clave
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### ultima modificacion por
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### Supervisor
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### Fecha de modificación
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### Formato de presentación
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### Última fecha de impresión
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### Compartido entre productores
```java
System.out.println("Is Shared between producers : " + documentProperties.getSharedDoc());
```
### Sujeto
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### Título
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## Conclusión
En este tutorial, aprendimos cómo acceder a las propiedades integradas en presentaciones de PowerPoint usando Aspose.Slides para Java. Si sigue los pasos descritos anteriormente, puede recuperar fácilmente varias propiedades, como el autor, la fecha de creación y el título, mediante programación.
## Preguntas frecuentes
### ¿Puedo modificar estas propiedades integradas usando Aspose.Slides para Java?
Sí, puede modificar estas propiedades usando Aspose.Slides. Simplemente utilice los métodos de configuración adecuados proporcionados por la interfaz IDocumentProperties.
### ¿Aspose.Slides es compatible con diferentes versiones de PowerPoint?
Aspose.Slides admite una amplia gama de versiones de PowerPoint, lo que garantiza la compatibilidad entre varias plataformas.
### ¿Puedo recuperar propiedades personalizadas también?
Sí, además de las propiedades integradas, también puede recuperar y modificar propiedades personalizadas utilizando Aspose.Slides para Java.
### ¿Aspose.Slides ofrece documentación y soporte?
 Sí, puede encontrar documentación completa y acceder a foros de soporte en el[Aspose sitio web](https://reference.aspose.com/slides/java/).
### ¿Existe una versión de prueba disponible para Aspose.Slides para Java?
 Sí, puedes descargar una versión de prueba gratuita desde[aquí](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
