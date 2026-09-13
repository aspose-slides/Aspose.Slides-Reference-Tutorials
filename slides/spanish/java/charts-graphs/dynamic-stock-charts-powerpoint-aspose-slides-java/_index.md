---
date: '2026-09-12'
description: Aprenda a usar Maven Aspose Slides para agregar y personalizar gráficos
  de acciones dinámicos en PowerPoint con Java. Incluye configuración, adición de
  series de datos, formato de líneas y guardado.
keywords:
- maven aspose slides
- add data series chart
- format chart lines
- customize chart java
lastmod: '2026-09-12'
og_description: El tutorial de Maven Aspose Slides muestra cómo crear y personalizar
  gráficos de acciones dinámicos en PowerPoint usando Java, abarcando series de datos,
  formato de líneas y guardado.
og_image_alt: Illustration of a Java-generated stock chart in PowerPoint using Aspose.Slides
og_title: 'Guía de Maven Aspose Slides: crear gráficos de acciones dinámicos en PowerPoint'
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to use Maven Aspose Slides to add and customize dynamic stock
    charts in PowerPoint with Java. Includes setup, adding data series, formatting
    lines, and saving.
  headline: 'Maven Aspose Slides: create dynamic stock charts in PowerPoint with Java'
  type: TechArticle
- questions:
  - answer: Yes. The library is pure Java, so you can run it in any servlet container
      or Spring Boot service.
    question: Can I use this code in a web application?
  - answer: Absolutely. It supports over 70 chart types, including Line, Bar, Pie,
      and Radar charts.
    question: Does Aspose.Slides support other chart types besides Stock?
  - answer: Use `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")`
      and then format the title as needed.
    question: How do I add a chart title programmatically?
  - answer: Practically, you can add tens of thousands of points; memory usage scales
      linearly, and the library streams data to keep the footprint low.
    question: Is there a limit to the number of data points per series?
  - answer: The latest version is always available under `com.aspose:aspose-slides:25.4`
      (or newer) on Maven Central.
    question: Which Maven coordinates should I use for the latest version?
  type: FAQPage
tags:
- maven aspose slides
- dynamic stock charts
- java charting
- aspose.slides
title: 'Maven Aspose Slides: crear gráficos de acciones dinámicos en PowerPoint con
  Java'
url: /es/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maven Aspose Slides: crear gráficos bursátiles dinámicos en PowerPoint con Java

## Introducción

**Maven Aspose Slides** le permite generar programáticamente presentaciones de PowerPoint sofisticadas desde Java. En este tutorial aprenderá a crear gráficos bursátiles dinámicos, añadir y formatear series de datos, personalizar líneas de gráficos y, finalmente, guardar el archivo. Ya sea que sea un analista financiero preparando informes trimestrales o un desarrollador creando presentaciones automatizadas, los pasos a continuación le ofrecen una solución completa y lista para producción.

**Lo que aprenderá**
- Cómo configurar Maven con Aspose.Slides para Java  
- Cómo añadir un gráfico bursátil y limpiar los datos predeterminados  
- Cómo **añadir series de datos al gráfico** y **formatear líneas del gráfico**  
- Cómo **personalizar elementos visuales específicos de Java en el gráfico**  
- Cómo guardar la presentación actualizada

¿Listo para convertir números crudos en visuales bursátiles llamativos? ¡Comencemos!

## Respuestas rápidas
- **¿Qué artefacto Maven necesito?** `aspose-slides` versión 25.4 (o más reciente).  
- **¿Puedo ejecutar esto en cualquier SO?** Sí, la biblioteca es Java puro y funciona en Windows, macOS y Linux.  
- **¿Necesito una licencia para desarrollo?** Una licencia temporal gratuita funciona para pruebas; se requiere una licencia completa para producción.  
- **¿Qué tipos de gráficos son compatibles?** Más de 70 tipos de gráficos incorporados, incluidos Stock, Line y Bar.  
- **¿Qué tamaño de presentación puedo procesar?** Aspose.Slides puede manejar archivos con más de 500 diapositivas sin cargar todo el archivo en memoria.

## ¿Qué es Maven Aspose Slides?

`Aspose.Slides for Java` es una API Java que permite crear, manipular y convertir archivos PowerPoint sin Microsoft Office. La integración con Maven simplifica la gestión de dependencias, permitiéndole obtener la biblioteca directamente de Maven Central.

## ¿Por qué usar Maven Aspose Slides para gráficos bursátiles?

