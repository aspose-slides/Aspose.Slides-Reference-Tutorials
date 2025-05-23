---
"description": "Aprenda a acceder a las propiedades integradas de PowerPoint con Aspose.Slides para Java. Este tutorial le guiará para recuperar el autor, la fecha de creación y más."
"linktitle": "Acceder a las propiedades integradas en PowerPoint"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Acceder a las propiedades integradas en PowerPoint"
"url": "/es/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Acceder a las propiedades integradas en PowerPoint

## Introducción
En este tutorial, exploraremos cómo acceder a las propiedades integradas en presentaciones de PowerPoint usando Aspose.Slides para Java. Aspose.Slides es una potente biblioteca que permite a los desarrolladores de Java trabajar con presentaciones de PowerPoint mediante programación, facilitando tareas como leer y modificar propiedades sin problemas.
## Prerrequisitos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1. Kit de desarrollo de Java (JDK): Asegúrese de tener el JDK instalado en su sistema. Puede descargarlo desde [aquí](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides para Java: Descargue e instale Aspose.Slides para Java desde [este enlace](https://releases.aspose.com/slides/java/).

## Importar paquetes
Primero, debe importar los paquetes necesarios a su proyecto Java. Agregue la siguiente declaración de importación al inicio de su archivo Java:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## Paso 1: Configurar el objeto de presentación
Comience configurando el objeto Presentación para que represente la presentación de PowerPoint con la que desea trabajar. Así es como puede hacerlo:
```java
// La ruta al directorio que contiene el archivo de presentación
String dataDir = "path_to_your_presentation_directory/";
// Instanciar la clase Presentación
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## Paso 2: Acceda a las propiedades del documento
Tras configurar el objeto Presentación, puede acceder a sus propiedades integradas mediante la interfaz IDocumentProperties. A continuación, se explica cómo recuperar diversas propiedades:
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
### Última modificación por
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
### Fecha de última impresión
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
En este tutorial, aprendimos a acceder a las propiedades integradas en presentaciones de PowerPoint con Aspose.Slides para Java. Siguiendo los pasos descritos anteriormente, podrá recuperar fácilmente diversas propiedades, como el autor, la fecha de creación y el título, mediante programación.
## Preguntas frecuentes
### ¿Puedo modificar estas propiedades integradas usando Aspose.Slides para Java?
Sí, puedes modificar estas propiedades con Aspose.Slides. Simplemente usa los métodos de configuración adecuados que proporciona la interfaz IDocumentProperties.
### ¿Aspose.Slides es compatible con diferentes versiones de PowerPoint?
Aspose.Slides admite una amplia gama de versiones de PowerPoint, lo que garantiza la compatibilidad entre diversas plataformas.
### ¿Puedo recuperar también propiedades personalizadas?
Sí, además de las propiedades integradas, también puedes recuperar y modificar propiedades personalizadas usando Aspose.Slides para Java.
### ¿Aspose.Slides ofrece documentación y soporte?
Sí, puede encontrar documentación completa y acceder a foros de soporte en el [Sitio web de Aspose](https://reference.aspose.com/slides/java/).
### ¿Hay una versión de prueba disponible de Aspose.Slides para Java?
Sí, puedes descargar una versión de prueba gratuita desde [aquí](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}