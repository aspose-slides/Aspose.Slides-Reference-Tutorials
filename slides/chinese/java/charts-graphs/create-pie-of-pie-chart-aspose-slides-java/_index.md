---
date: '2026-07-17'
description: 了解如何通过使用 Aspose.Slides for Java 创建 Pie of Pie 图表来向 PowerPoint 添加图表。内容包括环境设置、代码示例、定制以及保存为
  PPTX。
keywords:
- add chart to powerpoint
- how to create pie
- create pie of pie
- save presentation as pptx
- customize pie chart labels
lastmod: '2026-07-17'
og_description: 使用 Aspose.Slides for Java 向 PowerPoint 添加图表。本指南展示了如何在几分钟内创建、定制并将 Pie
  of Pie 图表保存为 PPTX。
og_image_alt: 'Guide: add chart to PowerPoint using Aspose.Slides Java'
og_title: 向 PowerPoint 添加图表 – 使用 Java 创建 Pie of Pie 图表
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
title: 向 PowerPoint 添加图表 – 使用 Aspose.Slides for Java 创建 Pie of Pie 图表
url: /zh/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 在 PowerPoint 中添加图表 – 使用 Aspose.Slides for Java 创建饼形图中的饼图

## 图表与图形

### 简介

在现代数据驱动的演示文稿中，**向 PowerPoint 添加图表**通常是将原始数字转化为可视化洞察的最快方式。普通的饼图适用于少量类别，但当某些切片非常小的时候，它们会变得难以阅读。*饼形图中的饼图*通过将这些小切片提取到次级饼图中，保持主图简洁并使细节易于查看，从而解决了此问题。

在本教程中，您将学习如何通过使用 Aspose.Slides for Java 创建饼形图中的饼图来**向 PowerPoint 添加图表**。我们将逐步演示环境搭建、图表创建、标签自定义、拆分位置调节，最后将演示文稿保存为 PPTX 文件。完成后，您即可在任何幻灯片中嵌入复杂的图表。

## 快速答疑
在 Aspose.Slides 中，`Presentation` 表示 PPTX 文件，`ChartType.PieOfPie` 选择饼形图中的饼图，`setShowValue(true)` 在标签上显示数值，`save` 将文件写入磁盘。

- **PowerPoint 操作的主要类是什么？** `Presentation` – 它在内存中表示整个 PPTX 文件。  
- **哪种图表类型会为小切片创建次级饼图？** `ChartType.PieOfPie`。  
- **如何在每个切片上显示数值？** 设置 `chart.getChartData().getSeries().get_Item(0).getLabels().setShowValue(true)`。  
- **可以直接将文件保存为 PPTX 吗？** 可以 – 调用 `presentation.save("output.pptx", SaveFormat.Pptx)`。  
- **开发时是否需要许可证？** 免费的 30 天试用可用于测试；永久许可证可去除评估水印。

## 什么是饼形图中的饼图？
**饼形图中的饼图**是一种两级饼形可视化，它将一个或多个小切片隔离到单独的、关联的饼图中，使其更易阅读。Aspose.Slides 开箱即支持此图表类型，允许您控制拆分大小、位置和标签格式。

## 为什么使用 Aspose.Slides 向 PowerPoint 添加图表？
Aspose.Slides 能够在未安装 Microsoft Office 的情况下生成、编辑和渲染 PowerPoint 文件。它支持 **50 多种输入和输出格式**，在普通服务器硬件上可在不到一秒的时间内处理 **最多 500 张幻灯片** 的演示文稿，并提供对图表样式、数据标签和布局的 **完整 API 控制**——非常适合自动化报告流水线。

## 先决条件

在开始之前，请确保您已具备以下条件：

- **Java Development Kit (JDK) 16+** 已安装。  
- 如 **IntelliJ IDEA**、**Eclipse** 或 **NetBeans** 等 IDE。  
- 用于依赖管理的 Maven 或 Gradle（请参见下文）。  
- 基本的 Java 知识以及项目构建经验。

## 设置 Aspose.Slides for Java

### 安装信息

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

**直接下载：** 您可以从 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 下载最新版本。

### 许可证获取步骤
- **免费试用：** 开始 30 天试用以探索所有功能。  
- **临时许可证：** 申请临时密钥以延长评估时间。  
- **购买：** 获取永久许可证用于生产，以去除评估水印。

### 基本初始化和设置
`Presentation` 是创建 PowerPoint 文件的主要对象，`Chart` 表示幻灯片中的图表形状。

