---
title: 从 Java 幻灯片中的图表绘图区域获取宽度和高度
linktitle: 从 Java 幻灯片中的图表绘图区域获取宽度和高度
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides for Java 在 Java Slides 中检索图表绘图区域尺寸。增强您的 PowerPoint 自动化技能。
type: docs
weight: 21
url: /zh/java/data-manipulation/get-width-height-chart-plot-area-java-slides/
---

## 介绍

图表是在 PowerPoint 演示文稿中可视化数据的有效方式。有时，您可能出于各种原因需要了解图表绘图区域的尺寸，例如调整图表中元素的大小或重新定位。本指南将演示如何使用 Java 和 Aspose.Slides for Java 获取绘图区域的宽度和高度。

## 先决条件

在我们深入研究代码之前，请确保您已在 Java 项目中安装并设置了 Aspose.Slides for Java 库。您可以从 Aspose 网站下载该库[这里](https://releases.aspose.com/slides/java/).

## 第 1 步：设置环境

确保您已将 Aspose.Slides for Java 库添加到您的 Java 项目中。您可以通过将库包含在项目的依赖项中或手动添加 JAR 文件来完成此操作。

## 第 2 步：创建 PowerPoint 演示文稿

我们首先创建一个 PowerPoint 演示文稿并向其中添加一张幻灯片。这将作为我们图表的容器。

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

代替`"Your Document Directory"`与您的文档目录的路径。

## 第 3 步：添加图表

现在，让我们向幻灯片添加聚集柱形图。我们还将验证图表布局。

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

此代码在位置 (100, 100) 处创建尺寸为 (500, 350) 的聚集柱形图。

## 第 4 步：获取绘图区域尺寸

要检索图表绘图区域的宽度和高度，我们可以使用以下代码：

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

现在，变量`x`, `y`, `w`， 和`h`包含绘图区域的 X 坐标、Y 坐标、宽度和高度的相应值。

## 第 5 步：保存演示文稿

最后，保存带有图表的演示文稿。

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

确保更换`"Chart_out.pptx"`与您想要的输出文件名。

## 从 Java 幻灯片中的图表绘图区域获取宽度和高度的完整源代码

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	//保存带有图表的演示文稿
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 结论

在本文中，我们介绍了如何使用 Aspose.Slides for Java API 获取 Java Slides 中图表绘图区域的宽度和高度。当您需要动态调整 PowerPoint 演示文稿中的图表布局时，此信息可能非常有价值。

## 常见问题解答

### 如何将图表类型更改为除簇状柱形图之外的其他类型？

您可以通过替换来更改图表类型`ChartType.ClusteredColumn`具有所需的图表类型枚举，例如`ChartType.Line`或者`ChartType.Pie`.

### 我可以修改图表的其他属性吗？

是的，您可以使用 Aspose.Slides for Java API 修改图表的各种属性，例如数据、标签和格式。请参阅文档了解更多详细信息。

### Aspose.Slides for Java 适合专业 PowerPoint 自动化吗？

是的，Aspose.Slides for Java 是一个功能强大的库，用于在 Java 应用程序中自动执行 PowerPoint 任务。它提供了用于处理演示文稿、幻灯片、形状、图表等的全面功能。

### 我如何了解有关 Aspose.Slides for Java 的更多信息？

您可以在 Aspose.Slides for Java 文档页面上找到大量文档和示例[这里](https://reference.aspose.com/slides/java/).
