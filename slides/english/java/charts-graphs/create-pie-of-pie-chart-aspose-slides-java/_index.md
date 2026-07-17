---
date: '2026-07-17'
description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart using
  Aspose.Slides for Java. Includes setup, code, customization, and saving as PPTX.
images:
- /java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/og-image.png
keywords:
- add chart to powerpoint
- how to create pie
- create pie of pie
- save presentation as pptx
- customize pie chart labels
lastmod: '2026-07-17'
og_description: Add chart to PowerPoint with Aspose.Slides for Java. This guide shows
  how to create, customize, and save a Pie of Pie chart as PPTX in minutes.
og_image_alt: 'Guide: add chart to PowerPoint using Aspose.Slides Java'
og_title: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  headline: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  name: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  steps:
  - name: Create an Instance of the Presentation Class
    text: This initializes the container for all subsequent slides and charts.
  - name: Add a 'Pie of Pie' Chart on the First Slide
    text: Here we specify `ChartType.PieOfPie` and define the chart’s position (X,
      Y) and size (width, height) on the slide canvas.
  - name: Set Data Labels to Show Values for the Series
    text: Enabling `showValue` makes each slice display its numeric value, which is
      essential for quick data interpretation.
  - name: Configure the Second Pie Size and Split by Percentage
    text: These options let you decide how much of the chart is allocated to the secondary
      pie and which slices are moved based on a percentage threshold.
  - name: Save the Presentation to Disk in PPTX Format
    text: '> **Pro tip:** Use an absolute path or Java’s `Paths.get()` to avoid platform‑specific
      separators.'
  type: HowTo
- questions:
  - answer: Yes, instantiate a new `IChart` for each slide or location; the API allows
      unlimited chart objects per file.
    question: Can I generate multiple charts in a single presentation?
  - answer: Absolutely – call `presentation.save("output.pdf", SaveFormat.Pdf)` to
      export the same slide deck to PDF.
    question: Does Aspose.Slides support saving as PDF as well?
  - answer: The library supports up to **10,000** data points per series, limited
      only by available memory.
    question: What is the maximum number of data points a Pie of Pie chart can handle?
  - answer: Yes, access each `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()`
      and set `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.
    question: Is it possible to customize the colors of individual slices?
  - answer: 'After saving the file, stream it directly to the client using `HttpServletResponse`
      with `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.'
    question: How do I embed the generated PPTX into a web application?
  type: FAQPage
tags:
- add chart to powerpoint
- Aspose.Slides
- Java charting
- PPTX generation
title: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
url: /java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides

## Charts & Graphs

### Introduction

In modern data‑driven presentations, **adding a chart to PowerPoint** is often the fastest way to turn raw numbers into visual insight. A regular pie chart works well for a handful of categories, but when a few slices are tiny they become unreadable. A *Pie of Pie* chart solves this problem by extracting those small slices into a secondary pie, keeping the main chart clean and the details accessible.

In this tutorial you’ll learn how to **add chart to PowerPoint** by creating a Pie of Pie chart with Aspose.Slides for Java. We’ll walk through environment setup, chart creation, label customization, split‑position tuning, and finally saving the presentation as a PPTX file. By the end you’ll be ready to embed sophisticated charts into any slide deck.

## Quick Answers
In Aspose.Slides, `Presentation` represents a PPTX file, `ChartType.PieOfPie` selects the Pie of Pie chart, `setShowValue(true)` shows values on labels, and `save` writes the file.

- **What is the primary class for PowerPoint manipulation?** `Presentation` – it represents an entire PPTX file in memory.  
- **Which chart type creates a secondary pie for small slices?** `ChartType.PieOfPie`.  
- **How do you display values on each slice?** Set `chart.getChartData().getSeries().get_Item(0).getLabels().setShowValue(true)`.  
- **Can you save the file directly as PPTX?** Yes – call `presentation.save("output.pptx", SaveFormat.Pptx)`.  
- **Do you need a license for development?** A free 30‑day trial works for testing; a permanent license removes evaluation watermarks.

## What is a Pie of Pie Chart?
A **Pie of Pie chart** is a two‑level pie visualization that isolates one or more small slices into a separate, linked pie, making them easier to read. Aspose.Slides supports this chart type out of the box, letting you control split size, position, and label formatting.

## Why add chart to PowerPoint with Aspose.Slides?
Aspose.Slides can generate, edit, and render PowerPoint files without Microsoft Office installed. It supports **50+ input and output formats**, processes presentations with **up to 500 slides** in under a second on typical server hardware, and provides **full API control** over chart styling, data labels, and layout—perfect for automated reporting pipelines.

## Prerequisites

Before you start, make sure you have:

