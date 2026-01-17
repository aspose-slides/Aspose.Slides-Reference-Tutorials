---
date: '2026-01-17'
description: Naučte se, jak přidat řady do grafu a přizpůsobit sloupcové grafy se
  zásobníkem v .NET prezentacích pomocí Aspose.Slides pro Java.
keywords:
- Aspose.Slides for Java
- .NET Presentations
- Chart Customization
title: Přidat řadu do grafu pomocí Aspose.Slides pro Java v .NET
url: /cs/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Mistrovství přizpůsobení grafů v .NET prezentacích pomocí Aspose.Slides pro Java

## Introduction
V oblasti prezentací řízených daty jsou grafy nepostradatelnými nástroji, které proměňují surová čísla v poutavé vizuální příběhy. Když potřebujete **add series to chart** programově, zejména v souborech .NET prezentací, může se úkol zdát ohromující. Naštěstí **Aspose.Slides for Java** poskytuje výkonné, jazykově nezávislé API, které usnadňuje tvorbu a přizpůsobení grafů – i když je vaším cílovým formátem .NET PPTX.

V tomto tutoriálu se dozvíte, jak **add series to chart**, jak **how to add chart** typu sloupcového zásobníku a jak doladit vizuální aspekty, jako je šířka mezery. Na konci budete schopni generovat dynamické, daty bohaté snímky, které vypadají profesionálně a elegantně.

**What You’ll Learn**
- Jak vytvořit prázdnou prezentaci pomocí Aspose.Slides  
- Jak **add stacked column chart** do snímku  
- Jak **add series to chart** a definovat kategorie  
- Jak naplnit datové body a upravit vizuální nastavení  

Pojďme připravit vaše vývojové prostředí.

## Quick Answers
- **What is the primary class to start a presentation?** `Presentation`  
- **Which method adds a chart to a slide?** `slide.getShapes().addChart(...)`  
- **How do you add a new series?** `chart.getChartData().getSeries().add(...)`  
- **Can you change the gap width between bars?** Yes, using `setGapWidth()` on the series group  
- **Do I need a license for production?** Yes, a valid Aspose.Slides for Java license is required  

## What is “add series to chart”?
Přidání série do grafu znamená vložení nové kolekce dat, kterou graf vykreslí jako samostatný vizuální prvek (např. nový sloupec, čára nebo výseč). Každá série může mít vlastní sadu hodnot, barev a formátování, což vám umožní porovnávat více datových sad vedle sebe.

## Why use Aspose.Slides for Java to modify .NET presentations?
- **Cross‑platform**: Napište Java kód jednou a cílové soubory PPTX použijí .NET aplikace.  
- **No COM or Office dependencies**: Funguje na serverech, v CI pipelinech i v kontejnerech.  
- **Rich chart API**: Podporuje více než 50 typů grafů, včetně stacked column charts.  

## Prerequisites
1. **Aspose.Slides for Java** knihovna (verze 25.4 nebo novější).  
2. Maven nebo Gradle build tool, nebo ruční stažení JAR souboru.  
3. Základní znalost Javy a povědomí o struktuře PPTX.  

## Setting Up Aspose.Slides for Java
### Maven Installation
Add the following dependency to your `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle Installation
Include this line in your `build.gradle` file:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download
Alternatively, grab the latest JAR from the official release page: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**License Acquisition**  
Start with a free trial by downloading a temporary license from [here](https://purchase.aspose.com/temporary-license/). For production use, purchase a full license to unlock all features.

## Step‑by‑Step Implementation Guide
Below each step you’ll find a concise code snippet (unchanged from the original tutorial) followed by an explanation of what it does.

### Step 1: Create an Empty Presentation
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```
*We start with a clean PPTX file, which gives us a canvas for adding charts.*

### Step 2: Add a Stacked Column Chart to the Slide
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```
*The `addChart` method creates a **add stacked column chart** and places it at the top‑left corner of the slide.*

### Step 3: Add Series to the Chart (Primary Goal)
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```
*Here we **add series to chart** – each call creates a new data series that will appear as a separate column group.*

### Step 4: Add Categories to the Chart
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```
*Categories act as the X‑axis labels, giving meaning to each column.*

### Step 5: Populate Series Data
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```
*Data points give each series its numeric values, which the chart will render as bar heights.*

### Step 6: Set Gap Width for Chart Series Group
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```
*Adjusting the gap width improves readability, especially when many categories are present.*

## Common Use Cases
- **Financial reporting** – compare quarterly revenue across business units.  
- **Project dashboards** – show task completion percentages per team.  
- **Marketing analytics** – visualize campaign performance side‑by‑side.

## Performance Tips
- **Reuse the `Presentation` object** when creating multiple charts to reduce memory overhead.  
- **Limit the number of data points** to only those needed for the visual story.  
- **Dispose of objects** (`presentation.dispose()`) after saving to free resources.

## Frequently Asked Questions
**Q: Can I add other chart types besides stacked column?**  
A: Yes, Aspose.Slides supports line, pie, area, and many more chart types.

**Q: Do I need a separate license for .NET output?**  
A: No, the same Java license works for all output formats, including .NET PPTX files.

**Q: How do I change the chart’s color palette?**  
A: Use `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` and set the desired `Color`.

**Q: Is it possible to add data labels programmatically?**  
A: Absolutely. Call `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` to display values.

**Q: What if I need to update an existing presentation?**  
A: Load the file with `new Presentation("existing.pptx")`, modify the chart, and save it back.

## Conclusion
You now have a complete, end‑to‑end guide on how to **add series to chart**, create a **stacked column chart**, and fine‑tune its appearance in .NET presentations using Aspose.Slides for Java. Experiment with different chart types, colors, and data sources to build compelling visual reports that impress stakeholders.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-17  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose