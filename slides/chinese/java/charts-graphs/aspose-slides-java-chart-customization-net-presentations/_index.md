---
date: '2026-06-08'
description: 了解如何使用 Aspose.Slides for Java 在 .NET 演示文稿中向图表添加系列并自定义堆叠柱形图。
keywords:
- add series to chart
- stacked column chart example
- populate chart data
- create empty presentation
- Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  headline: Add Series to Chart with Aspose.Slides for Java in .NET
  type: TechArticle
- description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  name: Add Series to Chart with Aspose.Slides for Java in .NET
  steps:
  - name: Create an Empty Presentation
    text: '`Presentation` is the entry point class that represents a PowerPoint file
      in memory. *We start with a clean PPTX file, which gives us a canvas for adding
      charts.*'
  - name: Add a Stacked Column Chart to the Slide
    text: '`Chart` represents a chart shape within a slide. `ChartType.StackedColumn`
      specifies a stacked column chart. *The `addChart` method creates a **stacked
      column chart** and places it at the top‑left corner of the slide.*'
  - name: Add Series to the Chart (Primary Goal)
    text: '`Series` encapsulates a single data series in a chart. *Here we **add series
      to chart** – each call creates a new data series that will appear as a separate
      column group.*'
  - name: Add Categories to the Chart
    text: '`Category` defines an X‑axis label for chart data. *Categories act as the
      X‑axis labels, giving meaning to each column.*'
  - name: Populate Series Data
    text: '`DataPoint` holds a numeric value for a series at a specific category.
      *Data points give each series its numeric values, which the chart will render
      as bar heights.*'
  - name: Set Gap Width for Chart Series Group
    text: '`SeriesGroup` controls layout properties for a group of series, such as
      gap width. *Adjusting the gap width improves readability, especially when many
      categories are present.*'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports line, pie, area, radar, bubble, and 50+ other
      chart types, all accessible through the same `addChart` method.
    question: Can I add other chart types besides stacked column?
  - answer: No, the same Java license works for all output formats, including .NET
      PPTX files.
    question: Do I need a separate license for .NET output?
  - answer: Use `series.getFormat().getFill().setFillType(FillType.Solid)` and then
      set the desired `Color` object for each series.
    question: How do I change the chart’s color palette?
  - answer: Absolutely. Call `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the numeric value on each column.
    question: Is it possible to add data labels programmatically?
  - answer: Load the file with `new Presentation("existing.pptx")`, modify the chart
      using the same API calls, and save it back to disk.
    question: What if I need to update an existing presentation?
  type: FAQPage
title: 在 .NET 中使用 Aspose.Slides for Java 向图表添加系列
url: /zh/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 掌握在 .NET 演示文稿中使用 Aspose.Slides for Java 的图表自定义

## 介绍
在数据驱动的演示文稿领域，图表是将原始数字转化为引人入胜的视觉故事的不可或缺的工具。当您需要以编程方式 **add series to chart**，尤其是在 .NET 演示文件内部时，这项任务可能会让人感到压力山大。幸运的是，**Aspose.Slides for Java** 提供了强大且语言无关的 API，使图表的创建和自定义变得直观——即使目标格式是 .NET PPTX。本指南将带您完成添加系列、构建堆积柱形图以及微调间隙宽度等视觉细节，从而生成外观精致、专业的动态数据丰富幻灯片。

## 快速答案
`Presentation` 类代表一个 PPTX 文件，`slide.getShapes().addChart(...)` 插入图表形状。使用 `chart.getChartData().getSeries().add(...)` 添加系列，`setGapWidth()` 调整间距。

- **启动演示文稿的主要类是什么？** `Presentation` – 它在内存中表示一个 PPTX 文件。  
- **哪个方法向幻灯片添加图表？** `slide.getShapes().addChart(...)` 在幻灯片上创建图表对象。  
- **如何添加新系列？** `chart.getChartData().getSeries().add(...)` 插入一个新的数据系列。  
- **可以更改柱形之间的间隙宽度吗？** 可以——调用 `chart.getChartData().getSeriesGroups().get_Item(0).setGapWidth(50)`（数值为百分比）。  
- **生产环境是否需要许可证？** 必须——有效的 Aspose.Slides for Java 许可证会解锁所有功能并移除评估水印。

## 什么是“add series to chart”？
向图表添加系列意味着插入一组新的数据点，图表会将其呈现为独立的可视元素（例如，单独的柱形组）。每个系列可以拥有自己的数值、颜色和格式，从而实现对多个数据集的并排比较。

## 为什么使用 Aspose.Slides for Java 来修改 .NET 演示文稿？
Aspose.Slides for Java 让您生成或编辑完全兼容 .NET PowerPoint 查看器的 PPTX 文件，而无需安装任何 Microsoft Office。使用 Aspose.Slides for Java，您可以获得服务器端、跨平台的解决方案来创建或更新 .NET PPTX 文件，支持 50 多种图表类型，并且能够在不将整个文档加载到内存中的情况下处理高达 500 MB 的文件。其 API 可在 Java、Kotlin、Scala 或任何 JVM 语言中使用，提供 .NET 开发者期望的相同输出。

## 先决条件
- **Aspose.Slides for Java** 库（版本 25.4 或更高）。  
- Maven、Gradle，或手动下载 JAR。  
- 基础的 Java 知识以及对 PPTX 文件结构的了解。  

## 设置 Aspose.Slides for Java
### Maven 安装
在您的 `pom.xml` 中添加以下依赖：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 安装
在您的 `build.gradle` 文件中加入此行：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 直接下载
或者，从官方发布页面获取最新的 JAR： [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)。

**许可证获取**  
先通过从 [here](https://purchase.aspose.com/temporary-license/) 下载临时许可证来获取免费试用。生产环境使用时，请购买完整许可证以解锁所有功能并移除评估水印。

## 分步实现指南
下面的每一步都附有简洁的代码片段（保持原教程不变），随后是对其作用的说明。

### 步骤 1：创建空演示文稿
`Presentation` 是表示内存中 PowerPoint 文件的入口类。  
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```  
*我们从一个空的 PPTX 文件开始，这为添加图表提供了画布。*

