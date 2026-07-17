---
date: '2026-07-17'
description: Aprenda cómo rotar pie chart, personalizar los colores de pie chart y
  exportar la diapositiva a PDF usando Aspose.Slides for Java – una guía completa
  de visualización de datos.
keywords:
- rotate pie chart
- customize pie chart colors
- export slide to pdf
- chart data worksheet
- java data visualization
lastmod: '2026-07-17'
og_description: Rotar pie chart y personalizar los colores de pie chart usando Aspose.Slides
  for Java. Aprenda a exportar la diapositiva a PDF y trabajar con chart data worksheet.
og_image_alt: Guide showing how to rotate a pie chart and set custom colors in Java
  with Aspose.Slides
og_title: Rotar Pie Chart y personalizar colores en Java – Guía Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to rotate pie chart, customize pie chart colors, and export
    slide to PDF using Aspose.Slides for Java – a full data visualization guide.
  headline: How to Rotate Pie Chart and Customize Colors in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Request a free trial from the Aspose website, then purchase a permanent
      license. Load it at runtime as shown in the Common Issues table.
    question: How do I obtain an Aspose.Slides license for Java?
  - answer: The API requires JDK 16 or higher; older versions are not supported.
    question: Can I use this code with older JDK versions?
  - answer: Yes—after rendering, call `chart.getChartData().getChartDataWorkbook().save("chart.png",
      ImageFormat.Png);`.
    question: Is it possible to export the chart as an image instead of PPTX?
  - answer: Pie charts are designed for a single data series; for multiple series,
      consider using a doughnut chart.
    question: What if I need more than one series in a pie chart?
  - answer: Absolutely—Aspose.Slides for Java is platform‑independent and works on
      any OS with a compatible JDK.
    question: Does Aspose.Slides run on Linux servers?
  type: FAQPage
tags:
- rotate pie chart
- Aspose.Slides
- Java charting
- data visualization
title: Cómo rotar Pie Chart y personalizar colores en Java con Aspose.Slides
url: /es/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Creación de gráficos de pastel con Aspose.Slides para Java: Un tutorial completo

## Introducción
En esta guía aprenderás a **rotar gráfico de pastel**, personalizar el color de cada porción y exportar la diapositiva final a PDF, todo con Aspose.Slides para Java. Ya sea que estés construyendo un panel de ventas, un informe financiero o cualquier presentación basada en datos, dominar estas técnicas te permite ofrecer visuales claros y llamativos sin depender de Microsoft Office. Preparemos las herramientas y comencemos.

## Respuestas rápidas
- **¿Qué clase inicia una nueva presentación?** `Presentation` from `com.aspose.slides`.
- **¿Qué llamada de API agrega un gráfico de pastel?** `slide.addChart(ChartType.Pie, …)`.
- **¿Cómo puedes dar a cada porción un color único?** Call `series.setColorVaried(true)` and set solid fills per data point.
- **¿Qué método rota el gráfico?** `chart.setRotationAngle(double)` – use degrees from 0 to 360.
- **¿Puede la diapositiva exportarse a PDF?** Yes, invoke `presentation.save("output.pdf", SaveFormat.Pdf)`.

## ¿Qué significa “personalizar colores de gráficos de pastel”?
Personalizar colores de gráficos de pastel significa asignar colores de relleno distintos a cada porción del pastel, mejorando la legibilidad y el impacto visual. En Aspose.Slides logras esto habilitando colores variados y luego estableciendo colores de relleno sólido para cada punto de datos. Este enfoque asegura que cada segmento de datos destaque claramente en la presentación.

## ¿Por qué usar Aspose.Slides para Java para crear gráficos de pastel?
Aspose.Slides soporta **150+ tipos de gráficos** y puede renderizar una presentación de 300 páginas en menos de **5 segundos** en un servidor típico, todo sin necesidad de instalar Microsoft Office. La biblioteca funciona en Windows, Linux y macOS, brindándote flexibilidad multiplataforma para cualquier proyecto de visualización de datos basado en Java.

## Requisitos previos
- **Aspose.Slides for Java** ≥ 25.4
- **JDK** 16 o superior
- IDE como IntelliJ IDEA, Eclipse o NetBeans
- Conocimientos básicos de Java y familiaridad con Maven o Gradle

## Configuración de Aspose.Slides para Java
Agrega la biblioteca a tu configuración de compilación.

