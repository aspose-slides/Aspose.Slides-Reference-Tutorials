---
"description": "学习如何使用 Aspose.Slides for Java 在 Java Slides 中自定义图表。探索第二个绘图选项并增强您的演示文稿。"
"linktitle": "Java 幻灯片中的图表第二个绘图选项"
"second_title": "Aspose.Slides Java PowerPoint 处理 API"
"title": "Java 幻灯片中的图表第二个绘图选项"
"url": "/zh/java/chart-creation/second-plot-options-charts-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 幻灯片中的图表第二个绘图选项


## Java 幻灯片中图表的第二个绘图选项简介

在本教程中，我们将探索如何使用 Aspose.Slides for Java 为图表添加第二个绘图选项。第二个绘图选项允许您自定义图表的外观和行为，尤其是在饼图中。我们将提供分步说明和源代码示例来实现此目的。 

## 先决条件
在开始之前，请确保您已经在 Java 项目中安装并设置了 Aspose.Slides for Java。

## 步骤 1：创建演示文稿
让我们从创建一个新的演示文稿开始：

```java
// 文档目录的路径。
String dataDir = "Your Document Directory";
// 创建 Presentation 类的实例
Presentation presentation = new Presentation();
```

## 步骤 2：向幻灯片添加图表
接下来，我们将在幻灯片中添加一个图表。在本例中，我们将创建一个饼图中的饼图：

```java
// 在幻灯片上添加图表
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## 步骤 3：自定义图表属性
现在，让我们为图表设置不同的属性，包括第二个绘图选项：

```java
// 显示第一个系列的数据标签
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// 设置第二个饼图的大小（百分比）
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// 按百分比分割饼图
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// 设置分割的位置
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## 步骤 4：保存演示文稿
最后，保存带有图表和第二个绘图选项的演示文稿：

```java
// 将演示文稿写入磁盘
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## 第二个绘图选项的完整源代码

```java
// 文档目录的路径。
String dataDir = "Your Document Directory";
// 创建 Presentation 类的实例
Presentation presentation = new Presentation();
// 在幻灯片上添加图表
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// 设置不同的属性
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// 将演示文稿写入磁盘
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## 结论

在本教程中，我们学习了如何使用 Aspose.Slides for Java 为 Java Slides 中的图表添加第二个绘图选项。您可以自定义各种属性来增强图表的外观和功能，使您的演示文稿更具信息量和视觉吸引力。

## 常见问题解答

### 如何更改饼图中第二个饼的大小？

要更改饼图中第二个饼的大小，请使用 `setSecondPieSize` 方法如上面的代码示例所示。调整值以百分比指定大小。

### 什么 `PieSplitBy` 饼图中的饼状图如何控制？

这 `PieSplitBy` 属性控制饼图的分割方式。您可以将其设置为 `PieSplitType.ByPercentage` 或者 `PieSplitType.ByValue` 分别按百分比或特定值拆分图表。

### 如何设置饼图中分割的位置？

您可以使用 `setPieSplitPosition` 方法。调整该值以指定所需的位置。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}