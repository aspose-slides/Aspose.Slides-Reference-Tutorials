---
title: Conversión de presentaciones a HTML conservando fuentes originales en diapositivas Java
linktitle: Conversión de presentaciones a HTML conservando fuentes originales en diapositivas Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Convierta presentaciones de PowerPoint a HTML conservando las fuentes originales utilizando Aspose.Slides para Java.
weight: 14
url: /es/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introducción a la conversión de presentaciones a HTML conservando las fuentes originales en diapositivas Java

En este tutorial, exploraremos cómo convertir una presentación de PowerPoint (PPTX) a HTML conservando las fuentes originales usando Aspose.Slides para Java. Esto asegurará que el HTML resultante se parezca mucho a la apariencia de la presentación original.

## Paso 1: configurar el proyecto
Antes de profundizar en el código, asegurémonos de tener la configuración necesaria:

1. Descargue Aspose.Slides para Java: si aún no lo ha hecho, descargue e incluya la biblioteca Aspose.Slides para Java en su proyecto.

2. Cree un proyecto Java: configure un proyecto Java en su IDE favorito y asegúrese de tener una carpeta "lib" donde pueda colocar el archivo JAR Aspose.Slides.

3. Importe las clases necesarias: importe las clases necesarias al principio de su archivo Java:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Paso 2: convertir una presentación a HTML con fuentes originales

Ahora, conviertamos una presentación de PowerPoint a HTML conservando las fuentes originales:

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";

// Cargar la presentación
Presentation pres = new Presentation("input.pptx");

try {
    // Excluir fuentes de presentación predeterminadas como Calibri y Arial
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // Cree opciones HTML y configure el formateador HTML personalizado
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // Guarde la presentación como HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // Desechar el objeto de presentación.
    if (pres != null) pres.dispose();
}
```

En este fragmento de código:

-  Cargamos la presentación de PowerPoint de entrada usando`Presentation`.

- Definimos una lista de fuentes (`fontNameExcludeList`que queremos excluir de la incrustación en el HTML. Esto es útil para excluir fuentes comunes como Calibri y Arial para reducir el tamaño del archivo.

-  Creamos una instancia de`EmbedAllFontsHtmlController` y pásele la lista de exclusión de fuentes.

-  Nosotros creamos`HtmlOptions` y configurar un formateador HTML personalizado usando`HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Finalmente guardamos la presentación como HTML con las opciones especificadas.

## Código fuente completo para convertir presentaciones a HTML conservando las fuentes originales en diapositivas Java

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// excluir fuentes de presentación predeterminadas
	String[] fontNameExcludeList = {"Calibri", "Arial"};
	EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
	HtmlOptions htmlOptionsEmbed = new HtmlOptions();
	htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
	pres.save("input-PFDinDisplayPro-Regular-installed.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusión

En este tutorial, aprendió cómo convertir una presentación de PowerPoint a HTML conservando las fuentes originales usando Aspose.Slides para Java. Esto es útil cuando desea mantener la fidelidad visual de sus presentaciones al compartirlas en la web.

## Preguntas frecuentes

### ¿Cómo descargo Aspose.Slides para Java?

 Puede descargar Aspose.Slides para Java desde el sitio web de Aspose. Visita[aquí](https://downloads.aspose.com/slides/java/) para obtener la última versión.

### ¿Puedo personalizar la lista de fuentes excluidas?

 Sí, puedes personalizar el`fontNameExcludeList` matriz para incluir o excluir fuentes específicas según sus requisitos.

### ¿Este método funciona para formatos de PowerPoint más antiguos como PPT?

Este ejemplo de código está diseñado para archivos PPTX. Si necesita convertir archivos PPT más antiguos, es posible que deba realizar ajustes en el código.

### ¿Cómo puedo personalizar aún más la salida HTML?

 Puedes explorar el`HtmlOptions` clase para personalizar varios aspectos de la salida HTML, como el tamaño de la diapositiva, la calidad de la imagen y más.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
