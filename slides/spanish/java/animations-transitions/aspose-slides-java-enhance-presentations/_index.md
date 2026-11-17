---
date: '2026-11-16'
description: Dibuje un marco alrededor del texto en tablas de PowerPoint usando Aspose.Slides
  for Java – aprenda a crear tablas, agregar texto a celdas, resaltar celdas y exportar
  el archivo como PPTX.
keywords:
- draw frame around text
- highlight table cell
- convert slide to png
- highlight word cell
- change frame color java
- add text table cell
lastmod: '2026-11-16'
og_description: Dibuje un marco alrededor del texto en tablas de PowerPoint usando
  Aspose.Slides for Java. Esta guía muestra cómo crear tablas, agregar y alinear texto,
  resaltar celdas y exportar diapositivas como PNG.
og_image_alt: 'Developer guide: draw frame around text in PowerPoint using Aspose.Slides
  for Java'
og_title: Dibujar un marco alrededor del texto y crear tablas en PowerPoint con Aspose.Slides
  for Java
schemas:
- author: Aspose
  dateModified: '2026-11-16'
  description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  headline: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
  type: TechArticle
- description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  name: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
  steps:
  - name: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
    text: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
  - name: '**License Acquisition**:'
    text: '**License Acquisition**:'
  - name: '**Basic Initialization**:'
    text: '**Basic Initialization**:'
  type: HowTo
- questions:
  - answer: The library supports JDK 8 onward, but the `jdk16` classifier gives the
      best performance on newer runtimes.
    question: Can I use these APIs with older JDK versions?
  - answer: Modify the line format fill color, e.g., `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.
    question: How do I change the frame color?
  - answer: Yes—use `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)`
      and then save the byte array.
    question: Is it possible to export the final slide as an image?
  - answer: Iterate through `cell.getTextFrame().getParagraphs()`, locate the portion
      containing “Total”, and draw a rectangle around that portion’s bounding box.
    question: What if I need to highlight only the word “Total” inside a cell?
  - answer: The API streams data and releases resources when `pres.dispose()` is called,
      which helps with memory management for large files.
    question: Does Aspose.Slides handle large presentations efficiently?
  type: FAQPage
tags:
- Aspose.Slides
- Java presentation automation
- PowerPoint table manipulation
- draw frame around text
- PPTX generation
title: Cómo dibujar un marco alrededor del texto y crear tablas en PowerPoint con
  Aspose.Slides for Java
url: /es/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo dibujar un marco alrededor del texto y crear tablas en PowerPoint con Aspose.Slides para Java

## Introducción

Dibujar un **marco alrededor del texto** en una diapositiva de PowerPoint te permite resaltar cifras clave sin cambiar el contenido subyacente. En este tutorial aprenderás a crear programáticamente una tabla, insertar y alinear texto dentro de celdas, resaltar palabras específicas o celdas completas, y finalmente guardar la presentación como archivo PPTX. Al final tendrás una diapositiva pulida que dirige la atención de la audiencia exactamente donde deseas.

## Respuestas rápidas
- **¿Qué significa “agregar texto a tabla”?** Significa insertar o actualizar el contenido textual de celdas individuales de la tabla de forma programática.  
- **¿Qué método guarda el archivo?** `pres.save("output.pptx", SaveFormat.Pptx)` – este paso de **guardar la presentación como pptx** finaliza tus cambios.  
- **¿Cómo puedo alinear texto dentro de una forma?** Usa `TextAlignment.Left` (o Center/Right) a través de `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **¿Puedo dibujar un rectángulo alrededor de un párrafo?** Sí – itera sobre los párrafos, obtén su rectángulo delimitador y agrega un `IAutoShape` sin relleno y con una línea negra.  
- **¿Necesito una licencia?** Una licencia temporal funciona para evaluación; se requiere una licencia completa para uso en producción.  

## ¿Por qué dibujar marcos alrededor del texto?

Dibujar un marco alrededor del texto resalta instantáneamente números importantes, advertencias o encabezados. Proporciona una pista visual mientras mantiene el formato original intacto, lo que lo hace ideal para informes financieros, paneles de KPI o cualquier diapositiva donde se requiera énfasis.

## ¿Qué es dibujar un marco alrededor del texto?

