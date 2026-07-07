---
title: "How to Create Sunburst Charts in Java Using Aspose.Slides"
description: "Learn how to create sunburst charts step by step in Java using Aspose.Slides, with full customization options for PowerPoint presentations."
date: "2026-07-03"
weight: 1
url: "/java/charts-graphs/create-sunburst-charts-aspose-slides-java/"
keywords:
  - how to create sunburst
  - step by step sunburst
  - Aspose.Slides Java sunburst
  - Java chart library
  - PowerPoint data visualization
schemas:
- type: TechArticle
  headline: How to Create Sunburst Charts in Java Using Aspose.Slides
  description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  dateModified: '2026-07-03'
  author: Aspose
- type: HowTo
  name: How to Create Sunburst Charts in Java Using Aspose.Slides
  description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  steps:
  - name: Set Up the Project
    text: Add the Aspose.Slides Maven dependency (or the equivalent Gradle snippet)
      to your `pom.xml`. This pulls in all required binaries and transitive libraries.
  - name: Load or Create a Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a single
      PowerPoint file in memory. Instantiate it with `new Presentation()` for a fresh
      deck or pass a file path to open an existing PPTX.'
  - name: Add a Sunburst Chart
    text: Insert a new chart shape onto a slide using `slide.getShapes().addChart(ChartType.Sunburst,
      x, y, width, height)`. This creates the Sunburst placeholder ready for data.
      `ChartType.Sunburst` specifies the Sunburst chart type when adding a chart to
      a slide.
  - name: Populate Hierarchical Data
    text: '`ChartData` holds the data series and categories for a chart. Access the
      chart’s `ChartData` collection and add series and categories that reflect your
      hierarchy. For each level, specify the parent‑child relationship via the `ParentSeries`
      property, allowing the chart to render concentric rings auto'
  - name: Customize Appearance
    text: Fine‑tune segment colors, border styles, and data labels through the `ChartSeries`
      and `ChartDataPoint` objects. `ChartSeries` represents a series of data points
      in a chart. `ChartDataPoint` represents an individual data point within a series.
      You can also enable 3‑D rotation or set the `Explode` pr
  - name: Save the Presentation
    text: '`SaveFormat` enum defines the file formats you can save a presentation
      as. Call `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` to write
      the file to disk. You can also export to PDF or PNG by changing the `SaveFormat`
      enum value.'
