---
title: "Create and Customize Charts in Java Presentations Using Aspose.Slides"
description: "Learn how to create, customize, and save charts with percentage labels in Java presentations using Aspose.Slides. Enhance your presentation skills today!"
date: "2025-04-17"
weight: 1
url: "/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/"
keywords:
- create Java charts
- customize Aspose.Slides charts
- Java presentation charts

---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Create and Customize Charts in Java Presentations Using Aspose.Slides

## Introduction
Creating compelling presentations often involves more than just text; it requires dynamic charts that convey information effectively. If you're looking to enhance your Java-based presentations with sophisticated chart features using Aspose.Slides, this tutorial is for you. We'll guide you through creating a presentation, adding and configuring charts, calculating totals, displaying percentage labels, and saving your work—all in just a few easy steps.

**What You’ll Learn:**
- How to create and customize presentations with charts using Aspose.Slides for Java
- Calculating category totals in charts
- Displaying data as percentage labels on charts
- Saving presentations with enhanced chart features

Let's dive into the prerequisites you need before getting started.

## Prerequisites
To follow this tutorial, ensure you have the following:

- **Java Development Kit (JDK)**: Version 8 or higher.
- **IDE**: Such as IntelliJ IDEA, Eclipse, or any Java-supported IDE.
- **Aspose.Slides for Java Library**: This is crucial for handling presentation features.

### Required Libraries and Versions
You’ll need Aspose.Slides for Java. Here's how to include it in your project:

**Maven:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternatively, you can directly download the latest version from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Environment Setup
Ensure your development environment is configured to use JDK 8 or later and that your IDE is set up to manage dependencies using Maven or Gradle.

**License Acquisition:**
- **Free Trial**: Access basic features for testing purposes.
- **Temporary License**: Test advanced features without evaluation limitations.
- **Purchase**: For long-term commercial use, consider purchasing a license.

## Setting Up Aspose.Slides for Java
Begin by setting up the Aspose.Slides library in your Java project. Here’s how to initialize and configure it:

1. Add the dependency via Maven or Gradle as shown above.
2. Import the necessary Aspose.Slides packages:
   ```java
   import com.aspose.slides.*;
   ```

3. Initialize a new `Presentation` instance:
   ```java
   Presentation presentation = new Presentation();
   ```

This setup will allow you to start building presentations programmatically.

## Implementation Guide

### Create and Customize Charts in Your Presentation

#### Overview
Creating a chart involves initializing your presentation, accessing slides, and adding a chart with specific attributes like type, position, and size.

**Steps:**
1. **Create Presentation Instance**: Start by creating an instance of the `Presentation` class.
2. **Access Slide**: Retrieve the first slide using `get_Item(0)`.
3. **Add Chart**: Use `addChart()` to add a stacked column chart at specified coordinates with defined dimensions.

```java
// Feature: Create a Presentation with Chart
import com.aspose.slides.*;

try {
    Presentation presentation = new Presentation();
    ISlide slide = presentation.getSlides().get_Item(0);
    
    IChart chart = slide.getShapes().addChart(
        ChartType.StackedColumn,
        20, 20, 400, 400
    );
} finally {
    if (presentation != null) presentation.dispose();
}
```

### Calculate Totals for Categories

#### Overview
Calculating category totals involves iterating through each series in the chart to sum up values per category.

**Steps:**
1. **Initialize Array**: Create an array to hold total values.
2. **Iterate Through Categories and Series**: Use nested loops to accumulate totals for each category from all series.

```java
// Feature: Calculate Totals for Categories in a Chart
import com.aspose.slides.*;

public void calculateCategoryTotals(IChart chart, double[] total_for_Cat) {
    for (int k = 0; k < chart.getChartData().getCategories().size(); k++) {
        IChartCategory cat = chart.getChartData().getCategories().get_Item(k);
        total_for_Cat[k] = 0;

        for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
            double value = (double) (
                chart.getChartData().getSeries().get_Item(i).
                    getDataPoints().get_Item(k).
                    getValue().getData());
            total_for_Cat[k] += value;
        }
    }
}
```

### Display Data as Percentage Labels on a Chart

#### Overview
This feature focuses on configuring data labels to display values as percentages, providing clarity in the visualization.

**Steps:**
1. **Configure Series Labels**: Set up label properties such as font size and visibility of legend keys.
2. **Calculate Percentages**: Compute percentage for each data point based on total category value.
3. **Set Label Text**: Format labels to show percentages with two decimal points.

```java
// Feature: Display Data as Percentage Labels on a Chart
import com.aspose.slides.*;

public void displayPercentageLabels(IChart chart, double[] total_for_Cat) {
    for (int x = 0; x < chart.getChartData().getSeries().size(); x++) {
        IChartSeries series = chart.getChartData().getSeries().get_Item(x);
        
        series.getLabels().getDefaultDataLabelFormat().setShowLegendKey(false);

        for (int j = 0; j < series.getDataPoints().size(); j++) {
            IDataLabel lbl = series.getDataPoints().get_Item(j).getLabel();
            double dataPontPercent = (double) (
                series.getDataPoints().get_Item(j).
                    getValue().getData()) / total_for_Cat[j] * 100;

            IPortion port = new Portion();
            port.setText(String.format("{0:F2} %%", dataPontPercent));
            port.getPortionFormat().setFontHeight(8f);
            
            lbl.getTextFrameForOverriding().setText("");
            IParagraph para = lbl.getTextFrameForOverriding().getParagraphs().get_Item(0);
            para.getPortions().add(port);

            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowPercentage(false);
            lbl.getDataLabelFormat().setShowLegendKey(false);
            lbl.getDataLabelFormat().setShowCategoryName(false);
            lbl.getDataLabelFormat().setShowBubbleSize(false);
        }
    }
}
```

### Save Presentation with Chart

#### Overview
Finally, save your presentation to a specified path in PPTX format.

**Steps:**
1. **Save Method**: Use the `save()` method on the `Presentation` instance.
2. **Dispose Resources**: Ensure resources are released after saving.

```java
// Feature: Save Presentation with Chart
import com.aspose.slides.*;

public void savePresentation(Presentation presentation, String outputPath) {
    try {
        presentation.save(outputPath + "DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Practical Applications

1. **Financial Reporting**: Use charts to display revenue growth percentages across departments.
2. **Sales Data Analysis**: Visualize sales data by region with percentage labels for clearer insights.
3. **Educational Presentations**: Enhance academic presentations with visual statistics.
4. **Marketing Campaigns**: Display campaign performance metrics as engaging visuals.
5. **Business Strategy Meetings**: Use charts to convey complex data in strategic planning discussions.

## Performance Considerations
- **Memory Management**: Dispose of `Presentation` objects promptly to free up resources.
- **Optimize Chart Loading**: Only load essential chart elements into memory if possible.
- **Batch Processing**: When processing multiple presentations, consider handling them in batches to manage resource consumption effectively.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}