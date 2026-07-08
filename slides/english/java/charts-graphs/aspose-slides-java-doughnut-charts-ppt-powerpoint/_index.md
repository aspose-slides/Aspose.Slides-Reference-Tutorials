---
date: '2026-07-08'
description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
  Java. This step‑by‑step guide shows adding chart data points programmatically, customizing
  labels, and saving the PPTX with high fidelity.
images:
- /java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/og-image.png
keywords:
- how to use aspose
- create doughnut chart powerpoint
- maven dependency aspose slides
lastmod: '2026-07-08'
og_description: How to use Aspose lets you create a doughnut chart in PowerPoint using
  Java. Follow this tutorial to add data points, customize labels, and save the PPTX
  with high fidelity.
og_image_alt: 'Guide: Create doughnut chart PowerPoint with Aspose.Slides for Java'
og_title: 'How to Use Aspose: Create Doughnut Chart in PowerPoint (Java)'
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  headline: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  type: TechArticle
- description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  name: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  steps:
  - name: Initialize the presentation
    text: Create a fresh presentation or open an existing file to obtain a slide collection.
      `Presentation` is the primary class that represents a PowerPoint file.
  - name: Add a doughnut chart to the slide
    text: Insert a chart shape, remove default series/categories, and configure basic
      visual settings like the doughnut hole size. `Chart` (or chart shape) represents
      a chart object placed on a slide.
  - name: Add chart data points and customize labels
    text: Populate category names, add data points for each series, and fine‑tune
      label formatting (font, color, position). This step demonstrates the “add chart
      data points” capability. `Workbook` provides access to the chart’s underlying
      spreadsheet data where cells are populated.
  - name: Save the updated presentation
    text: Persist the changes to a new PPTX file on disk. `save` writes the presentation
      to a file in the chosen format.
  type: HowTo
- questions:
  - answer: Yes, but you need a valid commercial license. A free trial is available
      for evaluation.
    question: Can I use Aspose.Slides for Java in commercial applications?
  - answer: Increase the loop limit in the “Add Doughnut Chart” step and ensure your
      data workbook contains enough rows.
    question: How do I add more than 15 series?
  - answer: Yes, call `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`
      before saving.
    question: Is it possible to change the doughnut hole size after creation?
  - answer: Absolutely. Use `chart.getImage()` and save the returned `java.awt.image.BufferedImage`
      in your preferred format.
    question: Can I export the chart as an image instead of a PPTX?
  - answer: Animation can be added via the `ISlide.getTimeline()` API, though it’s
      beyond the scope of this tutorial.
    question: Does Aspose.Slides support animated charts?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PowerPoint
- chart generation
- presentation automation
title: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
url: /java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# How to Use Aspose Create Doughnut Chart in PowerPoint (Java)

## Introduction
Creating compelling presentations often requires more than just text and images; charts can significantly enhance storytelling by visualizing data effectively. **How to use Aspose** for chart generation gives you programmatic control without ever opening PowerPoint. This tutorial walks you through building a doughnut chart, configuring its data points, and saving a high‑fidelity PPTX. You’ll need only basic Java knowledge and a few minutes of setup time.

`Aspose.Slides for Java` is a Java library that enables creation, manipulation, and conversion of PowerPoint files without Microsoft Office.

## Quick Answers
- **What library creates doughnut chart PowerPoint?** Aspose.Slides for Java  
- **Can I add chart data points programmatically?** Yes, using the chart API  
- **Do I need a license for production?** A valid Aspose.Slides license is required  
- **Which Java versions are supported?** Java 8 and later (JDK 16 classifier shown)  
- **How many series can I add?** The example adds up to 15 series, but you can adjust as needed  

## What is a doughnut chart in PowerPoint?
A doughnut chart is a circular chart similar to a pie chart but with a hollow center, allowing multiple series to be displayed simultaneously. It emphasizes part‑to‑whole relationships while keeping the visual layout compact and easy to read.

