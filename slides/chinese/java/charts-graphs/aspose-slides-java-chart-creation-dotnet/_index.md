---
date: '2026-02-06'
description: 学习如何在 .NET 中使用 Aspose.Slides for Java 初始化 Aspose Slides 演示文稿并自定义簇状柱形图。请按照本分步指南提升数据可视化效果。
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: 使用 Aspose Slides 初始化演示文稿：.NET 图表
url: /zh/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 在 .NET 演示文稿中使用 Aspose.Slides for Java 创建图表

## Introduction
在本教程中，您将 **initialize presentation Aspose Slides** 并学习如何在 .NET 幻灯片中嵌入动态、可定制的图表。可视化数据——如簇状柱形图——帮助观众瞬间把握趋势，而 Aspose.Slides for Java 即使在针对 .NET 环境时也能提供完整的编程控制。我们将演示如何设置库、创建新演示文稿、添加图表、填充数据以及应用格式技巧，例如为负值着色。

**What You’ll Learn**
- 如何在 .NET 项目中设置 Aspose.Slides for Java。  
- 如何 **initialize presentation Aspose Slides** 并添加图表。  
- 如何 **customize clustered column chart** 系列和类别。  
- 管理图表的数据工作簿并应用条件格式化。  

### Quick Answers
- **What is the first step?** 初始化一个 `Presentation` 对象。  
- **Which chart type is used in the example?** `ClusteredColumn`。  
- **Can I format negative values differently?** 可以，使用条件填充颜色。  
- **Do I need a license for testing?** 免费试用许可证可用于开发。  
- **Which Maven artifact is required?** `com.aspose:aspose-slides:25.4`，使用 `jdk16` 分类器。

## What is “initialize presentation Aspose Slides”?
初始化演示文稿会在内存中创建一个 PPTX 文件，您可以在保存之前对其进行操作。Aspose.Slides 抽象了文件格式，让您无需处理底层 OPC 结构即可添加幻灯片、形状和图表。

## Why customize a clustered column chart?
簇状柱形图非常适合在多个类别之间比较多个数据系列。自定义颜色、数据点和标签可以突出关键洞察——例如将负值显示为红色、正值显示为绿色——从而使幻灯片更具说服力。

## Prerequisites
- **Aspose.Slides for Java** ≥ 25.4  
- .NET 开发环境（推荐使用 Visual Studio，.NET 6+）  
- 基础 Java 知识（您将编写在 JVM 上运行的 Java 代码，并通过 JNI 或桥接层从 .NET 调用）  

### Required Libraries and Versions
- **Aspose.Slides for Java**：版本 25.4 或更高。

### Environment Setup Requirements
- 与 .NET 兼容的 Java 运行时（例如 AdoptOpenJDK 16）。  
- 用于依赖管理的 Maven 或 Gradle。

### Knowledge Prerequisites
- 熟悉在 .NET 环境中创建演示文稿。  
- 了解 Java 项目配置（Maven/Gradle）。

## Setting Up Aspose.Slides for Java
使用您偏好的构建工具将库添加到项目中。

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download
您也可以从官方发布页面下载最新的 JAR： [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)。

#### License Acquisition Steps
- **Free Trial** – 为开发生成临时许可证文件。  
- **Purchase** – 获取用于生产部署的完整许可证。

#### Basic Initialization and Setup
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
`try/finally` 块确保本机资源被释放，防止内存泄漏。

## How to initialize presentation Aspose Slides
下面我们深入具体步骤，创建全新的演示文稿并为插入图表做好准备。

### Initializing Presentation
**Overview:**  
创建演示文稿实例为后续所有操作奠定基础。

#### Step 1: Import Necessary Packages
```java
import com.aspose.slides.Presentation;
```

#### Step 2: Create a New Presentation Object
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*此操作确保在使用后正确释放演示文稿对象，防止内存泄漏。*

## How to customize clustered column chart
演示文稿准备好后，让我们添加并定制簇状柱形图。

### Adding Chart to Slide
**Overview:**  
添加图表可以让数据在幻灯片上栩栩如生。

#### Step 1: Import Necessary Packages
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Step 2: Initialize Presentation and Add Chart
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```
*此处，我们在第一张幻灯片的指定坐标和尺寸处添加了一个簇状柱形图。*

### Managing Chart Data Workbook
**Overview:**  
高效管理图表的数据工作簿，可让您轻松操作系列和类别。

#### Step 1: Import Necessary Packages
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Step 2: Access and Clear Data Workbook
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
*清空工作簿对于在添加新系列和类别时从干净的状态开始至关重要。*

### Adding Series and Categories to Chart
**Overview:**  
本步骤展示如何通过管理系列和类别来添加有意义的数据点。

#### Step 1: Add Series and Categories
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```
*添加系列和类别有助于实现更有条理的数据展示。*

### Populating Series Data and Formatting
**Overview:**  
为图表填充数据点并进行格式化，以提升可读性，尤其是在处理负值时。

#### Step 1: Populate Series Data
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*本节演示如何填充数据并应用颜色格式，以获得更佳的可视化效果。*

## Common Issues and Solutions
- **Memory leaks** – 始终像示例中那样将 `Presentation` 对象包装在 `try/finally` 块中，以确保释放。  
- **Incorrect cell coordinates** – 请记住行和列是从零开始计数的；索引不匹配会导致 `NullPointerException`。  
- **License not found** – 将许可证文件放置在应用程序的工作目录中，或通过 `License.setLicense("Aspose.Slides.Java.lic")` 明确设置路径。

## Frequently Asked Questions

**Q: Can I use this approach with .NET Core?**  
A: 可以。Aspose.Slides for Java 可在任何 JVM 上运行，您可以使用 IKVM 或 JNI 等桥接方式从 .NET Core 调用 Java 代码。

**Q: Do I need a paid license for development?**  
A: 免费试用许可证足以用于开发和测试。生产部署需要购买许可证。

**Q: How do I change the chart type after creation?**  
A: 您可以调用 `chart.getChartData().setChartType(ChartType.Pie)` 将图表类型切换为其他类型。

**Q: Is it possible to add data labels programmatically?**  
A: 可以。使用 `series.getDataPoints().get_Item(i).getLabel().setShowValue(true)` 在图表上显示数值。

**Q: What formats can I save the presentation in?**  
A: Aspose.Slides 支持 PPTX、PPT、PDF、XPS 以及 PNG、JPEG 等多种图像格式。

---

**Last Updated:** 2026-02-06  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}