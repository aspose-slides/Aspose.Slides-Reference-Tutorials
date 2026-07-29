---
date: '2026-07-27'
description: Learn how to create doughnut chart java using Aspose.Slides – a quick
  guide to set up the library, add a customizable doughnut chart, adjust hole size,
  and save the presentation.
images:
- /java/charts-graphs/creating-doughnut-charts-java-aspose-slides/og-image.png
keywords:
- create doughnut chart java
- Aspose.Slides Java charts
- customize doughnut chart Java
lastmod: '2026-07-27'
og_description: Learn how to create doughnut chart java using Aspose.Slides – a quick
  guide to set up the library, add a customizable doughnut chart, adjust hole size,
  and save the presentation.
og_image_alt: 'Guide: create doughnut chart java with Aspose.Slides in Java'
og_title: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  headline: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  type: TechArticle
- description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  name: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  steps:
  - name: '**Budget Allocation:** Display how a budget is distributed across departments.'
    text: '**Budget Allocation:** Display how a budget is distributed across departments.'
  - name: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
    text: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
  - name: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
    text: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
  type: HowTo
- questions:
  - answer: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`
      and then specify the desired RGB color.
    question: Can I adjust the colors of my doughnut chart segments?
  - answer: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the value inside each segment.
    question: How do I add data labels to my chart?
  - answer: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many
      other formats—over 50 in total.
    question: Is it possible to save charts in formats other than PPTX?
  - answer: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)`
      to stream the file and reduce memory consumption.
    question: What should I do if I encounter an exception while loading a large presentation?
  - answer: Yes. Retrieve data from a database or REST API, update the `ChartData`
      collection, and call `chart.refresh()` before saving the presentation.
    question: Can I automate chart updates with live data sources?
  type: FAQPage
tags:
- create doughnut chart java
- Aspose.Slides
- Java charting
- presentation automation
- slides library
title: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
url: /java/charts-graphs/creating-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# How to Create Doughnut Charts in Java Using Aspose.Slides for Presentations

## Introduction
Creating visually appealing presentations is essential for effectively conveying information. **Create doughnut chart java** is a common requirement when you need to illustrate proportional data with a modern look. In this tutorial you’ll learn how to set up Aspose.Slides for Java, build a doughnut chart, customize its hole size and colors, and finally save the presentation file. By the end you’ll have a reusable pattern you can drop into any Java project that generates PowerPoint decks automatically.

**What You'll Learn:**
- Setting up Aspose.Slides for Java
- Creating and configuring doughnut charts in presentations
- Adjusting chart aesthetics such as hole size
- Saving the presentation with your new chart

Let's begin by setting up our environment!

## Quick Answers
- **Which library creates doughnut chart java?** Aspose.Slides for Java.
- **How many lines of code are needed for a basic doughnut chart?** About 8–10 lines after the presentation is instantiated.
- **Can I change the hole size?** Yes, the `setHoleSize(double)` method accepts values from 0 % to 100 %.
- **What output formats are supported?** PPTX, PDF, XPS, PNG, JPEG and several others (over 50 total).
- **Do I need a license for production?** A commercial license is required for unlimited use; a free trial works for evaluation.

## What is Aspose.Slides for Java?
**Aspose.Slides for Java** is a fully managed API that enables developers to create, modify, convert, and render PowerPoint files without Microsoft Office. It supports more than 50 file formats and can handle presentations with thousands of slides while keeping memory usage low.

## Why use doughnut charts in presentations?
Doughnut charts display part‑to‑whole relationships while freeing space in the centre for labels or images. Aspose.Slides can render doughnut charts up to **500 slides per minute** on a typical 2.5 GHz server, and it processes **multi‑hundred‑page presentations** without loading the entire file into memory, making it ideal for large‑scale reporting solutions.

## Prerequisites
Before starting, ensure you have covered these prerequisites:

### Required Libraries and Versions
To work with Aspose.Slides for Java, include it in your project via Maven or Gradle, or download directly.

#### Environment Setup Requirements
- A working Java Development Kit (JDK), preferably version 8 or higher.
- An Integrated Development Environment (IDE) like IntelliJ IDEA or Eclipse.

### Knowledge Prerequisites
Familiarity with Java and basic programming concepts is beneficial. Basic knowledge of Maven or Gradle will help streamline the setup process.

## Setting Up Aspose.Slides for Java
Incorporating Aspose.Slides into your project can be done in several ways:

