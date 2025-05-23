---
"description": "Convierta presentaciones de PowerPoint a HTML conservando las fuentes originales utilizando Aspose.Slides para Java."
"linktitle": "Convertir una presentación a HTML conservando las fuentes originales en Java Slides"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Convertir una presentación a HTML conservando las fuentes originales en Java Slides"
"url": "/es/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Convertir una presentación a HTML conservando las fuentes originales en Java Slides


## Introducción a la conversión de presentaciones a HTML con conservación de fuentes originales en diapositivas de Java

En este tutorial, exploraremos cómo convertir una presentación de PowerPoint (PPTX) a HTML conservando las fuentes originales mediante Aspose.Slides para Java. Esto garantizará que el HTML resultante se asemeje lo más posible a la presentación original.

## Paso 1: Configuración del proyecto
Antes de sumergirnos en el código, asegurémonos de que tienes la configuración necesaria:

1. Descargue Aspose.Slides para Java: si aún no lo ha hecho, descargue e incluya la biblioteca Aspose.Slides para Java en su proyecto.

2. Cree un proyecto Java: configure un proyecto Java en su IDE favorito y asegúrese de tener una carpeta "lib" donde pueda colocar el archivo JAR Aspose.Slides.

3. Importar clases requeridas: importe las clases necesarias al comienzo de su archivo Java:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Paso 2: Convertir la presentación a HTML con fuentes originales

Ahora, convirtamos una presentación de PowerPoint a HTML conservando las fuentes originales:

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
    
    // Guardar la presentación como HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // Desechar el objeto de presentación
    if (pres != null) pres.dispose();
}
```

En este fragmento de código:

- Cargamos la presentación de PowerPoint de entrada usando `Presentation`.

- Definimos una lista de fuentes (`fontNameExcludeList`) que queremos excluir de la incrustación en el HTML. Esto es útil para excluir fuentes comunes como Calibri y Arial y así reducir el tamaño del archivo.

- Creamos una instancia de `EmbedAllFontsHtmlController` y pasarle la lista de exclusión de fuentes.

- Nosotros creamos `HtmlOptions` y configure un formateador HTML personalizado usando `HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Finalmente, guardamos la presentación como HTML con las opciones especificadas.

## Código fuente completo para convertir presentaciones a HTML conservando las fuentes originales en diapositivas de Java

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

En este tutorial, aprendiste a convertir una presentación de PowerPoint a HTML conservando las fuentes originales con Aspose.Slides para Java. Esto resulta útil si quieres mantener la fidelidad visual de tus presentaciones al compartirlas en la web.

## Preguntas frecuentes

### ¿Cómo descargo Aspose.Slides para Java?

Puede descargar Aspose.Slides para Java desde el sitio web de Aspose. Visite [aquí](https://downloads.aspose.com/slides/java/) para obtener la última versión.

### ¿Puedo personalizar la lista de fuentes excluidas?

Sí, puedes personalizar el `fontNameExcludeList` matriz para incluir o excluir fuentes específicas según sus requisitos.

### ¿Este método funciona para formatos de PowerPoint más antiguos como PPT?

Este ejemplo de código está diseñado para archivos PPTX. Si necesita convertir archivos PPT antiguos, es posible que deba realizar ajustes en el código.

### ¿Cómo puedo personalizar aún más la salida HTML?

Puedes explorar el `HtmlOptions` Clase para personalizar varios aspectos de la salida HTML, como el tamaño de la diapositiva, la calidad de la imagen y más.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}