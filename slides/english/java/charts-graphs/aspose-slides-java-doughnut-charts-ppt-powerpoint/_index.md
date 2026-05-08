---
title: "Create doughnut chart PowerPoint with Aspose.Slides for Java"
description: "Learn how to create doughnut chart PowerPoint using Aspose.Slides for Java and add chart data points programmatically. Follow easy steps and code examples."
date: "2026-02-17"
weight: 1
url: "/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/"
keywords:
- Aspose.Slides for Java
- dynamic doughnut charts PowerPoint
- Java PowerPoint chart creation
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Create doughnut chart PowerPoint with Aspose.Slides for Java

## Introduction
Creating compelling presentations often requires more than just text and images; charts can significantly enhance storytelling by visualizing data effectively. However, many developers struggle to integrate dynamic chart features into PowerPoint files programmatically. This tutorial demonstrates how to **create doughnut chart PowerPoint** using Aspose.Slides for Java—a powerful tool that combines flexibility and ease of use.

**What You'll Learn:**
- How to initialize a presentation using Aspose.Slides for Java
- A step‑by‑step guide to adding a doughnut chart to your slides
- Configuring data points and customizing label properties
- Saving the modified presentation with high fidelity

Let's explore how you can leverage these features to enhance your presentations. Before we start, ensure you're familiar with basic Java programming concepts.

## Quick Answers
- **What library creates doughnut chart PowerPoint?** Aspose.Slides for Java
- **Can I add chart data points programmatically?** Yes, using the chart API
- **Do I need a license for production?** A valid Aspose.Slides license is required
- **Which Java versions are supported?** Java 8 and later (JDK 16 classifier shown)
- **How many series can I add?** The example adds up to 15 series, but you can adjust as needed

## What is a doughnut chart in PowerPoint?
A doughnut chart is a variation of a pie chart with a hollow center, allowing you to display multiple data series in a compact, visually appealing way. It’s ideal for showing part‑to‑whole relationships while keeping the design clean.

## Why use Aspose.Slides for Java to create doughnut charts?
- **Full control** over chart appearance, data, and layout without opening PowerPoint
- **No COM interop** – works on any platform that supports Java
- **High performance** for generating large decks or integrating with web services
- **Rich customization** such as explosion, hole size, slice angles, and label formatting

## Prerequisites
- Basic knowledge of Java programming.
- An IDE like IntelliJ IDEA or Eclipse.
- Maven or Gradle for dependency management.
- A valid Aspose.Slides for Java license (free trial available).

## Setting Up Aspose.Slides for Java
Choose the dependency manager that fits your project.

**Maven**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

If you prefer downloading directly, visit the [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) page.

### License Acquisition
You can start with a free trial to explore Aspose.Slides features. For extended use, purchase a license or request a temporary one from [Aspose's website](https://purchase.aspose.com/temporary-license/). Follow the instructions provided for setting up your environment and initializing Aspose.Slides in your application.

## How to create doughnut chart PowerPoint using Aspose.Slides for Java
Below is a complete, step‑by‑step guide. Each code block is explained right before it, so you know exactly what’s happening.

### Step 1: Initialize the presentation
First, load an existing PPTX or create a new one. This prepares the slide collection for further modifications.

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Step 2: Add a doughnut chart to the slide
We add the chart shape, clear any default series/categories, and set basic visual properties.

```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Step 3: Add chart data points and customize labels
Here we populate categories, add data points for each series, and fine‑tune the label appearance. This is where the **add chart data points** keyword comes into play.

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

### Step 4: Save the updated presentation
Finally, persist the changes to a new PPTX file.

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Practical Applications
Doughnut charts can be used in various real‑world scenarios:
- **Financial Reports:** Visualize budget allocations or expense breakdowns.
- **Market Analysis:** Show market‑share distribution among competitors.
- **Survey Results:** Present categorical survey data in a compact form.
- **Dashboard Generation:** Combine with database queries to generate live‑updating slides.

## Performance Considerations
- **Dispose resources**: Call `pres.dispose()` when you’re done to free native memory.
- **Limit chart count**: Adding hundreds of charts can increase memory usage; batch‑process if needed.
- **Use streaming**: For massive data sets, populate the workbook directly from streams instead of in‑memory arrays.

## Common Issues and Solutions
| Issue | Cause | Fix |
|-------|-------|-----|
| **Chart appears blank** | Data cells not populated correctly | Verify that `workBook.getCell(...)` references the correct row/column indices. |
| **Labels overlap** | Too many categories in limited space | Increase `DoughnutHoleSize` or adjust `FirstSliceAngle`. |
| **OutOfMemoryError** | Large presentations without disposing | Call `pres.dispose()` after saving and consider increasing JVM heap size. |

## Frequently Asked Questions

**Q: Can I use Aspose.Slides for Java in commercial applications?**  
A: Yes, but you need a valid commercial license. A free trial is available for evaluation.

**Q: How do I add more than 15 series?**  
A: Increase the loop limit in the “Add Doughnut Chart” step and ensure your data workbook has enough rows.

**Q: Is it possible to change the doughnut hole size after creation?**  
A: Yes, call `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` at any point before saving.

**Q: Can I export the chart as an image instead of a PPTX?**  
A: Absolutely. Use `chart.getImage()` and save the returned `java.awt.image.BufferedImage` in your preferred format.

**Q: Does Aspose.Slides support animated charts?**  
A: Animation can be added via the `ISlide.getTimeline()` API, though it’s beyond the scope of this tutorial.

## Conclusion
You now have a complete, production‑ready method to **create doughnut chart PowerPoint** files with Aspose.Slides for Java, including how to **add chart data points**, customize labels, and handle performance considerations. Experiment with different colors, data sources, and chart types to make your presentations truly stand out.

---

**Last Updated:** 2026-02-17  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}