**Maven:**  
Add this dependency to your `pom.xml` file:  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
Include this in your `build.gradle` file:  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download:**  
Alternatively, download the latest version from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### License Acquisition
- **Free Trial:** Start by downloading a trial version to explore Aspose.Slides features.  
- **Temporary License:** Obtain a temporary license for extended functionality without limitations.  
- **Purchase:** For ongoing use, purchasing a license is required.

Once you have the library set up and your environment ready, let's move on to implementing our doughnut chart.

## How to create a doughnut chart in Java?
Load a new `Presentation` object, add a doughnut chart to a slide, set the hole size, and save the file – all in a handful of straightforward API calls. This approach gives you full control over chart data, appearance, and export format, and it works without needing Microsoft PowerPoint installed on the server.

### Initialize Presentation Object
The `Presentation` class is Aspose.Slides' top‑level object that represents a PowerPoint file in memory.  
```java
// Create an instance of Presentation class to represent a PPTX document
Presentation presentation = new Presentation();
```  
This step creates an empty presentation where you can add slides, shapes, and charts.

### Add Doughnut Chart to Slide
`ISlide` is the interface for a single slide; you can retrieve the first slide or add a new one.  
```java
// Access the first slide in the presentation
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Position at (50, 50) with size 400x400
```  
The method `addChart` creates a doughnut chart; the parameters define its position (X, Y) and size (width, height) on the slide.

### Configure Doughnut Hole Size
`Chart` exposes `setHoleSize(double)` to control the inner radius as a percentage of the chart radius.  
```java
// Set the hole size for the doughnut chart to 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```  
Setting the hole size to 90 % makes the chart appear almost as a full circle, which is useful when you want to emphasize the outer segments.

### Save Presentation
`presentation.save(String, SaveFormat)` writes the file to disk in the chosen format.  
```java
// Save the presentation to disk in PPTX format at the specified directory
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```  
The example saves the result as `DoughnutHoleSize_out.pptx`, but you could also choose PDF, PNG, or any of the 50+ supported formats.

### Clean Up Resources
Calling `presentation.dispose()` releases native resources and prevents memory leaks, especially important in long‑running server applications.  
```java
// Dispose of the presentation object to free resources
if (presentation != null) presentation.dispose();
```  

## Practical Applications
Doughnut charts are versatile. Here are some scenarios where they shine:
1. **Budget Allocation:** Display how a budget is distributed across departments.  
2. **Survey Results:** Visualize responses to questions with multiple‑choice answers.  
3. **Website Traffic Sources:** Show the percentage of traffic coming from different channels (organic, paid, referral, etc.).

## Performance Considerations
When working with Aspose.Slides, consider these tips for optimal performance:
- Dispose of `Presentation` objects as soon as you’re done to free native memory.  
- Use streams (`FileInputStream`, `ByteArrayOutputStream`) for large data sets to avoid loading entire files into RAM.  
- Reuse chart objects when generating many slides in a loop to reduce object‑creation overhead.

## Common Issues and Solutions
- **Error while saving:** Verify the output directory exists and the application has write permissions.  
- **Missing chart data:** Ensure you populate the chart’s `ChartData` collection before calling `setHoleSize`.  
- **Memory spikes:** For presentations with thousands of slides, enable `Presentation.setSlideSize` to a smaller size and dispose of intermediate slides promptly.

## Frequently Asked Questions

**Q: Can I adjust the colors of my doughnut chart segments?**  
A: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)` and then specify the desired RGB color.

**Q: How do I add data labels to my chart?**  
A: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)` to display the value inside each segment.

**Q: Is it possible to save charts in formats other than PPTX?**  
A: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many other formats—over 50 in total.

**Q: What should I do if I encounter an exception while loading a large presentation?**  
A: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)` to stream the file and reduce memory consumption.

**Q: Can I automate chart updates with live data sources?**  
A: Yes. Retrieve data from a database or REST API, update the `ChartData` collection, and call `chart.refresh()` before saving the presentation.

## Resources
- **Documentation:** Explore detailed API references at [Aspose.Slides for Java](https://reference.aspose.com/slides/java/).  
- **Download:** Get the latest library version from [Aspose.Slides releases](https://releases.aspose.com/slides/java/).  
- **Purchase:** For full access, purchase a license at [Aspose Purchase](https://purchase.aspose.com/buy).  
- **Free Trial:** Test drive Aspose.Slides with a free trial available on their download page.  
- **Temporary License:** Obtain a temporary license for extended testing without limitations.  
- **Support:** Have questions? Visit the [Aspose Forum](https://forum.aspose.com/c/slides/11) for assistance.

---

**Last Updated:** 2026-07-27  
**Tested With:** Aspose.Slides for Java 24.12  
**Author:** Aspose

## Related Tutorials

- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [How to Create Chart in Java with Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}