**Maven**  
Agrega este fragmento a tu archivo `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Incluye lo siguiente en tu archivo `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Descarga directa**  
Si prefieres un enfoque manual, descarga el JAR más reciente desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Pasos para adquirir la licencia
- **Free Trial** – explore all features without cost.  
- **Temporary License** – extend trial limits for a short period.  
- **Purchase** – obtain a permanent license for production use.

**Inicialización y configuración básica**  
La clase `Presentation` representa un archivo PowerPoint en memoria y proporciona métodos para manipular diapositivas.  
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Guía de implementación
A continuación se muestra una guía paso a paso que cubre todo, desde crear una diapositiva hasta rotar el gráfico de pastel final.

### Inicializar presentación y diapositiva
Crea una nueva instancia de `Presentation` y recupera la primera diapositiva para usarla como lienzo del gráfico.  
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Agregar gráfico de pastel a la diapositiva
`addChart` adds a chart shape of the specified type to the slide at given coordinates.  
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Establecer título del gráfico
`setTitle` assigns a text title to the chart and positions it centrally.  
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Configurar etiquetas de datos para la serie
`setShowValue(true)` enables numeric value labels on each data point of the series.  
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Preparar hoja de datos del gráfico
`ChartDataWorkbook` stores the underlying data table that feeds the chart series and categories.  
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Añadir categorías al gráfico
`addCategory` creates a new category label for the chart's data series.  
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Añadir serie y poblar puntos de datos
`addSeries` creates a data series, and `addDataPointForBarSeries` inserts numeric values for each category.  
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Personalizar colores y bordes de la serie
`setColorVaried(true)` enables per-slice colors, and `setFillFormat` assigns a solid fill to each data point.  
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Configurar etiquetas de datos personalizadas
`setDataLabelFormat` customizes label appearance, position, and font for clearer chart annotations.  
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Establecer ángulo de rotación y guardar la presentación
`setRotationAngle` rotates the entire pie chart, and `save` writes the presentation to a file.  
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## ¿Cómo rotar el gráfico de pastel?
Carga el objeto del gráfico, llama a `chart.setRotationAngle(45.0)` (o cualquier valor en grados), y luego guarda la presentación. Rotar un gráfico de pastel desplaza el ángulo de inicio, permitiéndote enfatizar un segmento particular sin alterar los datos. Esta única llamada de método funciona para cualquier instancia de `Chart` en Aspose.Slides. También puedes combinar la rotación con colores de porción variados para destacar el punto de datos más importante.

## Problemas comunes y soluciones
| Problema | Causa | Solución |
|----------|-------|----------|
| **Slices all appear the same color** | `setColorVaried(true)` not called | Ensure you enable varied colors on the series group. |
| **Data labels not showing** | `showValue` flag disabled | Call `setShowValue(true)` on the label format. |
| **Rotation has no effect** | Using an older Aspose.Slides version | Upgrade to version 25.4 or later. |
| **License exception at runtime** | Missing or invalid license file | Load your license with `License license = new License(); license.setLicense("Aspose.Slides.lic");` before creating the `Presentation`. |

## Preguntas frecuentes

**Q: ¿Cómo obtengo una licencia de Aspose.Slides para Java?**  
A: Request a free trial from the Aspose website, then purchase a permanent license. Load it at runtime as shown in the Common Issues table.

**Q: ¿Puedo usar este código con versiones anteriores de JDK?**  
A: The API requires JDK 16 or higher; older versions are not supported.

**Q: ¿Es posible exportar el gráfico como imagen en lugar de PPTX?**  
A: Yes—after rendering, call `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);`.

**Q: ¿Qué pasa si necesito más de una serie en un gráfico de pastel?**  
A: Pie charts are designed for a single data series; for multiple series, consider using a doughnut chart.

**Q: ¿Aspose.Slides funciona en servidores Linux?**  
A: Absolutely—Aspose.Slides for Java is platform‑independent and works on any OS with a compatible JDK.

---

**Last Updated:** 2026-07-17  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Cómo crear gráficos de pastel en presentaciones Java usando Aspose.Slides: Guía completa](/slides/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/)
- [Domina los gráficos de pastel en Java usando Aspose.Slides: Guía completa](/slides/java/charts-graphs/master-pie-charts-aspose-slides-java/)
- [Rotar textos de gráficos en Java con Aspose.Slides: Guía completa](/slides/java/charts-graphs/rotate-chart-texts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}