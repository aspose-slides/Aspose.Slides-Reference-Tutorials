---
date: '2026-07-17'
description: Learn how to add sunburst charts in PowerPoint using Aspose Slides for
  Java. Step‑by‑step guide covers setup, chart creation, customization, and real‑world
  use cases.
images:
- /java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/og-image.png
keywords:
- how to add sunburst
- create sunburst chart powerpoint
- create powerpoint presentation java
lastmod: '2026-07-17'
og_description: How to add sunburst charts in PowerPoint using Aspose Slides for Java.
  Follow this tutorial to set up the library, create a chart, customize data points,
  and apply it to real projects.
og_image_alt: 'Developer guide: Add sunburst chart to PowerPoint using Aspose Slides
  for Java'
og_title: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  headline: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  type: TechArticle
- description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  name: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  steps:
  - name: Add Sunburst Chart
    text: The `IChart` interface defines a chart object that can be placed on any
      slide. Here we add a sunburst chart at coordinates (100, 100) with a size of
      450 × 400 points.
  - name: Save the Presentation
    text: Always persist your changes by calling `save`. You can choose PPTX, PDF,
      or any of the 50+ supported output formats.
  - name: Access Data Points Collection
    text: The first series of the chart holds a collection of `IChartDataPoint` objects
      that represent each slice.
  - name: Show Value for a Specific Data Point
    text: Set `IsValueShown` to `true` on the desired data point to display its numeric
      value directly on the slice.
  - name: Modify Label Formats
    text: Adjust label visibility, font color, and background to improve readability.
  - name: Set Fill Color for Data Points
    text: Customize the fill color of individual slices to match your brand palette
      or to highlight key segments.
  - name: Save the Modified Presentation
    text: Persist the customized chart by saving the presentation again.
  type: HowTo
