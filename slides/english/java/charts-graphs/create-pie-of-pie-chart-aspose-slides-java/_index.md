---
title: "Create a Pie of Pie Chart in Java with Aspose.Slides&#58; A Comprehensive Guide"
description: "Learn how to create and customize a Pie of Pie chart using Aspose.Slides for Java. This guide covers setup, implementation, and practical applications."
date: "2025-04-17"
weight: 1
url: "/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/"
keywords:
- Aspose.Aspose.Slides
- Java
- Document Processing

---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}
# Create a Pie of Pie Chart in Java with Aspose.Slides: A Comprehensive Guide

## Charts & Graphs

### Introduction

In data visualization, pie charts are an intuitive way to represent proportions within a dataset. However, when dealing with complex datasets where some segments are significantly smaller than others, traditional pie charts can become cluttered and hard to interpret. Pie of Pie charts address this by splitting off small slices into a secondary chart, enhancing readability.

In this tutorial, you'll learn how to create and manipulate a Pie of Pie Chart using Aspose.Slides for Java. You’ll cover setting up your environment, creating the chart, customizing properties like data labels and split positions, and saving your presentation in PPTX format. By the end, you’ll have mastered these features with practical applications and performance tips.

**What You'll Learn:**
- Setting up Aspose.Slides for Java
- Creating a Pie of Pie Chart
- Customizing chart properties such as data labels and split configurations
- Saving your presentation to disk

Ready to get started? Let's look at the prerequisites first!

## Prerequisites

Before creating our Pie of Pie Chart, ensure you have:

### Required Libraries, Versions, and Dependencies:
- **Aspose.Slides for Java**: Essential for managing PowerPoint presentations programmatically.

### Environment Setup Requirements:
- A Java Development Kit (JDK) installed on your machine. We recommend using JDK 16 or later.
- An Integrated Development Environment (IDE) like IntelliJ IDEA, Eclipse, or NetBeans.

### Knowledge Prerequisites:
- Basic understanding of Java programming
- Familiarity with Maven or Gradle for dependency management

## Setting Up Aspose.Slides for Java

### Installation Information:

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

**Direct Download**: You can download the latest version from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### License Acquisition Steps:
- **Free Trial**: Start with a 30-day trial to explore all features.
- **Temporary License**: Request a temporary license for extended evaluation.
- **Purchase**: Consider purchasing a license if Aspose.Slides meets your needs.

### Basic Initialization and Setup

Once you have the library set up in your project, initialize it by creating an instance of the `Presentation` class:

```java
Presentation presentation = new Presentation();
```

This sets the stage for adding various charts to your slides. Next, let's move on to implementing our Pie of Pie Chart.

## Implementation Guide

### Creating a 'Pie of Pie' Chart

#### Overview
We'll start by creating an instance of a `Presentation` and add a Pie of Pie chart on the first slide. This chart will effectively visualize data by separating smaller segments into a secondary pie, enhancing readability.

#### Step 1: Create an Instance of the Presentation Class
```java
// Create a new presentation
ePresentation presentation = new Presentation();
```
This code initializes your presentation where we'll add our charts.

#### Step 2: Add a 'Pie of Pie' Chart on the First Slide
```java
// Add a Pie of Pie chart to the first slide at position (50, 50) with size (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```
Here we specify the type of chart (`PieOfPie`) and its position and dimensions on the slide.

#### Step 3: Set Data Labels to Show Values for the Series
```java
// Configure data labels to display values
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```
This step ensures that each segment of our pie chart displays its corresponding value, aiding in quick data interpretation.

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
These configurations allow you to customize how your chart splits and displays smaller segments, improving clarity for viewers.

#### Step 5: Save the Presentation to Disk in PPTX Format
```java
// Define output directory
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Save the presentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\
{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}