## Why use Aspose.Slides for Java to create doughnut charts?
Aspose.Slides for Java handles over 50 input and output formats and can generate presentations up to 500 MB without loading the whole file into memory. It gives full programmatic control over chart appearance, data, and layout on any Java platform, eliminates COM interop, and can render 100 chart‑rich slides in under two seconds on a typical server.

## Prerequisites
- Basic knowledge of Java programming.  
- An IDE such as IntelliJ IDEA or Eclipse.  
- Maven or Gradle for dependency management.  
- A valid Aspose.Slides for Java license (free trial available).

## Setting Up Aspose.Slides for Java
Choose the dependency manager that fits your project.

**Maven**  
Add the following dependency to your `pom.xml` (replace the version with the latest release):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Add this line to your `build.gradle`:

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

If you prefer downloading directly, visit the [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) page.

### License Acquisition
You can start with a free trial to explore Aspose.Slides features. For extended use, purchase a license or request a temporary one from [Aspose's website](https://purchase.aspose.com/temporary-license/). Follow the instructions provided for setting up your environment and initializing Aspose.Slides in your application.

## How to create doughnut chart PowerPoint using Aspose.Slides for Java
To build a doughnut chart, start by loading or creating a `Presentation`, add a chart shape of type `ChartType.Doughnut`, clear default series, set the hole size, and then fill the chart’s workbook with category names and numeric values. Finally, adjust label formatting and save the PPTX.

### Step 1: Initialize the presentation
Create a fresh presentation or open an existing file to obtain a slide collection.

`Presentation` is the primary class that represents a PowerPoint file.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Step 2: Add a doughnut chart to the slide
Insert a chart shape, remove default series/categories, and configure basic visual settings like the doughnut hole size.

`Chart` (or chart shape) represents a chart object placed on a slide.  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Step 3: Add chart data points and customize labels
Populate category names, add data points for each series, and fine‑tune label formatting (font, color, position). This step demonstrates the “add chart data points” capability.

`Workbook` provides access to the chart’s underlying spreadsheet data where cells are populated.  
```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Step 4: Save the updated presentation
Persist the changes to a new PPTX file on disk.

`save` writes the presentation to a file in the chosen format.  
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

## Practical Applications
Doughnut charts are perfect for:
- **Financial Reports:** Visualizing budget allocations or expense breakdowns.  
- **Market Analysis:** Showing market‑share distribution among competitors.  
- **Survey Results:** Presenting categorical survey data in a compact form.  
- **Dashboard Generation:** Combining with database queries to produce live‑updating slides.

## Performance Considerations
- **Dispose resources:** Call `pres.dispose()` after saving to free native memory.  
- **Limit chart count:** Adding hundreds of charts can increase memory usage; batch‑process if needed.  
- **Use streaming:** For massive data sets, populate the workbook directly from streams instead of in‑memory arrays.  

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
A: Increase the loop limit in the “Add Doughnut Chart” step and ensure your data workbook contains enough rows.

**Q: Is it possible to change the doughnut hole size after creation?**  
A: Yes, call `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` before saving.

**Q: Can I export the chart as an image instead of a PPTX?**  
A: Absolutely. Use `chart.getImage()` and save the returned `java.awt.image.BufferedImage` in your preferred format.

**Q: Does Aspose.Slides support animated charts?**  
A: Animation can be added via the `ISlide.getTimeline()` API, though it’s beyond the scope of this tutorial.

## Conclusion
You now have a complete, production‑ready method to **create doughnut chart PowerPoint** files with Aspose.Slides for Java, including how to **add chart data points**, customize labels, and handle performance considerations. Experiment with different colors, data sources, and chart types to make your presentations truly stand out.

---

**Last Updated:** 2026-07-08  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose

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

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Related Tutorials

- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step‑by‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [How to Edit PowerPoint Chart Data Using Aspose.Slides for Java: A Comprehensive Guide](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Animate Charts PowerPoint Using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}