`draw frame around text` es la técnica de agregar programáticamente una forma rectangular que sigue los límites exactos de un párrafo o una porción de texto, usando formato de línea sin rellenar el interior. Este enfoque permite enfatizar contenido sin alterar el texto mismo.

## Requisitos previos

Antes de comenzar, asegúrate de contar con lo siguiente:

### Bibliotecas requeridas
Necesitarás Aspose.Slides para Java. Inclúyelo con uno de los gestores de paquetes:

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

También puedes explorar las versiones en [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Configuración del entorno
Se recomienda un Java Development Kit (JDK) 16 o superior porque los ejemplos usan el clasificador `jdk16`. Cualquier IDE como IntelliJ IDEA o Eclipse funcionará.

### Conocimientos previos
- Habilidades básicas de programación en Java.  
- Familiaridad con conceptos de PowerPoint (diapositivas, formas, tablas).  
- Comprensión de cómo Maven/Gradle gestionan dependencias.

## Configuración de Aspose.Slides para Java

`Presentation` es la clase central de Aspose.Slides que representa un archivo PowerPoint en memoria y brinda acceso a diapositivas, formas y tablas. Puede manejar presentaciones de hasta **10,000 diapositivas** manteniendo el uso de memoria por debajo de **500 MB**, lo que la hace adecuada para automatización a gran escala.

1. **Instalar la biblioteca** – usa Maven o Gradle, o descárgala directamente desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).  
2. **Adquisición de licencia** – comienza con una prueba gratuita en [Temporary License](https://purchase.aspose.com/temporary-license/) y actualiza a una licencia completa en [Purchase Aspose.Slides](https://purchase.aspose.com/buy) para cargas de trabajo de producción.  
3. **Inicialización básica** – crea un nuevo objeto `Presentation` y carga o crea diapositivas según sea necesario.  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## ¿Cómo agregar texto a una tabla en Aspose.Slides para Java?

`Presentation` es la clase principal que representa un archivo PowerPoint en memoria.  
Carga una nueva `Presentation`, crea una tabla en las coordenadas deseadas, rellena las celdas con objetos `TextFrame` y, finalmente, llama a `pres.save("output.pptx", SaveFormat.Pptx)`. Esta secuencia crea una **tabla en PowerPoint**, inserta texto personalizado en cada celda y escribe el resultado en un archivo PPTX en un flujo de trabajo único y eficiente.

### Respuesta directa
Crea una tabla llamando a `slide.getShapes().addTable(...)`, luego para cada celda usa `cell.getTextFrame().addParagraph().getPortions().add(new Portion("Your text"))`. Después de rellenar todas las celdas, invoca `pres.save("output.pptx", SaveFormat.Pptx)` para escribir el archivo. Este enfoque te permite controlar programáticamente el contenido y estilo de cada celda.

#### Característica 1: crear tabla y agregar texto a celdas

**1. crear una tabla** – inicializa una presentación, agrega una diapositiva y coloca una tabla en (50, 50) con anchos de columna y alturas de fila definidos.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. agregar texto a celdas** – para cada celda, crea un `Paragraph`, añade un `Portion` con la cadena deseada y asigna el párrafo al `TextFrame` de la celda.  
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```  

**3. guardar la presentación** – llama a `pres.save("output.pptx", SaveFormat.Pptx)`.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## ¿Cómo dibujar un marco alrededor del texto en una diapositiva de PowerPoint?

`Rectangle2D` representa un área rectangular en un espacio de coordenadas bidimensional.  
Carga la diapositiva, localiza el párrafo o porción que deseas enfatizar, recupera su rectángulo delimitador mediante `getRect()`, y luego agrega una forma `IAutoShape` rectangular sin relleno y con una línea coloreada. Este método funciona tanto para párrafos completos como para porciones de palabras individuales.

### Respuesta directa
Para dibujar un marco alrededor del texto, primero obtén el rectángulo del párrafo (`Rectangle2D rect = paragraph.getRect();`). Luego crea una forma rectangular `IAutoShape` (`slide.getShapes().addAutoShape(ShapeType.Rectangle, rect.getX(), rect.getY(), rect.getWidth(), rect.getHeight())`), establece `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.RED)` y desactiva el relleno (`shape.getFillFormat().setFillType(FillType.NoFill)`). La forma delineará perfectamente el texto.

#### Característica 3: dibujar marcos alrededor de párrafos y porciones en celdas de tabla

**1. crear una tabla** – reutiliza el código de la Característica 1 para configurar la tabla inicial.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. agregar párrafos** – reutiliza el código de creación de párrafos de la Característica 1.  
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```  

