---
date: '2026-06-23'
description: Aprenda cómo crear table en PowerPoint, add text to table cells, draw
  frames around text, y save presentation como pptx usando Aspose.Slides for Java.
keywords:
- create table in powerpoint
- add text to table
- draw frame around text
- highlight table cells
- save presentation as pptx
schemas:
- author: Aspose
  dateModified: '2026-06-23'
  description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  headline: How to create table in PowerPoint and draw frames with Aspose.Slides for
    Java
  type: TechArticle
- description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  name: How to create table in PowerPoint and draw frames with Aspose.Slides for Java
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
title: Cómo crear table en PowerPoint y dibujar frames con Aspose.Slides for Java
url: /es/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo crear una tabla en PowerPoint y dibujar marcos con Aspose.Slides for Java

## Introducción

Crear una **create table in PowerPoint** de forma programática puede ahorrarle horas de formato manual, especialmente cuando necesita resaltar números clave o agregar notas explicativas. En este tutorial descubrirá cómo agregar texto a las celdas de la tabla, dibujar marcos alrededor de párrafos específicos, establecer una alineación de texto precisa y, finalmente, **save presentation as pptx** – todo con la poderosa API Aspose.Slides for Java. Al final tendrá una diapositiva que se ve pulida, es fácil de leer y atrae instantáneamente la atención de la audiencia a los datos más importantes.

