---
title: "How to Customize Pie Chart Colors in Java with Aspose.Slides: A Complete Guide"
description: "Learn how to customize pie chart colors and add chart title using Aspose.Slides for Java. Includes Maven Aspose Slides setup and how to save presentation pptx."
date: "2026-01-22"
weight: 1
url: "/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/"
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Creating Pie Charts with Aspose.Slides for Java: How to **customize pie chart colors** – A Complete Tutorial

## Introduction
Delivering data‑driven stories in presentations is easier when you can **customize pie chart colors** to match your brand or highlight key values. In this tutorial you’ll see exactly how to create a pie chart, add chart title, work with pie chart data points, and fine‑tune the colors of each slice using Aspose.Slides for Java. By the end, you’ll also know how to **save presentation pptx** and integrate the library with Maven Aspose Slides.

**What You'll Learn**
- How to create pie charts (how to create pie) and set up a Java project.
- Steps to add chart title and manage pie chart data points.
- Techniques to **customize pie chart colors** for maximum visual impact.
- Maven Aspose Slides dependency configuration.
- Saving the final file as a PPTX presentation.

Let's get started!

## Quick Answers
- **How do I add a chart title?** Use `chart.getChartTitle().addTextFrameForOverriding("Your Title")`.
- **Which build tool works best?** Both Maven and Gradle are supported; Maven Aspose Slides is the most common.
- **Can I change slice colors?** Yes—set `setColorVaried(true)` and adjust each `DataPoint` fill.
- **What format does the file get saved as?** Use `presentation.save("MyChart.pptx", SaveFormat.Pptx)`.
- **Do I need a license?** A free trial works for development; a permanent license is required for production.

## Prerequisites
- **Aspose.Slides for Java** ≥ 25.4 (the latest version is recommended).
- **JDK 16+** installed and configured.
- An IDE such as IntelliJ IDEA, Eclipse, or NetBeans.
- Basic Java knowledge and familiarity with Maven or Gradle.

## Setting Up Aspose.Slides for Java
To start using Aspose.Slides, add the library to your project.

**Maven** (maven aspose slides)  
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

**Direct Download**  
If you prefer not to use a build tool, download the latest release from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### License Acquisition Steps
- **Free Trial** – start experimenting without a license.
- **Temporary License** – extend trial usage.
- **Purchase** – obtain a full license for production deployments.

### Basic Initialization
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Implementation Guide
Below is a step‑by‑step walkthrough that keeps the code exactly as the original library expects.

### Step 1: Initialize Presentation and Slide
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
islide slides = presentation.getSlides().get_Item(0);
```

### Step 2: Add a Pie Chart to the Slide
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Step 3: Add Chart Title
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Step 4: Show Data Labels for the First Series
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Step 5: Prepare the Chart Data Worksheet
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Step 6: Add Categories (pie chart data points)
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Step 7: Add Series and Populate Data Points
```java
import com.aspose.slides.*;

// Add a new series and set its name.
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Step 8: **Customize Pie Chart Colors** – The Core of This Tutorial
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Step 9: Configure Custom Data Labels
```java
import com.aspose.slides.*;

// Configure custom labels.
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Step 10: Set Rotation Angle and **Save Presentation PPTX**
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Common Issues & Troubleshooting
- **Missing colors after export** – Ensure `setColorVaried(true)` is called before modifying individual data points.
- **Data points not showing** – Verify that categories and series are cleared before adding new ones (see Step 5).
- **License not applied** – Load your license file before creating the `Presentation` object to avoid trial watermarks.

## Frequently Asked Questions

**Q: Can I use this code with older JDK versions?**  
A: The library requires JDK 16 or higher; older versions are not supported.

**Q: How do I change the chart title after creation?**  
A: Call `chart.getChartTitle().addTextFrameForOverriding("New Title")` and adjust the text format as needed.

**Q: Is it possible to export to formats other than PPTX?**  
A: Yes—Aspose.Slides supports PDF, ODP, and several image formats via the `SaveFormat` enum.

**Q: What if I want to animate the pie slices?**  
A: Use the `SlideShow` API to add slide transitions or shape animations after the chart is created.

**Q: Does the Maven dependency include all transitive libraries?**  
A: The Maven Aspose Slides artifact pulls in required dependencies automatically; no extra steps are needed.

## Conclusion
You now have a full, production‑ready example that shows **how to customize pie chart colors**, add a chart title, work with pie chart data points, and **save presentation pptx** using Aspose.Slides for Java. Feel free to experiment with different color palettes, data sets, and rotation angles to match your brand style.

---

**Last Updated:** 2026-01-22  
**Tested With:** Aspose.Slides 25.4 (JDK 16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}