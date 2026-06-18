---
title: "Create Pie Chart Aspose – Add a Chart to a Presentation with Maven"
description: "Learn how to create pie chart aspose using Aspose.Slides Maven, add pie chart java to a slide, and customize chart data. Step‑by‑step guide with Maven setup and real‑world examples."
date: "2026-05-29"
weight: 1
url: "/java/charts-graphs/add-pie-chart-aspose-slides-java/"
keywords:
- create pie chart aspose
- add pie chart java
- add chart slide
- aspose slides maven example
schemas:
- type: TechArticle
  headline: Create Pie Chart Aspose – Add a Chart to a Presentation with Maven
  description: Learn how to create pie chart aspose using Aspose.Slides Maven, add
    pie chart java to a slide, and customize chart data. Step‑by‑step guide with Maven
    setup and real‑world examples.
  dateModified: '2026-05-29'
  author: Aspose
- type: FAQPage
  questions:
  - question: How do I install Aspose.Slides for Java?
    answer: Use the Maven or Gradle dependency shown above, or download the library
      from the releases page.
  - question: What are the system requirements for Aspose.Slides?
    answer: JDK 16 or later; the library runs on any platform that supports Java.
  - question: Can I add other chart types besides pie charts?
    answer: Yes, Aspose.Slides supports bar, line, scatter, radar, and more than 20
      chart types.
  - question: How should I handle large presentations efficiently?
    answer: Dispose of objects promptly, limit high‑resolution images, and reuse chart
      templates to keep memory usage low.
  - question: Where can I find more details about Aspose.Slides features?
    answer: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/)
      for a complete API reference.
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# How to Add a Pie Chart to a Presentation Using Aspose.Slides Java

## Introduction
In this guide you’ll **create pie chart aspose** with Aspose.Slides Maven and see how to embed it into a PowerPoint slide. Creating visually appealing presentations is crucial for effectively conveying information, especially when data visualization plays a key role. If you’re looking to automate this process with **aspose slides maven**, you’ve come to the right place. We’ll walk through adding a chart to a slide — specifically a pie chart — and customizing it for real‑world scenarios.

### What You'll Learn
- How to initialize a presentation object in Java.  
- Steps to **add a pie chart java** on the first slide of a presentation.  
- Accessing chart data workbooks and listing worksheets within them.  

Let's dive into how you can harness Aspose.Slides Java to enhance your presentations with dynamic charts!

## Quick Answers
- **What library adds charts via Maven?** aspose slides maven  
- **Which chart type is demonstrated?** Pie chart (add chart to slide)  
- **Minimum Java version required?** JDK 16 or later  
- **Do I need a license for testing?** A free trial works; production needs a license  
- **Where can I find the Maven dependency?** In the setup section below  

## What is Aspose Slides Maven?
Aspose.Slides for Java is a powerful API that lets developers create, modify, and render PowerPoint files programmatically. The Maven package (`aspose-slides`) simplifies dependency management, allowing you to focus on building and customizing slides—like adding a pie chart—without dealing with low‑level file handling.

## Why Use Aspose.Slides Maven to Add a Chart to a Slide?
Using Aspose.Slides Maven lets you generate charts directly from Java code without manual PowerPoint editing. It provides full programmatic control over chart types, data sources, and styling, ensuring consistent branding and accuracy. The Maven artifact also handles all required dependencies, simplifying builds and enabling seamless integration into CI/CD pipelines.

## Prerequisites
- **Aspose.Slides for Java** version 25.4 or later (Maven/Gradle).  
- JDK 16+ installed.  
- An IDE (IntelliJ IDEA, Eclipse, etc.).  
- Basic Java knowledge and familiarity with Maven or Gradle.