## Respuestas rápidas
- **What does “add text to table” mean?** Significa insertar o actualizar el contenido textual de celdas individuales de la tabla de forma programática.  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – este paso **save presentation as pptx** finaliza sus cambios.  
- **How can I align text inside a shape?** Use `TextAlignment.Left` (o Center/Right) a través de `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Can I draw a rectangle around a paragraph?** Sí – itere sobre los párrafos, obtenga su rectángulo delimitador y agregue un `IAutoShape` sin relleno y con una línea negra.  
- **Do I need a license?** Una licencia temporal funciona para evaluación; se requiere una licencia completa para uso en producción.  

## ¿Por qué dibujar marcos alrededor del texto?

Dibujar un marco (o rectángulo) alrededor de un párrafo o una porción específica—como cualquier texto que contenga el carácter **'0'**—atrae instantáneamente la atención de la audiencia a ese contenido. Proporciona una pista visual clara sin alterar el texto subyacente, lo que lo hace ideal para resaltar cifras clave, advertencias o separar secciones dentro de una diapositiva.

## Requisitos previos

Antes de sumergirse en el código, asegúrese de tener lo siguiente:

### Bibliotecas requeridas
Necesitará Aspose.Slides for Java. Aquí se muestra cómo incluirlo usando Maven o Gradle:

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

### Configuración del entorno
Asegúrese de tener instalado un Java Development Kit (JDK), preferiblemente JDK 16 o posterior, ya que este ejemplo usa el clasificador `jdk16`.

### Requisitos de conocimientos
- Comprensión básica de la programación Java.  
- Familiaridad con software de presentaciones como PowerPoint.  
- Experiencia usando un Entorno de Desarrollo Integrado (IDE) como IntelliJ IDEA o Eclipse.

## Configuración de Aspose.Slides para Java

`Presentation` es la clase central de Aspose.Slides que representa un archivo PowerPoint en memoria y proporciona acceso a diapositivas, formas y tablas. Para comenzar a usar Aspose.Slides, siga estos pasos:

1. **Install the Library**: Use Maven o Gradle para gestionar dependencias, o descárguelo directamente desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **Adquisición de licencia**:
   - Comience con una prueba gratuita descargando una licencia temporal desde [Temporary License](https://purchase.aspose.com/temporary-license/).
   - Para acceso completo, considere comprar una licencia en [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

3. **Inicialización básica**:  
   Initialize your presentation environment with the following code snippet:  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## ¿Cómo agregar texto a una tabla en Aspose.Slides for Java?

Cargue una nueva `Presentation`, cree una tabla en las coordenadas deseadas, rellene las celdas con objetos `TextFrame` y finalmente llame a `pres.save("output.pptx", SaveFormat.Pptx)`. Esta secuencia crea una **create table in PowerPoint**, inserta texto personalizado en cada celda y escribe el resultado en un archivo PPTX en un flujo de trabajo único y eficiente.

### Funcionalidad 1: Crear tabla y agregar texto a celdas

#### Descripción general
Esta funcionalidad muestra cómo **create table**, luego **add text to table** celdas y después **save presentation as pptx**.

#### Pasos

**1. Create a Table**  
Primero, inicialice su presentación y agregue una tabla en la posición (50, 50) con anchos de columna y alturas de fila especificados.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Add Text to Cells**  
Cree párrafos con porciones de texto y agréguelos a una celda específica.  
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

**3. Guardar la presentación**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

### Funcionalidad 2: Agregar TextFrame a AutoShape y establecer alineación

#### Descripción general
Aprenda cómo agregar un marco de texto con alineación específica a una auto forma—un ejemplo de **set text alignment java**.

#### Pasos

Una AutoShape es una forma que puede contener texto y gráficos.

**1. Add an AutoShape**  
Agregue un rectángulo como AutoShape en la posición (400, 100) con dimensiones especificadas.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

`TextAlignment` enum defines horizontal alignment options for text within a shape.

**2. Set Text Alignment**  
Establezca el texto a “Text in shape” y alinéelo a la izquierda.  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. Guardar la presentación**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

### Funcionalidad 3: Dibujar marcos alrededor de párrafos y porciones en celdas de tabla

#### Descripción general
Esta funcionalidad se centra en **draw frames around text** e incluso **draw rectangle around paragraph** para porciones que contienen el carácter ‘0’.

#### Pasos

`IAutoShape` representa un objeto de forma que puede dibujarse en una diapositiva, como rectángulos usados para marcos.

**1. Create a Table**  
Reutilice el código de “Create Table and Add Text to Cells” para la configuración inicial.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Add Paragraphs**  
Reutilice el código de creación de párrafos de la funcionalidad anterior.  
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

**3. Draw Frames**  
Itere sobre los párrafos y porciones para dibujar marcos a su alrededor.  
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

**4. Guardar la presentación**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Problemas comunes y consejos

- **Null checks** – Siempre envuelva el uso de `Presentation` en un bloque try‑finally para asegurar que `pres.dispose()` se ejecute y libere los recursos nativos.  
- **Bounding rectangle accuracy** – El rectángulo devuelto por `para.getRect()` refleja el diseño actual; si cambia el tamaño de fuente o los márgenes, vuelva a calcular el rectángulo antes de dibujar el marco.  
- **Performance** – Al trabajar con tablas muy grandes, considere agrupar la adición de formas o reutilizar una única instancia de `IAutoShape` con geometría actualizada para reducir la sobrecarga de memoria.  

## Preguntas frecuentes

**Q: ¿Puedo usar estas API con versiones más antiguas de JDK?**  
A: La biblioteca admite JDK 8 en adelante, pero el clasificador `jdk16` ofrece el mejor rendimiento en entornos de ejecución más recientes.

**Q: ¿Cómo cambio el color del marco?**  
A: Modifique el color de relleno del formato de línea, por ejemplo, `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: ¿Es posible exportar la diapositiva final como una imagen?**  
A: Sí—use `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` y luego guarde el arreglo de bytes.

**Q: ¿Qué pasa si necesito resaltar solo la palabra “Total” dentro de una celda?**  
A: Itere a través de `cell.getTextFrame().getParagraphs()`, localice la porción que contiene “Total” y dibuje un rectángulo alrededor del cuadro delimitador de esa porción.

**Q: ¿Aspose.Slides maneja presentaciones grandes de manera eficiente?**  
A: La API transmite datos y libera recursos cuando se llama a `pres.dispose()`, lo que ayuda con la gestión de memoria para archivos grandes.

---

**Última actualización:** 2026-06-23  
**Probado con:** Aspose.Slides for Java 25.4 (jdk16)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Aspose.Slides for Java&#58; Dominio de tablas PPTX y manipulación de texto en presentaciones PowerPoint](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [Cómo crear marcos de texto dinámicos en PowerPoint usando Aspose.Slides for Java](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Agregar columnas en el marco de texto usando Aspose.Slides for Java](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}