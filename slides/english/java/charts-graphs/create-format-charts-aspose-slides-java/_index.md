---
title: "How to create line chart with Aspose.Slides in Java – A Complete Guide"
description: "Learn how to create line chart in Java using Aspose.Slides, add chart title, add grid lines, format chart labels and save professional presentations."
date: "2026-03-07"
weight: 1
url: "/java/charts-graphs/create-format-charts-aspose-slides-java/"
keywords:
- Aspose.Slides Java
- create charts in Java
- format PowerPoint charts
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# How to create line chart with Aspose.Slides in Java

## How to create line chart in Java Using Aspose.Slides

### Introduction
Creating visually appealing presentations is crucial for effective communication. Whether you're a business professional or an educator, you often need to **create line chart** visuals that are both informative and aesthetically pleasing. In this tutorial we’ll walk through using **Aspose.Slides for Java** to generate a line chart, add chart title, add grid lines, format chart labels, and save the result as a PowerPoint file.

#### Quick Answers
- **What library is best for creating charts in Java?** Aspose.Slides for Java
- **Which chart type does this guide focus on?** Line chart with markers
- **Do I need a license to run the sample?** A free temporary license works for evaluation
- **What IDE can I use?** Any Java IDE such as IntelliJ IDEA, Eclipse, or NetBeans
- **How are chart elements formatted?** Using fluent API calls for titles, axes, grid lines, legends, and backgrounds

### What is a line chart and why use Aspose.Slides?
A line chart displays data points connected by straight lines, making it ideal for showing trends over time. Aspose.Slides lets you create and fully customize these charts programmatically, eliminating the need for manual PowerPoint editing.

### Prerequisites
- **Java Development Kit (JDK) 8+** installed
- **IDE** (IntelliJ IDEA, Eclipse, NetBeans, etc.)
- **Aspose.Slides for Java** library (added via Maven or Gradle)

#### Required Libraries and Dependencies
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

Alternatively, download the latest JAR from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### License Acquisition
- Obtain a [free trial license](https://purchase.aspose.com/temporary-license/) for testing.
- Purchase a full license from [Aspose's official site](https://purchase.aspose.com/buy) for production use.

### Setting Up Aspose.Slides for Java
1. **Add the dependency** shown above to your project.
2. **Apply the license** (if you have one) before creating any presentation objects.

```java
import com.aspose.slides.Presentation;
// Initialize the Presentation object
Presentation pres = new Presentation();
```

## Step‑by‑Step Implementation

### Step 1: Create the output directory (create directory java)
```java
import java.io.File;
// Define the target directory
String dataDir = "YOUR_DOCUMENT_DIRECTORY";

// Check if directory exists; create it if not
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs(); // Create directories recursively
}
```
*Why this matters:* Ensuring the folder exists prevents `FileNotFoundException` when you later save the presentation.

### Step 2: Add a slide and insert a line chart
```java
import com.aspose.slides.*;
// Create a new presentation
Presentation pres = new Presentation();
try {
    // Access the first slide
    ISlide slide = pres.getSlides().get_Item(0);

    // Add a chart to the slide
    IChart chart = slide.getShapes().addChart(
        ChartType.LineWithMarkers, 50, 50, 500, 400);
```
*Explanation:* This creates a fresh slide and places a **line chart with markers** at the specified coordinates.

### Step 3: Add chart title (add chart title)
```java
// Enable and format the title
chart.setTitle(true);
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding()
    .getParagraphs().get_Item(0).getPortions().get_Item(0);

chartTitle.setText("Sample Line Chart");
chartTitle.getPortionFormat().setFontBold(NullableBool.True);
chartTitle.getPortionFormat().setFillType(FillType.Solid);
chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
chartTitle.getPortionFormat().setFontHeight(20);
```
*Tip:* Using a bold, gray title makes the chart instantly recognizable.

### Step 4: Format axes and add grid lines (add grid lines)
#### Vertical Axis Formatting
```java
IChartAxis verticalAxis = chart.getAxes().getVerticalAxis();

// Format major grid lines
verticalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.BLUE);
verticalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Configure axis properties
verticalAxis.setNumberFormat("0.0%");
verticalAxis.setMaxValue(15f);
verticalAxis.setMinValue(-2f);
```

#### Horizontal Axis Formatting
```java
IChartAxis horizontalAxis = chart.getAxes().getHorizontalAxis();

// Format major grid lines
horizontalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.GREEN);
horizontalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Set label positions and rotations
horizontalAxis.setTickLabelPosition(TickLabelPositionType.Low);
horizontalAxis.setTickLabelRotationAngle(45);
```
*Why this matters:* Clear grid lines and rotated labels improve readability, especially when data points are dense.

### Step 5: Customize the legend (add chart title – already covered, but legend is part of overall formatting)
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Prevent overlap with the chart area
chart.getLegend().setOverlay(true);
```

### Step 6: Set background colors (format chart labels – part of overall visual styling)
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```

### Step 7: Save the presentation
```java
// Save the presentation to disk
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // Clean up resources
}
```
*Result:* You now have a PowerPoint file (`FormattedChart_out.pptx`) containing a fully formatted line chart.

## Practical Applications
- **Business Reports:** Showcase quarterly performance with trend lines.
- **Educational Slides:** Visualize scientific data for lectures.
- **Project Proposals:** Highlight milestones and forecasts.
- **Marketing Analysis:** Present campaign ROI trends.
- **Dashboard Integration:** Export live data to PowerPoint for stakeholder meetings.

## Performance Considerations
- **Memory Management:** Always call `dispose()` on the `Presentation` object to release native resources promptly.

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| **License not applied** | Load the trial/full license before creating any `Presentation` objects. |
| **Chart appears blank** | Verify that the slide actually contains data series; add series if needed. |
| **File not saved** | Ensure the output directory exists (use the “create directory java” step). |
| **Colors not applied** | Use `Color` constants from `java.awt.Color` or `PresetColor`. |

## Frequently Asked Questions

**Q: Can I create other chart types besides line charts?**  
A: Yes, Aspose.Slides supports bar, pie, scatter, and many more chart types.

**Q: How do I add multiple data series to the line chart?**  
A: Use `chart.getChartData().getSeries().add(...)` to insert additional series before formatting.

**Q: Is it possible to export the chart as an image?**  
A: Absolutely. Call `chart.getChartData().getChartDataWorkbook().save(...)` or render the slide to an image format.

**Q: Do I need a paid license for development?**  
A: A free temporary license works for evaluation; a commercial license is required for production deployments.

**Q: Which Java versions are supported?**  
A: The library works with JDK 8 through JDK 22 (use the appropriate classifier, e.g., `jdk16`). 

---

**Last Updated:** 2026-03-07  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}