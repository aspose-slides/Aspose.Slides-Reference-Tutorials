---
title: "Add Legend PowerPoint Chart – Create Dynamic Doughnut Charts with Aspose.Slides for Java"
description: "Learn how to add legend PowerPoint chart and create dynamic doughnut charts in PowerPoint using Aspose.Slides for Java. Step‑by‑step guide with code examples."
date: "2026-01-19"
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
# Create Dynamic Doughnut Charts in PowerPoint using Aspose.Slides for Java

## Introduction
Adding a legend to a PowerPoint chart can turn a plain visual into a story‑telling masterpiece. In this tutorial you’ll learn **how to add legend PowerPoint chart** elements while building a dynamic doughnut chart with Aspose.Slides for Java. We'll walk through initializing a presentation, inserting the chart, configuring data points, customizing labels, and finally saving the file. By the end you’ll have a fully functional PowerPoint that not only displays data but also includes a clear legend and polished data labels.

**What You'll Learn:**
- How to initialize a presentation using Aspose.Slides for Java  
- A step‑by‑step guide to adding a doughnut chart to your slides  
- Configuring data points, **add data labels chart**, and customizing legend properties  
- Saving the modified presentation with high fidelity  

Let's explore how you can leverage these features to enhance your presentations. Before we start, make sure you’re comfortable with basic Java syntax.

## Quick Answers
- **What is the primary library?** Aspose.Slides for Java  
- **Can I add a legend to a doughnut chart?** Yes – use the chart’s legend and series settings  
- **Do I need a license?** A trial works for development; a commercial license is required for production  
- **Which Java version is supported?** The example uses JDK 16 (classifier jdk16)  
- **How many data series can I create?** The sample loops up to 15 series, but you can adjust as needed  

## What is a doughnut chart and why add a legend?
A doughnut chart is a variant of a pie chart with a hollow center, ideal for showing part‑to‑whole relationships while leaving space for additional information. Adding a legend helps viewers quickly map colors to categories, improving readability—especially when you have many series.

## Prerequisites
- Basic knowledge of Java programming.  
- An IDE such as IntelliJ IDEA or Eclipse.  
- Maven or Gradle for dependency management.  
- A valid Aspose.Slides for Java license (free trial available).

## Setting Up Aspose.Slides for Java
Choose the dependency format that matches your build tool.

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

If you prefer downloading the JAR directly, visit the [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) page.

### License Acquisition
You can start with a free trial to explore Aspose.Slides features. For extended use, purchase a license or request a temporary one from [Aspose's website](https://purchase.aspose.com/temporary-license/). Follow the instructions provided for setting up your environment and initializing Aspose.Slides in your application.

## Implementation Guide
Below is a complete walkthrough. Each code block is explained before it appears, so you know exactly what’s happening.

### Initialize Presentation
First, load an existing PPTX or create a new one. This step sets up the presentation object that will hold the chart.

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Add Doughnut Chart
Now we add a doughnut chart to the slide. The `ChartType.Doughnut` creates the right visual, and we also turn off the default legend because we’ll customize it later.

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

### Configure Data Points and Labels
Next we populate categories, add data points for each series, and **add data labels chart**. The label customization also demonstrates how to position a legend‑like description next to the last series in each category.

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

### Save the Presentation
Finally, persist the changes to a new PPTX file.

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Why add legend PowerPoint chart to a doughnut chart?
- **Clarity:** Legends map colors to categories without crowding the chart area.  
- **Scalability:** When you have many series (as in the loop above), a legend keeps the slide readable.  
- **Professional look:** A polished legend combined with custom data labels gives a corporate‑grade presentation.

## Practical Applications
Doughnut charts with legends are perfect for:
- **Financial reports:** Show expense breakdowns alongside a legend for each department.  
- **Market analysis:** Visualize market share while the legend identifies each competitor.  
- **Survey results:** Present multiple‑choice responses with clear category names.

You can pull data from databases, CSV files, or web services and feed it into the loop to generate charts on the fly.

## Performance Considerations
- Dispose of `Presentation` objects promptly (`pres.dispose()`) in long‑running apps.  
- Limit the number of series if you notice memory pressure; each series adds overhead.  
- Re‑use a single `IChartDataWorkbook` when populating large datasets.

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| Legend not visible | `chart.setLegend(false)` disables it. | Set `chart.setLegend(true)` and customize position. |
| Labels overlapping | Default label placement may clash with the doughnut hole. | Adjust `lbl.setX()` / `lbl.setY()` or increase `DoughnutHoleSize`. |
| Color not applied | Fill type not set to `Solid`. | Ensure `dataPoint.getFormat().getFill().setFillType(FillType.Solid)`. |

## Frequently Asked Questions

**Q: Can I use Aspose.Slides for Java in commercial applications?**  
A: Yes, but you need a valid commercial license. A free trial is available for evaluation.

**Q: How do I enable the legend after it has been disabled?**  
A: Call `chart.setLegend(true);` and optionally set its position with `chart.getLegend().setPosition(LegendPosition.Right);`.

**Q: Is it possible to change the legend font style?**  
A: Absolutely. Use `chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(12);` and other font properties.

**Q: Can I bind the chart to real‑time data from a database?**  
A: Yes. Retrieve data with JDBC, populate the workbook cells inside the loops, and the chart will reflect the latest values.

**Q: Does Aspose.Slides support other chart types besides doughnut?**  
A: It supports a full range of chart types—pie, bar, line, scatter, and more. Just replace `ChartType.Doughnut` with the desired enum.

---

**Last Updated:** 2026-01-19  
**Tested With:** Aspose.Slides 25.4 (JDK 16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}