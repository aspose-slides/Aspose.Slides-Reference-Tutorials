---
title: Guarde PowerPoint con fuente normal predeterminada usando Java
linktitle: Guarde PowerPoint con fuente normal predeterminada usando Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a manipular presentaciones de PowerPoint mediante programación utilizando Aspose.Slides para Java. Domine el manejo de Java PowerPoint con tutoriales paso a paso.
weight: 12
url: /es/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introducción
En el ámbito del desarrollo de Java, la creación y manipulación de presentaciones de PowerPoint mediante programación puede mejorar enormemente la productividad y las opciones de personalización. Aspose.Slides para Java es una biblioteca sólida que permite a los desarrolladores manejar archivos de PowerPoint de manera eficiente, ofreciendo un conjunto completo de funciones, desde modificaciones simples hasta presentaciones complejas.
## Requisitos previos
Antes de sumergirse en el uso de Aspose.Slides para Java, asegúrese de tener configurados los siguientes requisitos previos:
1. Kit de desarrollo de Java (JDK): Aspose.Slides para Java requiere JDK 1.8 o superior para funcionar correctamente.
2. Aspose.Slides para Java JAR: Descargue la última versión de Aspose.Slides para Java desde[aquí](https://releases.aspose.com/slides/java/).
3. Entorno de desarrollo integrado (IDE): utilice IntelliJ IDEA, Eclipse u otro IDE de Java de su elección.
4. Comprensión básica de Java: es necesaria estar familiarizado con los fundamentos del lenguaje de programación Java.

## Importar paquetes
Para comenzar a usar Aspose.Slides para Java, importe los paquetes necesarios:
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
Esto garantiza que tenga acceso a todas las clases y métodos proporcionados por Aspose.Slides para Java.
## Paso 1: configura tu proyecto
Primero, cree un nuevo proyecto Java en su IDE e incluya el archivo JAR Aspose.Slides para Java en la ruta de compilación de su proyecto.
## Paso 2: inicializar el objeto de presentación
 Crear una instancia de`Presentation` objeto cargando un archivo de PowerPoint existente (.pptx) desde su directorio local.
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// Cargar presentación
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
 Reemplazar`"Your Document Directory"` y`"Your Output Directory"` con las rutas de archivos reales.
## Paso 3: guarde la presentación con fuentes regulares predeterminadas
 Especifique la fuente normal predeterminada para los formatos de salida (HTML y PDF) usando`HtmlOptions` y`PdfOptions` respectivamente.
```java
try {
    // Opciones de guardado HTML
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    // Opciones para guardar PDF
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
 Asegúrese de reemplazar`"Arial Black"` y`"Lucida Console"` con las fuentes regulares predeterminadas que desee.

## Conclusión
Siguiendo estos pasos, habrá aprendido cómo manipular presentaciones de PowerPoint usando Aspose.Slides para Java de manera efectiva. Esta capacidad le permite automatizar tareas, personalizar presentaciones y mejorar sus aplicaciones Java con funcionalidades avanzadas de manejo de PowerPoint.
## Preguntas frecuentes
### ¿Puede Aspose.Slides para Java funcionar con versiones anteriores de JDK?
Aspose.Slides para Java requiere JDK 1.8 o superior para compatibilidad.
### ¿Cómo puedo obtener una licencia temporal de Aspose.Slides para Java?
 Puede obtener una licencia temporal de[aquí](https://purchase.aspose.com/temporary-license/).
### ¿Dónde puedo encontrar documentación más detallada sobre Aspose.Slides para Java?
 Explora la documentación completa[aquí](https://reference.aspose.com/slides/java/).
### ¿Existe soporte comunitario disponible para Aspose.Slides para Java?
 Sí, puedes obtener apoyo de la comunidad.[aquí](https://forum.aspose.com/c/slides/11).
### ¿Puedo probar Aspose.Slides para Java gratis?
 Sí, descarga una versión de prueba gratuita[aquí](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
