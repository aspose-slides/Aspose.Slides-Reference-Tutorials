---
title: "Create Doughnut Charts in Java using Aspose.Slides&#58; A Comprehensive Guide"
description: "Learn how to create stunning doughnut charts in Java with Aspose.Slides. This comprehensive guide covers initialization, data configuration, and saving presentations."
date: "2025-04-17"
weight: 1
url: "/java/charts-graphs/create-doughnut-charts-java-aspose-slides/"
keywords:
- create doughnut charts Java
- Aspose.Slides Java guide
- Java data visualization

---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}
# Create Doughnut Charts in Java Using Aspose.Slides: A Step-by-Step Guide

## Introduction

In today's data-driven environment, visualizing information effectively is key to enhancing understanding and engagement. While creating professional charts programmatically can seem challenging, especially with Java, this guide will walk you through using Aspose.Slides for Java to create Doughnut charts effortlessly.

By following these steps, developers will gain hands-on experience in manipulating presentation slides and integrating data visualization seamlessly.

**Key Takeaways:**
- Initialize a Presentation object using Aspose.Slides Java.
- Configure chart data and manage existing series or categories.
- Add and customize series and categories for your charts.
- Format and display data points effectively.
- Save your presentation in various formats with ease.

Before diving into the implementation, ensure you have everything needed to get started.

## Prerequisites

To follow this tutorial, make sure you have:

- **Required Libraries:**
  - Aspose.Slides for Java version 25.4 or later.
  
- **Environment Setup:**
  - JDK 16 or higher installed on your system.
  - An IDE like IntelliJ IDEA, Eclipse, or NetBeans.

- **Knowledge Prerequisites:**
  - Basic understanding of Java programming concepts.
  - Familiarity with managing dependencies in Maven or Gradle projects.

## Setting Up Aspose.Slides for Java

To integrate Aspose.Slides into your project, follow these steps based on your build tool:

**Maven Setup:**
Add the following dependency to your `pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle Setup:**
Include the following in your `build.gradle` file:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download:**
Alternatively, download the latest version directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Acquiring a License

To use Aspose.Slides without evaluation limitations:
- **Free Trial:** Start with a temporary license to explore full features.
- **Temporary License:** Obtain one via the [Aspose website](https://purchase.aspose.com/temporary-license/).
- **Purchase:** Consider purchasing for ongoing use.

Apply your license in your Java application using:
```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Implementation Guide

### Initializing Presentation and Chart

#### Overview
Begin by initializing a presentation object and adding a Doughnut chart to the first slide.

**Step 1: Initialize Presentation**
Load an existing PPTX file or create a new one:
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

**Step 2: Add Doughnut Chart**
Create a chart on the first slide at specified coordinates:
```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Configuring Chart Data Workbook and Clearing Existing Series/Categories

#### Overview
Configure the chart data workbook and remove any pre-existing series or categories.

**Step 1: Access Chart Data Workbook**
Retrieve the workbook linked with your chart:
```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

**Step 2: Clear Existing Series and Categories**
Ensure there are no residual data points:
```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Adding Series to Chart

#### Overview
Populate your chart with multiple series, each customized for appearance and behavior.

**Step 1: Add Series Iteratively**
Loop through indices to add series:
```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Adding Categories and Data Points to Chart

#### Overview
Configure categories and add data points with specific formatting for labels.

**Step 1: Add Categories**
Loop through indices for each category:
```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

**Step 2: Add Data Points to Each Series**
Iterate through each series for the current category:
```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### Saving the Presentation

#### Overview
Once you've configured your chart, save the presentation to a specified directory.

**Step 1: Save the Presentation**
Use the `save` method to write changes:
```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Conclusion

You've now learned how to create and customize Doughnut charts in Java using Aspose.Slides. These steps provide a foundation for integrating sophisticated data visualizations into your presentations.

**Next Steps:**
- Experiment with different chart types available in Aspose.Slides.
- Explore additional customization options like colors, fonts, and styles to match your branding needs.
{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}