- questions:
  - answer: A sunburst chart visualizes hierarchical data in concentric rings, with
      each ring representing a level of the hierarchy.
    question: What is a sunburst chart?
  - answer: Add the Maven dependency shown in the “Maven Dependency” section to your
      `pom.xml` and run `mvn clean install`.
    question: How do I install Aspose.Slides for Java using Maven?
  - answer: Yes, the library supports over 50 chart types, including column, line,
      pie, and radar charts.
    question: Can I customize other chart types with Aspose.Slides?
  - answer: Verify the file path is correct, the directory exists, and you have write
      permissions. Also, ensure the `Presentation.save()` method is called.
    question: My presentation isn’t saving—what should I check?
  - answer: Visit the [Aspose forum](https://forum.aspose.com/c/slides/11) or consult
      the official [Aspose.Slides reference](https://reference.aspose.com/slides/java/).
    question: Where can I get more help or examples?
  type: FAQPage
tags:
- sunburst chart
- Aspose.Slides
- Java PowerPoint
- data visualization
title: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
url: /java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# How to Add Sunburst Charts in PowerPoint with Aspose (Java)

## Introduction

Adding a sunburst chart to a PowerPoint deck can instantly turn a flat data table into an engaging visual hierarchy. In this tutorial you’ll learn **how to add sunburst** charts in PowerPoint using Aspose.Slides for Java, from environment setup to fine‑tuning colors and labels. Whether you’re building a sales dashboard, a project‑task breakdown, or an educational slide deck, the steps below will give you a production‑ready solution.

**What You’ll Learn**
- How to configure Aspose.Slides in a Maven or Gradle project  
- How to create a new presentation and insert a sunburst chart  
- How to customize data points, labels, and fill colors  
- Real‑world scenarios where sunburst charts shine  

Let’s get started and see how easy it is to turn raw hierarchy data into a polished PowerPoint visual.

## Quick Answers
- **Primary library?** Aspose.Slides for Java  
- **Supported chart type?** Sunburst (radial hierarchical)  
- **Minimum Java version?** JDK 16  
- **Typical implementation time?** 10‑15 minutes for a basic chart  
- **License needed for production?** Yes, a valid Aspose license  

## What is a Sunburst Chart?
A sunburst chart is a radial diagram that visualizes hierarchical data by nesting rings outward from a central point. It’s perfect for showing multi‑level relationships such as organization structures, product categories, or file‑system trees. Each concentric ring represents a level of the hierarchy, and the size of each segment reflects its quantitative value, allowing viewers to quickly grasp both structure and magnitude.

## Why Use Aspose.Slides for Java?
Aspose.Slides supports **50+ chart types** and can manipulate presentations with **up to 10,000 slides** without loading the entire file into memory, delivering high performance for enterprise‑scale reporting. It works cross‑platform, offers extensive API coverage, and includes robust licensing options that remove evaluation limits, making it ideal for production environments.

## Prerequisites
- **Java Development Kit (JDK)** 16 or newer  
- **IDE** – IntelliJ IDEA, Eclipse, or any Java‑compatible editor  
- Basic familiarity with Java syntax and Maven/Gradle build tools  

## Setting Up Aspose.Slides for Java

### Maven Dependency
Add the Aspose.Slides Maven artifact to your `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle Dependency
If you prefer Gradle, include the following line in `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download
You can also download the latest JAR directly from the official releases page: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### License Acquisition
To run without evaluation limits, obtain a license:
- **Free trial** – temporary license for quick evaluation.  
- **Temporary license** – request one from the [Aspose website](https://purchase.aspose.com/temporary-license).  
- **Full purchase** – buy a subscription for unlimited production use.

### Basic Initialization
The `Presentation` class is the entry point for creating or opening PowerPoint files.

```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialize Aspose.Slides with a license if available
        Presentation pres = new Presentation();
        try {
            // Your code here...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## Implementation Guide

### How to add a sunburst chart to a PowerPoint presentation using Aspose.Slides for Java?

Load a new `Presentation`, add a slide, insert an `IChart` of type `ChartType.Sunburst`, and call `save`. This concise three‑step pattern creates a fully functional sunburst chart ready for further customization.

#### Step 1: Initialize the Presentation
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Replace with your path
```

#### Step 2: Add Sunburst Chart
The `IChart` interface defines a chart object that can be placed on any slide. Here we add a sunburst chart at coordinates (100, 100) with a size of 450 × 400 points.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

#### Step 3: Save the Presentation
Always persist your changes by calling `save`. You can choose PPTX, PDF, or any of the 50+ supported output formats.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Modify Data Points in Chart

#### Overview
You can tailor every slice of the sunburst—labels, colors, and visibility—through the chart’s data point collection.

#### Step 1: Access Data Points Collection
The first series of the chart holds a collection of `IChartDataPoint` objects that represent each slice.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

#### Step 2: Show Value for a Specific Data Point
Set `IsValueShown` to `true` on the desired data point to display its numeric value directly on the slice.

```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

#### Step 3: Modify Label Formats
Adjust label visibility, font color, and background to improve readability.

```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

#### Step 4: Set Fill Color for Data Points
Customize the fill color of individual slices to match your brand palette or to highlight key segments.

```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

#### Step 5: Save the Modified Presentation
Persist the customized chart by saving the presentation again.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Practical Applications

1. **Business Analytics** – Visualize sales by region → product line → SKU in a single radial view.  
2. **Project Management** – Show work breakdown structures, drilling from phases to tasks to subtasks.  
3. **Education** – Map curriculum hierarchies, such as departments → courses → modules.  

## Performance Considerations

- **Memory Efficiency:** Aspose.Slides streams data, so even a 500‑page deck with multiple charts stays under 200 MB of RAM.  
- **Garbage Collection:** Release slide objects (`slide.dispose()`) when they are no longer needed to avoid memory leaks.  

## Frequently Asked Questions

**Q: What is a sunburst chart?**  
A: A sunburst chart visualizes hierarchical data in concentric rings, with each ring representing a level of the hierarchy.

**Q: How do I install Aspose.Slides for Java using Maven?**  
A: Add the Maven dependency shown in the “Maven Dependency” section to your `pom.xml` and run `mvn clean install`.

**Q: Can I customize other chart types with Aspose.Slides?**  
A: Yes, the library supports over 50 chart types, including column, line, pie, and radar charts.

**Q: My presentation isn’t saving—what should I check?**  
A: Verify the file path is correct, the directory exists, and you have write permissions. Also, ensure the `Presentation.save()` method is called.

**Q: Where can I get more help or examples?**  
A: Visit the [Aspose forum](https://forum.aspose.com/c/slides/11) or consult the official [Aspose.Slides reference](https://reference.aspose.com/slides/java/).

## Resources
- **Documentation:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Reference (lowercase):** [Aspose.Slides reference](https://reference.aspose.com/slides/java/)  
- **Community Forum:** [Aspose Forum](https://forum.aspose.com/c/slides)  
- **Downloads:** [Aspose.Slides Downloads](https://releases.aspose.com/slides/java)  

---

**Last Updated:** 2026-07-17  
**Tested With:** Aspose.Slides for Java 24.12  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Related Tutorials

- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step-by-Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Animate Charts PowerPoint Using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Create chart in Java with Aspose.Slides – Add & Validate Charts](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}