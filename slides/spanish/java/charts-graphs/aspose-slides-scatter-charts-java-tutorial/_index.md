---
date: '2026-02-24'
description: Aprenda cómo personalizar gráficos de dispersión con Aspose usando Aspose.Slides
  para Java. Esta guía le guía paso a paso en la creación, el estilo y el guardado
  de gráficos de dispersión dinámicos en sus presentaciones.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Personalizar gráfico de dispersión Aspose en Java
url: /es/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

 sure to keep code blocks placeholders unchanged.

Also keep markdown formatting.

Let's craft translation.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Personalizar Scatter Chart Aspose en Java

En este tutorial aprenderás a **customize scatter chart aspose** con la potente biblioteca Aspose.Slides for Java. Recorreremos la configuración de tu proyecto, la creación de un scatter chart, la modificación de tipos de series y marcadores, y finalmente la guardado de la presentación. Al final, podrás generar programáticamente scatter charts de aspecto profesional y adaptar cada detalle visual para que coincida con tu marca o necesidades de informes.

## Quick Answers
- **What library do I need?** Aspose.Slides for Java (v25.4+).  
- **Which Java version is supported?** JDK 8 or higher.  
- **Can I change marker shapes?** Yes – use `MarkerStyleType` to pick stars, circles, etc.  
- **How do I save the file?** Call `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **Is a license required?** A free trial works for development; a commercial license is needed for production.

## What is “customize scatter chart aspose”?
Personalizar un scatter chart con Aspose significa definir programáticamente los datos, la apariencia y el comportamiento del gráfico—todo, desde las coordenadas de los puntos hasta los símbolos de los marcadores—sin abrir PowerPoint manualmente. Este enfoque es ideal para informes automatizados, presentaciones basadas en datos o cualquier escenario donde necesites visualizaciones repetibles y de alta calidad.

## Why customize scatter charts with Aspose.Slides?
- **Full control** – modify series types, marker styles, colors, and more via Java code.  
- **Automation** – generate dozens of charts on the fly for dashboards or batch reports.  
- **Cross‑platform** – works on any OS that supports Java, no Office installation required.  
- **Performance** – lightweight API that handles large data sets efficiently.

## Prerequisites

Para seguir este tutorial, asegúrate de tener:

- **Aspose.Slides for Java** (v25.4 o posterior).  
- **Java Development Kit (JDK)** 8 + instalado.  
- Maven o Gradle para la gestión de dependencias (o puedes descargar el JAR manualmente).  
- Conocimientos básicos de Java y familiaridad con la herramienta de compilación que prefieras.

## Setting Up Aspose.Slides for Java

Integra la biblioteca en tu proyecto usando uno de los métodos a continuación.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

O descarga la última versión desde [Aspose Releases](https://releases.aspose.com/slides/java/).

#### License Acquisition
- **Free Trial** – 30‑day evaluation.  
- **Temporary License** – extended testing period.  
- **Full License** – production use with premium support.

## Step‑by‑Step Guide to Customize Scatter Chart Aspose

### 1️⃣ Prepare a folder for your presentation files
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```
*Why this matters:* Ensuring the output folder exists prevents `FileNotFoundException` when you later save the PPTX.

### 2️⃣ Create a new presentation and grab the first slide
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
A fresh `Presentation` gives you a clean canvas; the first slide is where we’ll place the chart.

### 3️⃣ Add a scatter chart with smooth lines
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
The `ChartType.ScatterWithSmoothLines` creates a smooth‑line scatter chart, perfect for trend visualization.

### 4️⃣ Clear any default series and add your own
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
Removing the default series gives you full control over the data you display.

### 5️⃣ Populate the first series with data points
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
`addDataPointForScatterSeries` takes an X‑value cell and a Y‑value cell, building the scatter plot point‑by‑point.

### 6️⃣ Customize series type and marker appearance
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
Here we **customize the scatter chart aspose** by switching to straight lines, enlarging markers, and picking distinct symbols (star vs. circle) for visual clarity.

### 7️⃣ Save the presentation
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
Saving as `Pptx` preserves all chart customizations and makes the file ready for sharing or further editing.

## Common Use Cases for Customized Scatter Charts
- **Financial dashboards** – plot stock price vs. volume.  
- **Scientific research** – display experimental measurements with error markers.  
- **Project management** – compare planned vs. actual effort across tasks.  

## Performance Tips
- Dispose of the `Presentation` object (`pres.dispose()`) after saving to free native resources.  
- For large data sets, populate the workbook first and then bind the series to avoid repeated UI refreshes.  
- Reuse a single `IChartDataWorkbook` instance when adding many series.

## Frequently Asked Questions

### How do I change the color of the markers?
Use `series.getMarker().getFillFormat().setFillColor(Color)` where `Color` is an instance of `java.awt.Color` (e.g., `Color.RED`).

### Can I add more than two series to a scatter chart?
Absolutely. Repeat the `chart.getChartData().getSeries().add(...)` call for each additional series and populate its data points accordingly.

### Is it possible to set a custom legend for each series?
Yes. After creating a series, call `series.getLegend().setText("Your Legend Text")` to override the default name.

### How can I export the chart as an image instead of a PPTX?
Call `chart.getImage().save("chart.png", ImageFormat.Png)` after configuring the chart. This gives you a standalone PNG file.

### What if I need to animate the scatter points?
Aspose.Slides supports animation effects. Use `chart.getTimeline().getMainSequence().addEffect(...)` to add entrance or emphasis animations to the chart or individual series.

---

**Last Updated:** 2026-02-24  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}