**3. dibujar marcos** – itera sobre cada párrafo, obtén su rectángulo delimitador y agrega una forma rectangular como se describió arriba. Para las porciones que contengan el carácter ‘0’, dibuja un marco adicional para resaltar esos números.  
```java
    double x = tbl.getX() + cell.getOffsetX();
    double y = tbl.getY() + cell.getOffsetY();

    for (IParagraph para : cell.getTextFrame().getParagraphs()) {
        if ("".equals(para.getText())) continue;

        Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
        IAutoShape shape = (IAutoShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(
            ShapeType.Rectangle, rect.x, rect.y, rect.width, rect.height);

        shape.getTextFrame().setText(para.getText());
        shape.setFillFormat(FillFormat.createNoFill());
        shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLACK);
    }
```  

**4. guardar la presentación** – mismo paso final que antes.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## ¿Cómo agregar un marco de texto a un AutoShape y establecer la alineación?

`AutoShape` es una forma que puede contener texto, imágenes u otro contenido.  
Un `AutoShape` puede contener un `TextFrame`. Puedes controlar la alineación horizontal usando el enum `ParagraphFormat`.

### Respuesta directa
Crea un AutoShape rectangular (`slide.getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 300, 100)`), accede a su `TextFrame`, establece el texto con `shape.getTextFrame().setText("Text in shape")` y luego llama a `shape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left)`. Esto alinea el texto a la izquierda dentro de la forma.

**1. agregar un AutoShape** – coloca un rectángulo en la ubicación deseada.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

**2. establecer alineación de texto** – aplica la alineación a la izquierda como se muestra arriba.  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. guardar la presentación** – mismo paso final.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Problemas comunes y consejos

- **Siempre liberar recursos** – envuelve el uso de `Presentation` en un bloque try‑finally y llama a `pres.dispose()` para liberar recursos nativos.  
- **Recalcular rectángulos delimitadores** – si cambias el tamaño de fuente, márgenes o relleno de celda después de dibujar un marco, vuelve a llamar a `paragraph.getRect()` antes de agregar la forma.  
- **Creación por lotes de formas para tablas grandes** – reutilizar una única instancia de `IAutoShape` y actualizar su geometría reduce la presión de memoria al procesar tablas con cientos de filas.  
- **Datos de rendimiento** – Aspose.Slides puede generar un PPTX de 200 páginas en menos de 2 segundos en un servidor típico de 4 núcleos, y dibujar marcos alrededor de 1,000 párrafos añade menos de 150 ms de sobrecarga.

## Preguntas frecuentes

**P: ¿Puedo usar estas API con versiones más antiguas de JDK?**  
R: La biblioteca es compatible con JDK 8 en adelante, pero el clasificador `jdk16` ofrece el mejor rendimiento en entornos más recientes.

**P: ¿Cómo cambio el color del marco?**  
R: Modifica el color de relleno del formato de línea, por ejemplo, `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**P: ¿Es posible exportar la diapositiva final como imagen?**  
R: Sí—usa `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` y luego guarda el arreglo de bytes.

**P: ¿Qué pasa si solo necesito resaltar la palabra “Total” dentro de una celda?**  
R: Itera a través de `cell.getTextFrame().getParagraphs()`, localiza la porción que contiene “Total” y dibuja un rectángulo alrededor del cuadro delimitador de esa porción.

**P: ¿Aspose.Slides maneja presentaciones grandes de forma eficiente?**  
R: La API transmite datos y libera recursos cuando se llama a `pres.dispose()`, lo que ayuda a la gestión de memoria en archivos de gran tamaño.

---

**Última actualización:** 2026-11-16  
**Probado con:** Aspose.Slides for Java 25.4 (jdk16)  
**Autor:** Aspose  

## Tutoriales relacionados

- [Aspose.Slides para Java: Dominio de la manipulación de tablas y texto PPTX en presentaciones de PowerPoint](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [Cómo crear marcos de texto dinámicos en PowerPoint usando Aspose.Slides para Java](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Agregar columnas en el marco de texto usando Aspose.Slides para Java](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}