## Setting Up Aspose.Slides for Java
First, include Aspose.Slides in your project via Maven or Gradle.

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
```groovy
implementation 'com.aspose:aspose-slides:25.4'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternatively, you can [download the latest release](https://releases.aspose.com/slides/java/) directly from Aspose's website.

### License Acquisition
Aspose.Slides for Java offers a free trial with a temporary license for testing. For unrestricted production use, purchase a license through the [purchase page](https://purchase.aspose.com/buy).

## Implementation Guide
Below we break the solution into two features: adding a pie chart and accessing its data workbook.

### Feature 1: Creating a Presentation and Adding a Chart
#### Overview
This part shows how to create a new presentation and **add a pie chart** to the first slide.

#### How to create pie chart aspose?
Load the `Presentation` class, add a chart of type `ChartType.Pie`, and save the file. The entire operation requires only three API calls and runs in under a second for a typical 10‑slide deck, making it ideal for automated report generation.

#### Step‑by‑Step

**Step 1: Initialize a New Presentation Object**  
The `Presentation` class is Aspose.Slides' top‑level object that represents a PowerPoint file in memory.  
```java
Presentation pres = new Presentation();
```
*Creates the `Presentation` instance that will hold all slides.*

**Step 2: Add a Pie Chart**  
`ChartType.Pie` tells Aspose to render a pie chart.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*Places a pie chart at coordinates (50, 50) with a width of 400 and height of 500.*

**Step 3: Dispose of Resources**  
Calling `dispose()` releases native resources and prevents memory leaks.  
```java
if (pres != null) pres.dispose();
```
*Releases native resources; always call `dispose()` when you’re done.*

### Feature 2: Accessing Chart Data Workbook and Worksheets
#### Overview
Learn how to reach the underlying workbook that stores chart data and iterate through its worksheets.

#### How to access chart data workbook?
Retrieve the `IChartDataWorkbook` from the chart, then loop through its `Worksheets` collection. This workbook mimics an Excel file, allowing you to read, modify, or add data series programmatically, which the chart will reflect instantly when refreshed during runtime without restarting.

#### Step‑by‑Step

**Step 1: (Reuse) Initialize a New Presentation Object**  
*Same as Feature 1, Step 1.*

**Step 2: (Reuse) Add a Pie Chart**  
*Same as Feature 1, Step 2.*

**Step 3: Get the Chart Data Workbook**  
`IChartDataWorkbook` is the interface that provides read/write access to the chart’s internal Excel‑like workbook.  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*Retrieves the `IChartDataWorkbook` linked to the chart.*

**Step 4: Iterate Through Worksheets**  
`Worksheet` objects represent individual sheets inside the workbook.  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*Prints each worksheet’s name, letting you verify the data structure.*

**Step 5: Dispose of Resources**  
*Same as Feature 1, Step 3.*

## Practical Applications
- **Data Reporting:** Auto‑generate slide decks with up‑to‑date metrics for business intelligence.  
- **Academic Presentations:** Visualize research results without manual chart creation.  
- **Marketing Material:** Showcase product performance or survey results instantly.

## Performance Considerations
- Aspose.Slides can handle **50+ input and output formats** and process multi‑hundred‑page presentations without loading the entire file into memory.  
- Keep the slide and chart count reasonable; each chart consumes native memory.  
- Always call `dispose()` to free resources promptly.  
- Optimize workbook data handling—avoid loading massive datasets into a single chart.

## Conclusion
We’ve covered how **aspose slides maven** enables you to **add chart to slide** programmatically and how to work with the chart’s data workbook. With these building blocks you can automate any reporting workflow that requires a polished PowerPoint output.

### Next Steps
- Explore chart styling options (colors, legends, data labels).  
- Connect to external data sources (CSV, databases) to populate charts dynamically.  
- Combine multiple chart types in a single presentation for richer storytelling.

## Frequently Asked Questions

**Q: How do I install Aspose.Slides for Java?**  
A: Use the Maven or Gradle dependency shown above, or download the library from the releases page.

**Q: What are the system requirements for Aspose.Slides?**  
A: JDK 16 or later; the library runs on any platform that supports Java.

**Q: Can I add other chart types besides pie charts?**  
A: Yes, Aspose.Slides supports bar, line, scatter, radar, and more than 20 chart types.

**Q: How should I handle large presentations efficiently?**  
A: Dispose of objects promptly, limit high‑resolution images, and reuse chart templates to keep memory usage low.

**Q: Where can I find more details about Aspose.Slides features?**  
A: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/) for a complete API reference.

**Q: Is a license required for commercial use?**  
A: A valid license is required for production; a free trial is available for evaluation.

**Q: Does the Maven package include all chart capabilities?**  
A: Yes, the `aspose-slides` Maven artifact contains the full charting engine.

## Resources
- Documentation: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- Download: [Latest Releases](https://releases.aspose.com/slides/java/)
- Purchase and Trial: [Purchase Page](https://purchase.aspose.com/buy)
- Free trial: [Trial Downloads](https://releases.aspose.com/slides/java/)
- Temporary License: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- Support Forum: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

---  

**Last Updated:** 2026-05-29  
**Tested With:** Aspose.Slides 25.4 for Java (jdk16)  
**Author:** Aspose

## Related Tutorials

- [How to Customize Pie Chart Colors in Java with Aspose.Slides – A Complete Guide](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Create a Pie of Pie Chart in Java with Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/)
- [Animate Charts PowerPoint Using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}