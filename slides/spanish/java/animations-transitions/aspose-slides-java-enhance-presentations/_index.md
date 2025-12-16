---
date: '2025-12-10'
description: Aprenda cómo agregar texto a una tabla y dibujar marcos alrededor del
  texto en PowerPoint usando Aspose.Slides para Java. Esta guía cubre la creación
  de tablas, la configuración de la alineación del texto y el encuadre del contenido.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Aspose.Slides para Java – agregar texto a tabla y manipulación de marcos
url: /es/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Dominar la Manipulación de Tablas y Marcos en Presentaciones con Aspose.Slides para Java

## Introducción

Presentar datos de manera eficaz puede ser un desafío en PowerPoint. Ya seas un desarrollador de software o un diseñador de presentaciones, **add text to table** celdas y dibujar marcos alrededor de párrafos clave para que tus diapositivas destaquen. En este tutorial verás exactamente cómo **add text to table**, alinearlo y dibujar marcos alrededor del texto — todo con Aspose.Slides para Java. Al final, podrás crear presentaciones pulidas que resaltan la información correcta en el momento adecuado.

¿Listo para transformar tus presentaciones? ¡Comencemos!

## Respuestas rápidas
- **What does “add text to table” mean?** Significa insertar o actualizar el contenido textual de celdas individuales de una tabla de forma programática.  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – this **save presentation as pptx** step finalizes your changes.  
- **How can I align text inside a shape?** Usa `TextAlignment.Left` (o Center/Right) a través de `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Can I draw a rectangle around a paragraph?** Sí – itera sobre los párrafos, obtén su rectángulo delimitador y agrega un `IAutoShape` sin relleno y con una línea negra.  
- **Do I need a license?** Una licencia temporal funciona para evaluación; se requiere una licencia completa para uso en producción.

## Requisitos previos

Antes de sumergirte en el código, asegúrate de contar con lo siguiente:

### Bibliotecas requeridas
Necesitarás Aspose.Slides para Java. Aquí se muestra cómo incluirlo usando Maven o Gradle:

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
Asegúrate de tener instalado un Java Development Kit (JDK), preferiblemente JDK 16 o posterior, ya que este ejemplo usa el clasificador `jdk16`.

### Prerrequisitos de conocimientos
- Comprensión básica de la programación Java.  
- Familiaridad con software de presentación como PowerPoint.  
- Experiencia usando un Entorno de Desarrollo Integrado (IDE) como IntelliJ IDEA o Eclipse.

## Configuración de Aspose.Slides para Java

Para comenzar a usar Aspose.Slides, sigue estos pasos:

1. **Install the Library**: Usa Maven o Gradle para gestionar dependencias, o descárgalo directamente desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **License Acquisition**:
   - Comienza con una prueba gratuita descargando una licencia temporal desde [Temporary License](https://purchase.aspose.com/temporary-license/).
   - Para acceso completo, considera comprar una licencia en [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

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

## ¿Por qué agregar texto a la tabla y dibujar marcos?

Agregar texto a una tabla te permite presentar datos estructurados de forma clara, mientras que dibujar marcos alrededor de párrafos o porciones específicas (p. ej., aquellas que contienen el carácter **'0'**) dirige la atención del público a valores importantes. Esta combinación es perfecta para informes financieros, paneles de control o cualquier diapositiva donde necesites resaltar números clave sin desorden.

## Cómo agregar texto a la tabla en Aspose.Slides para Java

### Función 1: Crear tabla y agregar texto a celdas

#### Visión general
Esta función muestra cómo **how to create table**, luego **add text to table** celdas y después **save presentation as pptx**.

#### Pasos

**1. Create a Table**  
Primero, inicializa tu presentación y agrega una tabla en la posición (50, 50) con anchos de columna y alturas de fila especificados.
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
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Función 2: Agregar TextFrame a AutoShape y establecer alineación

#### Visión general
Aprende a agregar un marco de texto con alineación específica a una autoforma—un ejemplo de **set text alignment java**.

#### Pasos

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
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Función 3: Dibujar marcos alrededor de párrafos y porciones en celdas de tabla

#### Visión general
Esta función se centra en **draw frames around text** e incluso **draw rectangle around paragraph** para porciones que contienen el carácter ‘0’.

#### Pasos

**1. Create a Table**  
Reutiliza el código de “Create Table and Add Text to Cells” para la configuración inicial.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Paragraphs**  
Reutiliza el código de creación de párrafos de la función anterior.
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
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Conclusión
Al seguir esta guía, puedes **add text to table**, alinear texto dentro de formas y **draw frames around text** para enfatizar información importante. Dominar estas técnicas te permite crear presentaciones altamente pulidas y basadas en datos con Aspose.Slides para Java. Para seguir explorando, prueba combinar estas funciones con gráficos, animaciones o exportar a PDF.

## Preguntas frecuentes

**Q: Can I use these APIs with older JDK versions?**  
A: La biblioteca soporta JDK 8 en adelante, pero el clasificador `jdk16` ofrece el mejor rendimiento en entornos más recientes.

**Q: How do I change the frame color?**  
A: Modifica el color de relleno del formato de línea, por ejemplo, `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Is it possible to export the final slide as an image?**  
A: Sí—usa `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` y luego guarda el arreglo de bytes.

**Q: What if I need to highlight only the word “Total” inside a cell?**  
A: Itera a través de `cell.getTextFrame().getParagraphs()`, localiza la porción que contiene “Total” y dibuja un rectángulo alrededor del cuadro delimitador de esa porción.

**Q: Does Aspose.Slides handle large presentations efficiently?**  
A: La API transmite datos y libera recursos cuando se llama a `pres.dispose()`, lo que ayuda a la gestión de memoria para archivos grandes.

---

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2025-12-10  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}