Aspose.Slides admite **más de 70 tipos de gráficos** y puede renderizar presentaciones de cientos de páginas en menos de un segundo en hardware de servidor típico. Sus características de **línea alta‑baja** y **barras arriba/abajo** le brindan un control preciso sobre visualizaciones financieras, mucho más allá de lo que ofrece la interfaz de PowerPoint.

## Requisitos previos

- **Java Development Kit (JDK)** – versión 11 o superior.  
- **IDE** – IntelliJ IDEA, Eclipse o cualquier editor que prefiera.  
- **Aspose.Slides for Java** – versión 25.4 (la más reciente al momento de escribir).  

### Configuración de Aspose.Slides para Java

#### Maven
Para integrar Aspose.Slides en su proyecto usando Maven, añada la siguiente dependencia a su `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle
Para usuarios de Gradle, incluya esto en su `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Descarga directa
Alternativamente, descargue el JAR más reciente de [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Adquisición de licencia** – comience con una prueba gratuita o solicite una licencia temporal. Para uso comercial, adquiera una licencia completa.

Para una referencia detallada de la API, consulte la [documentación de Aspose.Slides](https://docs.aspose.com/slides/java/).

## Cómo crear un gráfico bursátil dinámico paso a paso

Cargue su presentación, añada un gráfico bursátil, limpie los datos predeterminados y luego inserte sus propias series y categorías. La respuesta directa a la pregunta principal es:

> Load an existing PPTX with `new Presentation("template.pptx")`, add a `Chart` of type `ChartType.Stock`, clear its default series and categories, then populate it with your own data points and formatting options. Finally, call `presentation.save("output.pptx", SaveFormat.Pptx)`.

### Inicializar presentación
#### Visión general
Comience cargando un archivo PowerPoint existente para poder modificarlo en su lugar.

#### Paso a paso
1. **Importar la biblioteca** – la clase `Presentation` es el punto de entrada para todas las operaciones de diapositivas.  

   ```java
   import com.aspose.slides.Presentation;
   ```

2. **Cargar el archivo de presentación** – proporcione la ruta a su PPTX de plantilla.  

   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // Ready to perform operations on 'pres'
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Añadir gráfico bursátil a la diapositiva
#### Visión general
Inserte un gráfico Stock en la primera diapositiva de la presentación.

La clase `Chart` representa una forma de gráfico que puede añadirse a una diapositiva.

#### Respuesta directa
Añade un gráfico bursátil llamando a `slide.getShapes().addChart(ChartType.Stock, x, y, width, height)`. Esto crea un objeto de gráfico que puede manipularse inmediatamente.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.ChartType;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Borrar series de datos y categorías existentes en el gráfico
#### Visión general
Elimine cualquier serie o categoría pre‑poblada para comenzar con un conjunto de datos limpio.

El objeto `ChartData` contiene las series y categorías de un gráfico.

#### Respuesta directa
Ejecute `chart.getChartData().getSeries().clear()` y `chart.getChartData().getCategories().clear()` para eliminar el contenido predeterminado antes de añadir el suyo.

   ```java
   import com.aspose.slides.IChart;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       chart.getChartData().getSeries().clear();
       chart.getChartData().getCategories().clear();
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Añadir categorías a los datos del gráfico
#### Visión general
Defina las categorías del eje X (p. ej., fechas) que agrupan sus valores bursátiles.

Un `ChartCategory` representa una etiqueta del eje X para un gráfico.

#### Respuesta directa
Cree un nuevo `ChartCategory` para cada etiqueta usando `chart.getChartData().getCategories().add(dataWorkbook.getCell(0, row, 0), "Jan")`, repitiendo para cada mes o período.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // Add categories
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Añadir series de datos al gráfico
#### Visión general
Añada las cuatro series esenciales: Open, High, Low y Close.

Un `ChartSeries` contiene una colección de puntos de datos para una serie específica en el gráfico.

#### Respuesta directa
Para cada serie, llame a `chart.getChartData().getSeries().add(dataWorkbook.getCell(0, 0, colIndex), chart.getType())`. Esto registra la serie en el libro de datos del gráfico.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add series for 'Open', 'High', 'Low', and 'Close'
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 1, "Open"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 2, "High"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 3, "Low"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 4, "Close"), chart.getType());
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Añadir puntos de datos a la serie
#### Visión general
Rellene cada serie con valores numéricos que representan precios bursátiles.

Un `DataPoint` representa un único valor en una serie.

#### Respuesta directa
Itere a través de su colección de datos y use `series.getDataPoints().addDataPointForBarSeries(dataWorkbook.getCell(0, row, col), value)` (o el método apropiado para el tipo de serie) para insertar cada punto.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add data points to 'Open' series
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // Add data points to 'High' series
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // Add data points to 'Low' series
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // Add data points to 'Close' series
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Formatear líneas alta‑baja y barras arriba/abajo
#### Visión general
Ajuste el estilo visual de los conectores alta‑baja y los rellenos de las barras arriba/abajo.

Un `Marker` define el símbolo visual para un punto de datos.

#### Respuesta directa
Establezca `chart.getChartData().getSeries().get(0).getMarker().setSize(10)` y configure `chart.getChartData().getSeries().get(0).getFormat().getLine().setWidth(2)` para controlar el grosor y color de la línea.

   ```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // Format high-low lines for 'Close' series
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

#### Mostrar barras arriba/abajo
Utilice el método `setShowUpDownBars(true)` del gráfico para hacer visibles las barras arriba/abajo.

   ```java
   // Display up/down bars for the stock chart series group
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### Personalizar etiquetas de datos en líneas alta‑baja
#### Visión general
Muestre valores numéricos directamente en las líneas alta‑baja para referencia rápida.

Un `DataLabel` controla la apariencia de las etiquetas adjuntas a los puntos de datos.

#### Respuesta directa
Active las etiquetas de datos con `chart.getChartData().getSeries().get(0).getDataPoints().get(i).getLabel().setShowValue(true)` y estílelas según sea necesario.

   ```java
    // Show values on up/down bars for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### Establecer color de relleno de barras arriba/abajo
#### Visión general
Dé a las barras ascendentes un relleno verde y a las descendentes un relleno rojo para transmitir intuitivamente el movimiento del mercado.

El objeto `UpDownBars` brinda acceso al formato de las barras arriba y abajo.

#### Respuesta directa
Aplique `chart.getUpDownBars().getUpBar().getFillFormat().setFillType(FillType.Solid)` y establezca el color sólido a `Color.GREEN`; repita para la barra descendente con `Color.RED`.

   ```java
    // Change the up/down bar colors for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // 'Open' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // Up bars in cyan
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // 'High' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // Down bars in dark sea green
        }
    }
    ```

### Guardar el archivo PowerPoint
#### Visión general
Guarde sus cambios en un nuevo archivo PPTX.

El método `save` escribe la presentación en disco en el formato especificado.

#### Respuesta directa
Llame a `presentation.save("DynamicStockChart.pptx", SaveFormat.Pptx)` – esto escribe la presentación modificada en disco en el formato estándar de PowerPoint.

   ```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## Problemas comunes y solución de problemas

- **El gráfico no aparece** – asegúrese de que las coordenadas X/Y y dimensiones del gráfico estén dentro de los límites de la diapositiva.  
- **Faltan puntos de datos** – verifique que los índices de celdas del libro de datos coincidan con la serie/fila que desea poblar.  
- **Excepción de licencia** – una licencia de prueba temporal expira después de 30 días; reemplácela con una licencia permanente para compilaciones de producción.  
- **Ralentización del rendimiento en archivos grandes** – use `Presentation.setCacheSize(0)` para desactivar el caché si procesa miles de diapositivas en lote.

## Preguntas frecuentes

**Q: ¿Puedo usar este código en una aplicación web?**  
A: Sí. La biblioteca es Java puro, por lo que puede ejecutarse en cualquier contenedor servlet o servicio Spring Boot.

**Q: ¿Aspose.Slides admite otros tipos de gráficos además de Stock?**  
A: Absolutamente. Admite más de 70 tipos de gráficos, incluidos Line, Bar, Pie y Radar.

**Q: ¿Cómo añado un título de gráfico programáticamente?**  
A: Use `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")` y luego formatee el título según sea necesario.

**Q: ¿Existe un límite para el número de puntos de datos por serie?**  
A: Prácticamente, puede añadir decenas de miles de puntos; el uso de memoria escala linealmente y la biblioteca transmite datos para mantener una huella baja.

**Q: ¿Qué coordenadas Maven debo usar para la última versión?**  
A: La última versión siempre está disponible bajo `com.aspose:aspose-slides:25.4` (o más reciente) en Maven Central.

---

**Última actualización:** 2026-09-12  
**Probado con:** Aspose.Slides for Java 25.4  
**Autor:** Aspose

## Tutoriales relacionados

- [dependencia maven de aspose slides: Añadir y Configurar Gráficos en Presentaciones Usando Aspose.Slides para Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Crear Gráfico PowerPoint Java – Guardar Presentaciones con Gráficos Usando Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [Crear y Formatear Gráficos PowerPoint Aspose Slides Java](/slides/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}