### 步骤 2：向幻灯片添加堆积柱形图
`Chart` 表示幻灯片中的图表形状。`ChartType.StackedColumn` 指定堆积柱形图。  
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```  
*`addChart` 方法创建一个 **stacked column chart** 并将其放置在幻灯片的左上角。*

### 步骤 3：向图表添加系列（主要目标）
`Series` 封装图表中的单个数据系列。  
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```  
*这里我们 **add series to chart** ——每次调用都会创建一个新的数据系列，显示为单独的柱形组。*

### 步骤 4：向图表添加类别
`Category` 定义图表数据的 X 轴标签。  
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```  
*类别充当 X 轴标签，为每根柱形赋予意义。*

### 步骤 5：填充系列数据
`DataPoint` 保存特定类别下系列的数值。  
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```  
*数据点为每个系列提供数值，图表会将其渲染为柱形高度。*

### 步骤 6：设置图表系列组的间隙宽度
`SeriesGroup` 控制一组系列的布局属性，例如间隙宽度。  
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```  
*调整间隙宽度可以提升可读性，尤其是在类别较多时。*

## 常见用例
- **财务报告** ——比较各业务单元的季度收入。  
- **项目仪表盘** ——显示各团队的任务完成百分比。  
- **营销分析** ——并排可视化活动绩效。  
这些场景受益于 **stacked column chart example**，因为它能够突出各类别对总体的贡献。

## 性能提示
- **在创建多个图表时复用 `Presentation` 对象**，以减少内存开销。  
- **仅保留必要的数据点**；Aspose.Slides 能处理 10,000 个点，但在约 5,000 点后渲染速度会下降。  
- **在保存后释放对象**（`presentation.dispose()`），以释放资源并避免内存泄漏。  

## 常见问题
**问：除了堆积柱形图，我还能添加其他图表类型吗？**  
答：可以，Aspose.Slides 支持折线图、饼图、面积图、雷达图、气泡图以及 50 多种其他图表类型，均可通过相同的 `addChart` 方法访问。

**问：针对 .NET 输出我需要单独的许可证吗？**  
答：不需要，同一份 Java 许可证适用于所有输出格式，包括 .NET PPTX 文件。

**问：如何更改图表的配色方案？**  
答：使用 `series.getFormat().getFill().setFillType(FillType.Solid)`，然后为每个系列设置所需的 `Color` 对象。

**问：可以编程方式添加数据标签吗？**  
答：完全可以。调用 `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` 即可在每根柱形上显示数值。

**问：如果需要更新已有的演示文稿怎么办？**  
答：使用 `new Presentation("existing.pptx")` 加载文件，使用相同的 API 调用修改图表，然后保存回磁盘。

## 结论
现在您已经掌握了如何 **add series to chart**、创建 **stacked column chart**，以及在 .NET 演示文稿中使用 Aspose.Slides for Java 微调其外观的完整端到端指南。尝试不同的图表类型、颜色和数据源，构建能够打动利益相关者并推动数据驱动决策的精彩可视化报告。

---

**Last Updated:** 2026-06-08  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [如何在 .NET 中使用 Aspose.Slides 创建基于百分比的堆积柱形图](/slides/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/)
- [使用 Aspose.Slides .NET 进行图表系列创建与操作的高级指南](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)
- [使用 Aspose.Slides .NET 清除特定图表系列的数据点](/slides/net/additional-chart-features/clear-specific-chart-series-data-points-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}