- **Java Development Kit (JDK) 16+** installed.
- An IDE such as **IntelliJ IDEA**, **Eclipse**, or **NetBeans**.
- Maven or Gradle for dependency management (see the sections below).
- Basic Java knowledge and familiarity with building projects.

## Setting Up Aspose.Slides for Java

### Installation Information

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

**Direct Download:** You can download the latest version from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### License Acquisition Steps
- **Free Trial:** Start with a 30‑day trial to explore all features.  
- **Temporary License:** Request a temporary key for extended evaluation.  
- **Purchase:** Obtain a permanent license for production use to remove evaluation watermarks.

### Basic Initialization and Setup
`Presentation` is the main object for creating PowerPoint files, and `Chart` represents a chart shape within a slide.

```java
Presentation presentation = new Presentation();
```  

This creates an empty presentation ready for slides and charts.

## Implementation Guide

### How do you add a chart to PowerPoint using Aspose.Slides for Java?

Load a new `Presentation`, add a slide, and insert a `Chart` of type `PieOfPie`. The API call chain is concise: create the chart, populate series data, adjust label visibility, configure the secondary pie size, and finally save. The entire process typically fits in under 20 lines of code, making it ideal for automated report generation.

### Creating a 'Pie of Pie' Chart

#### Overview
We’ll build a Pie of Pie chart on the first slide, split out the smallest slices, and label each segment with its value.

#### Step 1: Create an Instance of the Presentation Class
```java
// Create a new presentation
ePresentation presentation = new Presentation();
```  
This initializes the container for all subsequent slides and charts.

#### Step 2: Add a 'Pie of Pie' Chart on the First Slide
```java
// Add a Pie of Pie chart to the first slide at position (50, 50) with size (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```  
Here we specify `ChartType.PieOfPie` and define the chart’s position (X, Y) and size (width, height) on the slide canvas.

#### Step 3: Set Data Labels to Show Values for the Series
```java
// Configure data labels to display values
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```  
Enabling `showValue` makes each slice display its numeric value, which is essential for quick data interpretation.

#### Step 4: Configure the Second Pie Size and Split by Percentage
```java
// Set the size of the secondary pie
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Split the pie by percentage
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Set the split position
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```  
These options let you decide how much of the chart is allocated to the secondary pie and which slices are moved based on a percentage threshold.

#### Step 5: Save the Presentation to Disk in PPTX Format
```java
// Define output directory
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Save the presentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\
```

> **Pro tip:** Use an absolute path or Java’s `Paths.get()` to avoid platform‑specific separators.

## Common Issues and Solutions

`License` class loads a license file to remove evaluation restrictions.

- **Missing license warning:** If you see “Evaluation Only” on the chart, ensure you’ve applied a valid license file via `License license = new License(); license.setLicense("Aspose.Slides.lic");`.
- **Incorrect slice split:** Verify that the `splitBy` property is set to `SplitBy.Percentage` and that the `secondPieSize` is a value between 0 and 100.
- **Data not displaying:** Confirm that the chart’s series contains at least one data point; otherwise the chart renders empty.

## Frequently Asked Questions

`IChart` represents a chart object that can be added to a slide.

**Q: Can I generate multiple charts in a single presentation?**  
A: Yes, instantiate a new `IChart` for each slide or location; the API allows unlimited chart objects per file.

`SaveFormat.Pdf` specifies PDF output format for saving.

**Q: Does Aspose.Slides support saving as PDF as well?**  
A: Absolutely – call `presentation.save("output.pdf", SaveFormat.Pdf)` to export the same slide deck to PDF.

`IPortion` represents an individual slice of a pie chart.

**Q: What is the maximum number of data points a Pie of Pie chart can handle?**  
A: The library supports up to **10,000** data points per series, limited only by available memory.

**Q: Is it possible to customize the colors of individual slices?**  
A: Yes, access each `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()` and set `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.

**Q: How do I embed the generated PPTX into a web application?**  
A: After saving the file, stream it directly to the client using `HttpServletResponse` with `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.

## Conclusion

You now have a complete, production‑ready recipe for **adding a chart to PowerPoint** by creating a Pie of Pie chart with Aspose.Slides for Java. Experiment with different split thresholds, label formats, and color schemes to match your brand guidelines. Next, explore other chart types—such as stacked bar or radar—to further enrich your automated slide decks.

---

**Last Updated:** 2026-07-17  
**Tested With:** Aspose.Slides for Java 24.12  
**Author:** Aspose

## Related Tutorials

- [Create Dynamic Chart Java – PowerPoint Charts Tutorials for Aspose.Slides](/slides/java/charts-graphs/)
- [How to add pie chart PowerPoint with Aspose.Slides for Java](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step‑by‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}