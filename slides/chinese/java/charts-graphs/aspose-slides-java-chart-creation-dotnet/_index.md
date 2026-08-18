---
date: '2026-06-03'
description: 了解如何在 .NET 演示文稿中创建图表，并使用 Aspose.Slides for Java 将图表添加到幻灯片。遵循此分步指南进行数据可视化。
keywords:
- create charts in .net
- generate chart in presentation
- add chart to slide
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  headline: Create charts in .NET using Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  name: Create charts in .NET using Aspose.Slides for Java
  steps:
  - name: Import Necessary Packages
    text: '`Presentation` and related classes are part of the `com.aspose.slides`
      namespace.'
  - name: Create a New Presentation Object
    text: Instantiate a `Presentation` object and wrap it in a try‑with‑resources
      block to guarantee disposal. *This ensures that the presentation object is properly
      disposed of after use, preventing memory leaks.*
  - name: Import Necessary Packages
    text: The `Chart` class represents a chart shape that can be placed on a slide
      and customized.
  - name: Initialize Presentation and Add Chart
    text: Create a slide, then call `addChart` with `ChartType.ClusteredColumn` and
      the desired position and size. *Here, we add a clustered column chart to the
      first slide at specified coordinates and dimensions.*
  - name: Import Necessary Packages
    text: '`IChartDataWorkbook` provides access to the underlying Excel‑like workbook
      used by charts.'
  - name: Access and Clear Data Workbook
    text: Retrieve the workbook from the chart and clear any existing data to start
      fresh. *Clearing the workbook is crucial for starting with a clean slate when
      adding new series and categories.*
  - name: Add Series and Categories
    text: Use `chart.getChartData().getSeries().add()` and `chart.getChartData().getCategories().add()`
      to define structure. *Adding series and categories allows for a more organized
      data presentation.*
  - name: Populate Series Data
    text: Assign numeric values to each cell in the workbook and apply a red fill
      for negative numbers. *This section demonstrates how to populate data and apply
      color formatting for better visualization.*
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides for Java is fully headless and works on servers without
      any graphical components.
    question: Can I generate a chart in presentation files without a GUI?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5, and .NET 6 are all supported.
    question: Which .NET versions are supported?
  - answer: Over 20 chart types are available, including column, line, pie, area,
      and radar charts.
    question: How many chart types can I add?
  - answer: Absolutely – you can set fill colors, borders, and markers for each data
      point via the `IDataPoint` API.
    question: Is it possible to style individual data points?
  - answer: No, the Aspose.Slides for Java .NET wrapper handles type conversion automatically.
    question: Do I need to convert Java objects to .NET types manually?
  type: FAQPage
title: 在 .NET 中使用 Aspose.Slides for Java 创建图表
url: /zh/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 在 .NET 中使用 Aspose.Slides for Java 创建图表

## 介绍
创建引人入胜的演示文稿通常需要集成可视化的数据表示，例如图表，以提升观众的理解和参与度。**如果您想在 .NET 中创建图表**，Aspose.Slides for Java 为您提供了强大且语言无关的 API，能够在 .NET 应用程序中无缝运行。在本教程中，您将学习如何初始化演示文稿、添加各种图表类型、管理图表数据工作簿以及格式化系列数据——包括处理负值。完成后，您将能够以编程方式在演示文件中生成图表，并仅用几行代码将图表添加到幻灯片中。

## 快速答案
- **主要目标是什么？** 使用 Aspose.Slides for Java 在 .NET 演示文稿中创建图表。  
- **需要哪个库版本？** Aspose.Slides for Java 25.4 或更高版本。  
- **是否需要许可证？** 开发阶段可使用免费试用版；生产环境需要商业许可证。  
- **可以使用 Maven 或 Gradle 吗？** 可以——两种构建系统均受支持。  
- **有哪些图表类型可用？** 簇状柱形图、折线图、饼图、条形图、面积图等。

## 如何使用 Aspose.Slides for Java 在 .NET 演示文稿中创建图表？
`Presentation` 类代表一个 PowerPoint 文件，并提供操作其幻灯片的方法。加载一个新的 `Presentation` 对象，调用 `slides.addEmptySlide()` 获取幻灯片，然后使用 `slide.getShapes().addChart()` 在指定坐标处插入所需的图表类型。图表添加后，向其数据工作簿填充系列和类别，应用任何格式（例如负值的颜色），最后将演示文稿保存为 .pptx 文件。此流程让您能够通过简洁的 API 调用 **在 .NET 中创建图表**。

## 什么是 Aspose.Slides for Java？
Aspose.Slides for Java 是一个跨平台 API，帮助开发者在没有 Microsoft Office 的情况下创建、修改和渲染 PowerPoint 文件。它支持 **50 多种输入和输出格式**，并且能够在内存使用低于 200 MB 的情况下处理包含数千张幻灯片的演示文稿。

## 为什么在 .NET 项目中使用 Aspose.Slides for Java？
Aspose.Slides for Java 运行在 Java 虚拟机上，可通过原生包装器从 .NET 调用，为 .NET 开发者提供成熟的图表引擎、高性能的大数据集处理能力，以及与现有 Java 代码的完整兼容，无需重写逻辑。

## 前置条件
在深入使用 Aspose.Slides for Java 创建图表之前，先列出您需要的准备工作：

