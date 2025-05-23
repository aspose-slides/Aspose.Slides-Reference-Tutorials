---
"date": "2025-04-17"
"description": "学习如何使用 Aspose.Slides for Java 创建和自定义饼图。本指南涵盖设置、实现和实际应用。"
"title": "使用 Aspose.Slides 在 Java 中创建饼状图的综合指南"
"url": "/zh/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 使用 Aspose.Slides 在 Java 中创建饼图：综合指南

## 图表和图形

### 介绍

在数据可视化中，饼图是一种直观的表示数据集比例的方式。然而，当处理某些部分明显小于其他部分的复杂数据集时，传统的饼图可能会变得杂乱无章，难以解读。饼中饼图通过将小块拆分成辅助图表来解决这个问题，从而增强了可读性。

在本教程中，您将学习如何使用 Aspose.Slides for Java 创建和操作饼图。您将学习如何设置环境、创建图表、自定义数据标签和拆分位置等属性，以及如何将演示文稿保存为 PPTX 格式。最后，您将通过实际应用和性能技巧掌握这些功能。

**您将学到什么：**
- 设置 Aspose.Slides for Java
- 创建饼状图
- 自定义图表属性，例如数据标签和拆分配置
- 将演示文稿保存到磁盘

准备好开始了吗？我们先来看看先决条件！

## 先决条件

在创建饼图之前，请确保您已：

### 所需的库、版本和依赖项：
- **Aspose.Slides for Java**：对于以编程方式管理 PowerPoint 演示文稿至关重要。

### 环境设置要求：
- 您的计算机上已安装 Java 开发工具包 (JDK)。我们建议使用 JDK 16 或更高版本。
- 集成开发环境 (IDE)，如 IntelliJ IDEA、Eclipse 或 NetBeans。

### 知识前提：
- 对 Java 编程有基本的了解
- 熟悉 Maven 或 Gradle 的依赖管理

## 设置 Aspose.Slides for Java

### 安装信息：

**Maven：**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle：**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**直接下载**：您可以从 [Aspose.Slides for Java 发布](https://releases。aspose.com/slides/java/).

### 许可证获取步骤：
- **免费试用**：从 30 天试用开始探索所有功能。
- **临时执照**：申请临时许可证以进行延长评估。
- **购买**：如果 Aspose.Slides 满足您的需求，请考虑购买许可证。

### 基本初始化和设置

在项目中设置库后，通过创建 `Presentation` 班级：

```java
Presentation presentation = new Presentation();
```

这为在幻灯片中添加各种图表奠定了基础。接下来，让我们继续实现饼图中的饼图。

## 实施指南

### 创建“饼状图”

#### 概述
我们首先创建一个 `Presentation` 并在第一张幻灯片上添加一个饼状图。此图表通过将较小的部分分成一个饼状图，有效地可视化数据，从而增强可读性。

#### 步骤 1：创建表示类的实例
```java
// 创建新演示文稿
ePresentation presentation = new Presentation();
```
此代码初始化您的演示文稿，我们将在其中添加图表。

#### 第 2 步：在第一张幻灯片上添加“饼图”
```java
// 在第一张幻灯片中，在位置 (50, 50) 处添加一个饼状图，大小为 (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```
这里我们指定图表的类型（`PieOfPie`) 及其在幻灯片上的位置和尺寸。

#### 步骤 3：设置数据标签以显示系列的值
```java
// 配置数据标签以显示值
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```
此步骤可确保饼图的每个部分都显示其对应的值，有助于快速解释数据。

#### 步骤 4：配置第二个饼图的大小并按百分比分割
```java
// 设置次级饼图的大小
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// 按百分比分割饼图
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// 设置分割位置
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```
这些配置允许您自定义图表如何分割和显示较小的部分，从而提高查看者的清晰度。

#### 步骤 5：将演示文稿以 PPTX 格式保存到磁盘
```java
// 定义输出目录
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// 保存演示文稿\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}