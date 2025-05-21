---
title: "How to Create Doughnut Charts in Java Using Aspose.Slides for Presentations"
description: "Learn how to create and customize doughnut charts in Java presentations with Aspose.Slides, including setting up your environment and adjusting chart aesthetics."
date: "2025-04-17"
weight: 1
url: "/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/"
keywords:
- create doughnut charts Java
- Aspose.Slides Java charts
- customize doughnut charts Java

---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# How to Create Doughnut Charts in Java Using Aspose.Slides for Presentations

## Introduction
Creating visually appealing presentations is essential for effectively conveying information. Charts are crucial elements that enhance the understanding of data distributions. This tutorial guides you through creating customizable doughnut charts using Aspose.Slides for Java, enabling effortless chart generation with extensive customization options like hole size and positioning.

**What You'll Learn:**
- Setting up Aspose.Slides for Java
- Creating and configuring doughnut charts in presentations
- Adjusting chart aesthetics such as hole size
- Saving the presentation with your new chart

Let's begin by setting up our environment!

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
- **Free Trial**: Start by downloading a trial version to explore Aspose.Slides features.
- **Temporary License**: Obtain a temporary license for extended functionality without limitations.
- **Purchase**: For ongoing use, purchasing a license is required.

Once you have the library set up and your environment ready, let's move on to implementing our doughnut chart.

## Implementation Guide

### Creating a Doughnut Chart
Creating a presentation with a customized doughnut chart using Aspose.Slides involves several steps. We'll break them down for clarity:

#### Initialize Presentation Object
Start by creating an instance of the `Presentation` class, representing your PowerPoint document.
```java
// Create an instance of Presentation class to represent a PPTX document
Presentation presentation = new Presentation();
```
This step initializes your presentation where you can add slides and charts.

#### Add Doughnut Chart to Slide
Access the first slide (or create one if necessary) and add a doughnut chart:
```java
// Access the first slide in the presentation
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Position at (50, 50) with size 400x400
```
This code snippet adds a doughnut chart to the first slide. The parameters define its position and dimensions on the slide.

#### Configure Doughnut Hole Size
To give your doughnut chart a unique look, adjust the hole size:
```java
// Set the hole size for the doughnut chart to 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```
Here, we're setting the hole size to 90%, making it almost a full circle. Adjust this value based on your design needs.

#### Save Presentation
After configuring your chart, save the presentation:
```java
// Save the presentation to disk in PPTX format at the specified directory
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```
This line writes your changes to a file named `DoughnutHoleSize_out.pptx` in your designated directory.

#### Clean Up Resources
Finally, ensure you dispose of the presentation object:
```java
// Dispose of the presentation object to free resources
if (presentation != null) presentation.dispose();
```
This step is crucial for resource management and avoiding memory leaks.

### Practical Applications
Doughnut charts are versatile. Here are some scenarios where they shine:
1. **Budget Allocation**: Display how a budget is distributed across departments.
2. **Survey Results**: Visualize responses to questions with multiple-choice answers.
3. **Website Traffic Sources**: Show the percentage of traffic coming from different sources.

### Performance Considerations
When working with Aspose.Slides, consider these tips for optimal performance:
- Manage memory by disposing of objects when they're no longer needed.
- Use streams for large data sets to minimize memory usage.
- Optimize your code by reusing instances where possible.

## Conclusion
Congratulations! You've learned how to create and customize a doughnut chart using Aspose.Slides for Java. This tutorial covered setting up the library, adding charts to presentations, and tweaking their appearance.

To continue exploring Aspose.Slides' capabilities, consider experimenting with other chart types or diving deeper into presentation automation features.

**Next Steps:**
- Experiment with different chart configurations.
- Explore additional Aspose.Slides documentation for more advanced features.

Ready to create your own doughnut charts? Try implementing this solution in your next project!

## FAQ Section
1. **Can I adjust the colors of my doughnut chart segments?**
   Yes, you can customize segment colors using `chart.getChartData().getSeries(i).getDataPointsForBarChart().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid);` to set a solid fill type and specify your desired color.

2. **How do I add data labels to my chart?**
   Use `chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category"));` and similar methods to add data points and labels programmatically.

3. **Is it possible to save charts in formats other than PPTX?**
   Absolutely! Aspose.Slides supports various output formats such as PDF, XPS, and image formats like PNG or JPEG.

4. **What if I encounter an error while saving the presentation?**
   Ensure your directory path is correct and that you have write permissions for the specified location. Check if the version of Aspose.Slides you're using supports the file format you're trying to save in.

5. **Can I automate chart updates with live data sources?**
   Yes, by integrating APIs or databases into your Java application, you can dynamically update chart data and refresh presentations as needed.

## Resources
- **Documentation**: Explore detailed API references at [Aspose.Slides for Java](https://reference.aspose.com/slides/java/).
- **Download**: Get the latest library version from [Aspose.Slides releases](https://releases.aspose.com/slides/java/).
- **Purchase**: For full access, purchase a license at [Aspose Purchase](https://purchase.aspose.com/buy).
- **Free Trial**: Test drive Aspose.Slides with a free trial available on their download page.
- **Temporary License**: Obtain a temporary license for extended testing without limitations.
- **Support**: Have questions? Visit the [Aspose Forum](https://forum.aspose.com/c/slides/11) for assistance.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}