### 必需的库和版本
- **Aspose.Slides for Java**：版本 25.4 或更高。

### 环境设置要求
- 支持 .NET 应用程序的开发环境。  
- 对 Java 编程概念有基本了解。

### 知识前置条件
- 熟悉在 .NET 应用程序上下文中创建演示文稿。  
- 了解 Java 依赖管理及其工具（Maven/Gradle）。

## 设置 Aspose.Slides for Java
要开始使用 Aspose.Slides，需在项目中将其作为依赖项引入。以下是具体做法：

### Maven
下面的 Maven 依赖片段会将 Aspose.Slides for Java 添加到您的项目中。

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
在 `build.gradle` 文件中加入以下行，即可从 Maven Central 拉取该库。

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下载
您也可以从 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下载最新版本。

#### 获取许可证的步骤
- **免费试用**：使用临时许可证探索功能。  
- **购买**：购买许可证以获得无限制的生产使用权。

#### 基本初始化和设置
`Slides` 的初始化需要设置许可证并创建 `Presentation` 实例。

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

此设置可确保资源得到有效管理。

## 实现指南
下面我们将一步步演示各项功能的实现过程。

### 初始化演示文稿
**概述:**  
创建演示文稿实例为后续所有操作奠定基础。本示例展示如何使用 Aspose.Slides 从头开始创建演示文稿。

#### 第一步：导入必要的包
`Presentation` 及相关类位于 `com.aspose.slides` 命名空间。

```java
import com.aspose.slides.Presentation;
```

#### 第二步：创建新的 Presentation 对象
实例化 `Presentation` 对象，并将其放入 try‑with‑resources 代码块中，以确保资源自动释放。

```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```

*这可确保在使用完毕后正确释放演示文稿对象，防止内存泄漏。*

### 向幻灯片添加图表
**概述:**  
在幻灯片中添加图表可以使数据可视化更具效果和吸引力。

#### 第一步：导入必要的包
`Chart` 类表示可以放置在幻灯片上的图表形状，并可进行自定义。

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### 第二步：初始化演示文稿并添加图表
创建幻灯片后，调用 `addChart`，使用 `ChartType.ClusteredColumn` 并指定所需的位置和大小。

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

*此示例在第一张幻灯片的指定坐标和尺寸处添加了一个簇状柱形图。*

### 管理图表数据工作簿
**概述:**  
高效管理图表的数据工作簿，可让您轻松操作系列和类别。

#### 第一步：导入必要的包
`IChartDataWorkbook` 提供对图表底层类 Excel 工作簿的访问。

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### 第二步：访问并清除数据工作簿
从图表中获取工作簿，并清除已有数据，以便重新开始。

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

*清空工作簿对于在添加新系列和类别时保持干净的起始状态至关重要。*

### 向图表添加系列和类别
**概述:**  
本功能展示如何通过管理系列和类别来添加有意义的数据点。

#### 第一步：添加系列和类别
使用 `chart.getChartData().getSeries().add()` 和 `chart.getChartData().getCategories().add()` 定义结构。

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

*添加系列和类别可使数据呈现更有条理。*

### 填充系列数据并进行格式化
**概述:**  
向图表填充数据点并进行外观格式化，以提升可读性，尤其是在处理负值时。

#### 第一步：填充系列数据
为工作簿中的每个单元格分配数值，并对负数应用红色填充。

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

*本节演示了如何填充数据并使用颜色格式化以获得更佳的可视化效果。*

## 常见问题及解决方案
- **LicenseNotFoundException** – 确认许可证文件路径正确且运行时可访问。  
- **NullPointerException on chart data** – 在添加新系列前务必清除工作簿，以避免残留数据导致空指针。  
- **Chart not rendering in .NET** – 请确认使用的是兼容 .NET 的 Aspose.Slides JAR，并且在 .NET 项目中正确配置了 Java 运行时。

## 常见问答

**Q: 能否在没有 GUI 的情况下生成演示文件中的图表？**  
A: 可以，Aspose.Slides for Java 完全无头，能够在没有任何图形组件的服务器上运行。

**Q: 支持哪些 .NET 版本？**  
A: 支持 .NET Framework 4.5+、.NET Core 3.1+、.NET 5 和 .NET 6。

**Q: 我可以添加多少种图表类型？**  
A: 超过 20 种图表类型可供选择，包括柱形图、折线图、饼图、面积图和雷达图等。

**Q: 能否对单个数据点进行样式设置？**  
A: 完全可以——您可以通过 `IDataPoint` API 为每个数据点设置填充颜色、边框和标记。

**Q: 是否需要手动将 Java 对象转换为 .NET 类型？**  
A: 不需要，Aspose.Slides for Java 的 .NET 包装器会自动处理类型转换。

---

**最后更新:** 2026-06-03  
**测试版本:** Aspose.Slides for Java 25.4  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [如何在 .NET 演示文稿中嵌入图表以实现有效的数据可视化](/slides/net/charts-graphs/embed-charts-net-presentations-aspose-slides/)
- [如何使用 Aspose.Slides for .NET 检索图表数据源类型 - 图表与图形](/slides/net/charts-graphs/retrieve-chart-data-source-aspose-slides-dotnet/)
- [使用 Aspose.Slides .NET 掌握图表系列创建与操作以实现有效的数据可视化](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}