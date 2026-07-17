---
date: '2026-07-17'
description: Learn how to rotate pie chart, customize pie chart colors, and export
  slide to PDF using Aspose.Slides for Java – a full data visualization guide.
images:
- /java/charts-graphs/aspose-slides-java-pie-charts-tutorial/og-image.png
keywords:
- rotate pie chart
- customize pie chart colors
- export slide to pdf
- chart data worksheet
- java data visualization
lastmod: '2026-07-17'
og_description: Rotate pie chart and customize pie chart colors using Aspose.Slides
  for Java. Learn to export slide to PDF and work with chart data worksheet.
og_image_alt: Guide showing how to rotate a pie chart and set custom colors in Java
  with Aspose.Slides
og_title: Rotate Pie Chart and Customize Colors in Java – Aspose.Slides Guide
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
title: How to Rotate Pie Chart and Customize Colors in Java with Aspose.Slides
url: /java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Creating Pie Charts with Aspose.Slides for Java: A Complete Tutorial

## Introduction
In this guide you’ll learn how to **rotate pie chart** elements, customize each slice’s color, and export the final slide to PDF—all with Aspose.Slides for Java. Whether you’re building a sales dashboard, a financial report, or any data‑driven presentation, mastering these techniques lets you deliver clear, eye‑catching visuals without relying on Microsoft Office. Let’s get the tools ready and dive in.

## Quick Answers
- **What class starts a new presentation?** `Presentation` from `com.aspose.slides`.
- **Which API call adds a pie chart?** `slide.addChart(ChartType.Pie, …)`.
- **How can you give each slice a unique color?** Call `series.setColorVaried(true)` and set solid fills per data point.
- **What method rotates the chart?** `chart.setRotationAngle(double)` – use degrees from 0 to 360.
- **Can the slide be exported to PDF?** Yes, invoke `presentation.save("output.pdf", SaveFormat.Pdf)`.

## What is “customize pie chart colors”?
Customizing pie chart colors means assigning distinct fill colors to each slice of the pie, improving readability and visual impact. In Aspose.Slides you achieve this by enabling varied colors and then setting solid fill colors for individual data points. This approach ensures each data segment stands out clearly in the presentation.

## Why use Aspose.Slides for Java to create pie charts?
Aspose.Slides supports **150+ chart types** and can render a 300‑page presentation in under **5 seconds** on a typical server, all without needing Microsoft Office installed. The library runs on Windows, Linux, and macOS, giving you cross‑platform flexibility for any Java‑based data‑visualization project.

## Prerequisites
- **Aspose.Slides for Java** ≥ 25.4
- **JDK** 16 or newer
- IDE such as IntelliJ IDEA, Eclipse, or NetBeans
- Basic Java knowledge and familiarity with Maven or Gradle

## Setting Up Aspose.Slides for Java
Add the library to your build configuration.

**Maven**  
Add this snippet to your `pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Include the following in your `build.gradle` file:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download**  
If you prefer a manual approach, download the latest JAR from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### License Acquisition Steps
- **Free Trial** – explore all features without cost.  
- **Temporary License** – extend trial limits for a short period.  
- **Purchase** – obtain a permanent license for production use.

**Basic Initialization and Setup**  
The `Presentation` class represents a PowerPoint file in memory and provides methods to manipulate slides.  
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Implementation Guide
Below is a step‑by‑step walkthrough that covers everything from creating a slide to rotating the final pie chart.

### Initialize Presentation and Slide
Create a new `Presentation` instance and retrieve the first slide to serve as the chart canvas.  
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Add Pie Chart to Slide
`addChart` adds a chart shape of the specified type to the slide at given coordinates.  
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Set Chart Title
`setTitle` assigns a text title to the chart and positions it centrally.  
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Configure Data Labels for Series
`setShowValue(true)` enables numeric value labels on each data point of the series.  
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Prepare Chart Data Worksheet
`ChartDataWorkbook` stores the underlying data table that feeds the chart series and categories.  
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Add Categories to Chart
`addCategory` creates a new category label for the chart's data series.  
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Add Series and Populate Data Points
`addSeries` creates a data series, and `addDataPointForBarSeries` inserts numeric values for each category.  
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Customize Series Colors and Borders
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

### Configure Custom Data Labels
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

### Set Rotation Angle and Save Presentation
`setRotationAngle` rotates the entire pie chart, and `save` writes the presentation to a file.  
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## How to rotate pie chart?
Load the chart object, call `chart.setRotationAngle(45.0)` (or any degree value), and then save the presentation. Rotating a pie chart shifts the start angle, allowing you to emphasize a particular segment without altering the data. This single method call works for any `Chart` instance in Aspose.Slides. You can also combine rotation with varied slice colors to draw attention to the most important data point.

## Common Issues and Solutions
| Issue | Cause | Fix |
|-------|-------|-----|
| **Slices all appear the same color** | `setColorVaried(true)` not called | Ensure you enable varied colors on the series group. |
| **Data labels not showing** | `showValue` flag disabled | Call `setShowValue(true)` on the label format. |
| **Rotation has no effect** | Using an older Aspose.Slides version | Upgrade to version 25.4 or later. |
| **License exception at runtime** | Missing or invalid license file | Load your license with `License license = new License(); license.setLicense("Aspose.Slides.lic");` before creating the `Presentation`. |

## Frequently Asked Questions

**Q: How do I obtain an Aspose.Slides license for Java?**  
A: Request a free trial from the Aspose website, then purchase a permanent license. Load it at runtime as shown in the Common Issues table.

**Q: Can I use this code with older JDK versions?**  
A: The API requires JDK 16 or higher; older versions are not supported.

**Q: Is it possible to export the chart as an image instead of PPTX?**  
A: Yes—after rendering, call `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);`.

**Q: What if I need more than one series in a pie chart?**  
A: Pie charts are designed for a single data series; for multiple series, consider using a doughnut chart.

**Q: Does Aspose.Slides run on Linux servers?**  
A: Absolutely—Aspose.Slides for Java is platform‑independent and works on any OS with a compatible JDK.

---

**Last Updated:** 2026-07-17  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Related Tutorials

- [How to Create Pie Charts in Java Presentations Using Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/)
- [Master Pie Charts in Java Using Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/master-pie-charts-aspose-slides-java/)
- [Rotate Chart Texts in Java with Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/rotate-chart-texts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}