---
date: '2026-02-09'
description: Aprenda a dibujar marcos alrededor del texto y a agregar texto a las
  celdas de tabla en PowerPoint usando Aspose.Slides para Java. Este tutorial cubre
  la creación de tablas, la configuración de la alineación del texto y el guardado
  de la presentación como pptx.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Cómo dibujar marcos y agregar texto a una tabla con Aspose.Slides para Java
url: /es/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo dibujar marcos y agregar texto a una tabla en presentaciones con Aspose.Slides para Java

## Introduction

Presentar datos claramente en PowerPoint puede ser un verdadero obstáculo, especialmente cuando necesitas **add text to table** en celdas y resaltar valores importantes con indicaciones visuales. En esta guía aprenderás **how to draw frames** alrededor de párrafos específicos, establecer la alineación del texto dentro de formas y, finalmente, **save presentation as pptx** — todo usando Aspose.Slides para Java. Al final tendrás una presentación pulida que dirige la mirada de la audiencia exactamente donde deseas.

¿Listo para que tus diapositivas destaquen? Repasemos el proceso paso a paso.

## Quick Answers
- **What does “add text to table” mean?** Significa insertar o actualizar el contenido textual de celdas individuales de la tabla de forma programática.  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – este paso **save presentation as pptx** finaliza tus cambios.  
- **How can I align text inside a shape?** Usa `TextAlignment.Left` (o Center/Right) mediante `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Can I draw a rectangle around a paragraph?** Sí – itera sobre los párrafos, obtén su rectángulo delimitador y agrega un `IAutoShape` sin relleno y con una línea negra.  
- **Do I need a license?** Una licencia temporal funciona para evaluación; se requiere una licencia completa para uso en producción.  

## Why draw frames around text?

Dibujar un marco (o rectángulo) alrededor de un párrafo o una porción específica (por ejemplo, cualquier texto que contenga el carácter **'0'**) atrae la atención de inmediato. Esta técnica es ideal para:

- Resaltar cifras financieras clave en una tabla.  
- Enfatizar advertencias o notas importantes en una diapositiva.  
- Crear separadores visuales sin añadir formas adicionales manualmente.

## Prerequisites

Before diving into the code, ensure you have the following:

### Required Libraries
Necesitarás Aspose.Slides para Java. Así es como puedes incluirlo usando Maven o Gradle:

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

### Environment Setup
Asegúrate de tener instalado un Java Development Kit (JDK), preferiblemente JDK 16 o posterior, ya que este ejemplo usa el clasificador `jdk16`.

### Knowledge Prerequisites
- Comprensión básica de la programación en Java.  
- Familiaridad con software de presentaciones como PowerPoint.  
- Experiencia usando un Entorno de Desarrollo Integrado (IDE) como IntelliJ IDEA o Eclipse.

## Setting Up Aspose.Slides for Java

Para comenzar a usar Aspose.Slides, sigue estos pasos:

1. **Install the Library**: Usa Maven o Gradle para gestionar dependencias, o descárgalo directamente de [lanzamientos de Aspose.Slides para Java](https://releases.aspose.com/slides/java/).

2. **License Acquisition**:
   - Comienza con una prueba gratuita descargando una licencia temporal de [Licencia temporal](https://purchase.aspose.com/temporary-license/).
   - Para acceso completo, considera comprar una licencia en [Comprar Aspose.Slides](https://purchase.aspose.com/buy).

3. **Basic Initialization**:
Inicializa tu entorno de presentación con el siguiente fragmento de código:
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```

## How to Add Text to Table in Aspose.Slides for Java

### Feature 1: Create Table and Add Text to Cells

#### Overview
Esta funcionalidad muestra cómo **create table**, luego **add text to table** en celdas y después **save presentation as pptx**.

#### Steps

**1. Create a Table**  
Primero, inicializa tu presentación y agrega una tabla en la posición (50, 50) con los anchos de columna y alturas de fila especificados.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Text to Cells**  
Crea párrafos con porciones de texto y añádelos a una celda específica.
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

**3. Save the Presentation**  
Guarda la presentación
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Feature 2: Add TextFrame to AutoShape and Set Alignment

#### Overview
Aprende cómo agregar un marco de texto con alineación específica a una autoforma — un ejemplo de **set text alignment java**.

#### Steps

**1. Add an AutoShape**  
Agrega un rectángulo como AutoShape en la posición (400, 100) con dimensiones especificadas.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

**2. Set Text Alignment**  
Establece el texto a “Text in shape” y alinéalo a la izquierda.
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```

**3. Save the Presentation**  
Guarda la presentación
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Feature 3: Draw Frames around Paragraphs and Portions in Table Cells

#### Overview
Esta funcionalidad se centra en **draw frames around text** e incluso **draw rectangle around paragraph** para porciones que contienen el carácter ‘0’.

#### Steps

**1. Create a Table**  
Reutiliza el código de “Create Table and Add Text to Cells” para la configuración inicial.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Paragraphs**  
Reutiliza el código de creación de párrafos de la funcionalidad anterior.
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
Itera sobre los párrafos y porciones para dibujar marcos alrededor de ellos.
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

**4. Save the Presentation**  
Guarda la presentación
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Common Pitfalls & Tips

- **Null checks** – Siempre envuelve el uso de `Presentation` en un bloque try‑finally para asegurar que `pres.dispose()` se ejecute y libere los recursos nativos.  
- **Bounding rectangle accuracy** – El rectángulo devuelto por `para.getRect()` refleja el diseño actual; si cambias el tamaño de fuente o los márgenes, vuelve a calcular el rectángulo antes de dibujar el marco.  
- **Performance** – Al trabajar con tablas muy grandes, considera agrupar la adición de formas o reutilizar una única instancia de `IAutoShape` con geometría actualizada para reducir la sobrecarga de memoria.

## Frequently Asked Questions

**Q: Can I use these APIs with older JDK versions?**  
A: La biblioteca soporta JDK 8 en adelante, pero el clasificador `jdk16` brinda el mejor rendimiento en entornos más recientes.

**Q: How do I change the frame color?**  
A: Modifica el color de relleno del formato de línea, por ejemplo, `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Is it possible to export the final slide as an image?**  
A: Sí—usa `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` y luego guarda el arreglo de bytes.

**Q: What if I need to highlight only the word “Total” inside a cell?**  
A: Itera a través de `cell.getTextFrame().getParagraphs()`, localiza la porción que contiene “Total” y dibuja un rectángulo alrededor del cuadro delimitador de esa porción.

**Q: Does Aspose.Slides handle large presentations efficiently?**  
A: La API transmite datos y libera recursos cuando se llama a `pres.dispose()`, lo que ayuda a la gestión de memoria en archivos grandes.

{{< blocks/products/products-backtop-button >}}

**Última actualización:** 2026-02-09  
**Probado con:** Aspose.Slides for Java 25.4 (jdk16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}