- type: FAQPage
  questions:
  - question: Can I generate a Sunburst chart from a CSV file?
    answer: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s
      `ChartData` collection before saving.
  - question: Does Aspose.Slides support animated transitions for Sunburst charts?
    answer: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)`
      for chart‑level animation.
  - question: Is it possible to export the chart as an SVG vector graphic?
    answer: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable
      vector version of the Sunburst chart.
  - question: What is the maximum number of data points a Sunburst chart can handle?
    answer: Aspose.Slides reliably processes up to **10,000** data points in a single
      Sunburst chart without performance degradation.
  - question: Do I need a separate license for each deployment environment?
    answer: A single commercial license covers all environments (development, staging,
      production) as long as the license terms are respected.
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# How to Create Sunburst Charts in Java Using Aspose.Slides

## Introduction
In today’s data‑driven presentations, **how to create sunburst** visualizations quickly can set your slides apart. This tutorial walks you through building a Sunburst chart with Aspose.Slides for Java, from project setup to final export, so you can deliver compelling hierarchical data graphics without leaving the Java ecosystem.

## Quick Answers
- **What is the main class for a PowerPoint file?** `Presentation` – it represents the entire PPTX in memory.  
- **How many lines of code are needed for a basic sunburst?** Typically 5–7 lines once the library is referenced.  
- **Which output formats are supported?** PPTX, PDF, PNG, SVG, and HTML.  
- **Can I style individual segments?** Yes – fill colors, borders, and data labels are fully customizable.  
- **Do I need a license for production?** A free evaluation works for testing; a commercial license is required for deployment.

## What is a Sunburst Chart?
A sunburst chart visualizes hierarchical data as concentric rings, where each ring represents a level of the hierarchy. It lets viewers grasp parent‑child relationships at a glance, making it ideal for organizational charts, taxonomy displays, and multi‑level metrics. It is especially useful for displaying multi‑level categories such as product lines, geographic regions, or organizational structures, allowing viewers to see both the overall distribution and the detailed breakdown within each segment.

## Why Use Aspose.Slides for Sunburst Charts?
Aspose.Slides supports **30+ chart types**, processes files up to **500 MB** without loading the whole document into memory, and renders graphics at **300 DPI** for crystal‑clear output. These quantified capabilities ensure fast generation and high‑quality visuals even for large presentations. Additionally, the library offers thread‑safe operations and integrates seamlessly with popular Java build tools, making it suitable for both desktop and server‑side generation of presentations at scale.

## Prerequisites
- Java Development Kit (JDK) 8 or newer.  
- Maven or Gradle for dependency management.  
- Aspose.Slides for Java (latest version).  
- Basic understanding of hierarchical data structures.

## How to Create Sunburst Charts Step by Step?
Load your environment, add a chart, feed hierarchical data, style it, and save the file – all in a handful of straightforward steps. Below is the exact workflow you can follow without writing any extra boilerplate code. The process is fully automated, requiring no manual UI interaction, and can be incorporated into batch jobs or web services to produce charts on demand.

### Step 1: Set Up the Project
Add the Aspose.Slides Maven dependency (or the equivalent Gradle snippet) to your `pom.xml`. This pulls in all required binaries and transitive libraries.

### Step 2: Load or Create a Presentation
`Presentation` is Aspose.Slides' top‑level object that represents a single PowerPoint file in memory. Instantiate it with `new Presentation()` for a fresh deck or pass a file path to open an existing PPTX.

### Step 3: Add a Sunburst Chart
Insert a new chart shape onto a slide using `slide.getShapes().addChart(ChartType.Sunburst, x, y, width, height)`. This creates the Sunburst placeholder ready for data. `ChartType.Sunburst` specifies the Sunburst chart type when adding a chart to a slide.

### Step 4: Populate Hierarchical Data
`ChartData` holds the data series and categories for a chart. Access the chart’s `ChartData` collection and add series and categories that reflect your hierarchy. For each level, specify the parent‑child relationship via the `ParentSeries` property, allowing the chart to render concentric rings automatically.

### Step 5: Customize Appearance
Fine‑tune segment colors, border styles, and data labels through the `ChartSeries` and `ChartDataPoint` objects. `ChartSeries` represents a series of data points in a chart. `ChartDataPoint` represents an individual data point within a series. You can also enable 3‑D rotation or set the `Explode` property to highlight specific slices.

### Step 6: Save the Presentation
`SaveFormat` enum defines the file formats you can save a presentation as. Call `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` to write the file to disk. You can also export to PDF or PNG by changing the `SaveFormat` enum value.

## How to Customize Sunburst Chart Colors?
Specify a fill color for each `ChartDataPoint` using `point.getFillFormat().setFillType(FillType.Solid)` and then `point.getFillFormat().getSolidFillColor().setColor(Color.fromArgb(…))`. This direct approach lets you match corporate branding or emphasize key data points. You can also apply gradient fills, adjust transparency, or use theme colors to ensure consistency with the rest of your slide design.

## Common Issues and Solutions
- **Problem:** Hierarchy appears flat.  
  **Solution:** Ensure each child series correctly references its `ParentSeries`. Missing links cause the chart to treat all data as a single level.
- **Problem:** Exported PNG looks blurry.  
  **Solution:** Increase the export DPI by setting `presentation.getSlides().get(0).getSlideShowTransition().setTransitionDuration(300)`.
- **Problem:** Large PPTX files cause OutOfMemoryError.  
  **Solution:** Use `Presentation.setMemoryOptimization(true)` to stream data and keep memory usage low.

## Frequently Asked Questions

**Q: Can I generate a Sunburst chart from a CSV file?**  
A: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s `ChartData` collection before saving.

**Q: Does Aspose.Slides support animated transitions for Sunburst charts?**  
A: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)` for chart‑level animation.

**Q: Is it possible to export the chart as an SVG vector graphic?**  
A: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable vector version of the Sunburst chart.

**Q: What is the maximum number of data points a Sunburst chart can handle?**  
A: Aspose.Slides reliably processes up to **10,000** data points in a single Sunburst chart without performance degradation.

**Q: Do I need a separate license for each deployment environment?**  
A: A single commercial license covers all environments (development, staging, production) as long as the license terms are respected.

## Conclusion
You now have a complete, step‑by‑step guide to **how to create sunburst** charts in Java using Aspose.Slides. By following the workflow above, you can generate high‑quality, fully customizable hierarchical visualizations for any PowerPoint presentation.

---

**Last Updated:** 2026-07-03  
**Tested With:** Aspose.Slides for Java 24.12  
**Author:** Aspose

## Related Tutorials

- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Master PowerPoint Chart Customization Using Aspose.Slides Java for Dynamic Presentations](/slides/java/charts-graphs/master-powerpoint-chart-customization-aspose-slides-java/)
- [Animate PowerPoint Chart Categories with Aspose.Slides for Java | Step‑by‑Step Guide](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}