```java
Presentation presentation = new Presentation();
```  

这将创建一个空的演示文稿，准备添加幻灯片和图表。

## 实现指南

### 如何使用 Aspose.Slides for Java 向 PowerPoint 添加图表？

加载一个新的 `Presentation`，添加幻灯片，并插入类型为 `PieOfPie` 的 `Chart`。API 调用链简洁：创建图表、填充系列数据、调整标签可见性、配置次级饼图大小，最后保存。整个过程通常不超过 20 行代码，非常适合自动化报告生成。

### 创建‘饼形图中的饼图’

#### 概述
我们将在第一张幻灯片上构建饼形图中的饼图，拆分出最小的切片，并为每个部分标注其数值。

#### 步骤 1：创建 Presentation 类的实例
```java
// Create a new presentation
ePresentation presentation = new Presentation();
```  
这将初始化用于后续所有幻灯片和图表的容器。

#### 步骤 2：在第一张幻灯片上添加‘饼形图中的饼图’
```java
// Add a Pie of Pie chart to the first slide at position (50, 50) with size (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```  
这里我们指定 `ChartType.PieOfPie` 并在幻灯片画布上定义图表的位置 (X, Y) 和大小 (宽度, 高度)。

#### 步骤 3：为系列设置显示数值的数据标签
```java
// Configure data labels to display values
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```  
启用 `showValue` 可让每个切片显示其数值，这对快速数据解释至关重要。

#### 步骤 4：配置次级饼图大小并按百分比拆分
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
这些选项让您决定图表中分配给次级饼图的比例，以及根据百分比阈值移动哪些切片。

#### 步骤 5：以 PPTX 格式将演示文稿保存到磁盘
```java
// Define output directory
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Save the presentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\
```

> **专业提示：** 使用绝对路径或 Java 的 `Paths.get()` 以避免平台特定的分隔符。

## 常见问题与解决方案

`License` 类加载许可证文件以去除评估限制。

- **缺少许可证警告：** 如果在图表上看到 “Evaluation Only”，请确保通过 `License license = new License(); license.setLicense("Aspose.Slides.lic");` 应用了有效的许可证文件。  
- **切片拆分不正确：** 请确认 `splitBy` 属性设置为 `SplitBy.Percentage`，且 `secondPieSize` 的值在 0 到 100 之间。  
- **数据未显示：** 确认图表的系列至少包含一个数据点；否则图表将为空。

## 常见问答

`IChart` 表示可以添加到幻灯片的图表对象。

**问：我可以在同一个演示文稿中生成多个图表吗？**  
答：可以，为每个幻灯片或位置实例化新的 `IChart`；API 允许每个文件中拥有无限数量的图表对象。

`SaveFormat.Pdf` 指定保存为 PDF 的输出格式。

**问：Aspose.Slides 是否也支持保存为 PDF？**  
答：当然可以 – 调用 `presentation.save("output.pdf", SaveFormat.Pdf)` 将相同的幻灯片导出为 PDF。

`IPortion` 表示饼图的单个切片。

**问：饼形图中的饼图最多能处理多少数据点？**  
答：该库每个系列支持最多 **10,000** 个数据点，仅受可用内存限制。

**问：可以自定义单个切片的颜色吗？**  
答：可以，通过 `chart.getChartData().getSeries().get_Item(0).getPortions()` 访问每个 `IPortion`，并使用 `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))` 设置颜色。

**问：如何将生成的 PPTX 嵌入到 Web 应用程序中？**  
答：保存文件后，使用 `HttpServletResponse` 并设置 `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation` 将其直接流式传输给客户端。

## 结论

现在，您已经掌握了使用 Aspose.Slides for Java 创建饼形图中的饼图来**向 PowerPoint 添加图表**的完整、可投入生产的方案。尝试不同的拆分阈值、标签格式和配色方案，以符合您的品牌指南。接下来，探索其他图表类型——如堆叠条形图或雷达图——进一步丰富您的自动化幻灯片。

---

**Last Updated:** 2026-07-17  
**Tested With:** Aspose.Slides for Java 24.12  
**Author:** Aspose

## 相关教程

- [创建动态图表 Java – Aspose.Slides PowerPoint 图表教程](/slides/java/charts-graphs/)
- [如何使用 Aspose.Slides for Java 在 PowerPoint 中添加饼图](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [如何使用 Aspose.Slides for Java 向 PowerPoint 添加图表：一步步指南](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}