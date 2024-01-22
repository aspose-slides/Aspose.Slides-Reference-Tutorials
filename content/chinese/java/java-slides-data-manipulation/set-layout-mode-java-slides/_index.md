---
title: 在 Java 幻灯片中设置布局模式
linktitle: 在 Java 幻灯片中设置布局模式
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides 设置 Java 幻灯片的布局模式。在本分步指南中使用源代码自定义图表位置和大小。
type: docs
weight: 23
url: /zh/java/data-manipulation/set-layout-mode-java-slides/
---

## Java幻灯片中设置布局模式简介

在本教程中，我们将学习如何使用 Aspose.Slides for Java 在 Java 幻灯片中设置图表的布局模式。布局模式决定幻灯片中图表的位置和大小。

## 先决条件

在开始之前，请确保您已在 Java 项目中安装并设置了 Aspose.Slides for Java 库。您可以从以下位置下载该库[这里](https://releases.aspose.com/slides/java/).

## 第 1 步：创建演示文稿

首先，我们需要创建一个新的演示文稿。

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## 第 2 步：添加幻灯片和图表

接下来，我们将向其添加幻灯片和图表。在此示例中，我们将创建一个聚集柱形图。

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## 第 3 步：设置图表布局

现在，让我们设置图表的布局。我们将使用以下命令调整幻灯片中图表的位置和大小`setX`, `setY`, `setWidth`, `setHeight`方法。此外，我们将设置`LayoutTargetType`来确定布局模式。

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

在此示例中，我们将图表的布局目标类型设置为“内部”，这意味着它将相对于幻灯片的内部区域进行定位和调整大小。

## 第 4 步：保存演示文稿

最后，让我们使用图表布局设置保存演示文稿。

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Java 幻灯片中设置布局模式的完整源代码

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	ISlide slide = presentation.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
	chart.getPlotArea().setX(0.2f);
	chart.getPlotArea().setY(0.2f);
	chart.getPlotArea().setWidth(0.7f);
	chart.getPlotArea().setHeight(0.7f);
	chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
	presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 结论

在本教程中，我们学习了如何使用 Aspose.Slides for Java 在 Java 幻灯片中设置图表的布局模式。您可以根据您的具体要求通过调整中的值来自定义图表的位置和大小`setX`, `setY`, `setWidth`, `setHeight`， 和`setLayoutTargetType`方法。这使您可以控制幻灯片中图表的位置。

## 常见问题解答

### 如何更改 Aspose.Slides for Java 中图表的布局模式？

要更改 Aspose.Slides for Java 中图表的布局模式，您可以使用`setLayoutTargetType`图表绘图区域上的方法。您可以将其设置为`LayoutTargetType.Inner`或者`LayoutTargetType.Outer`取决于您想要的布局。

### 我可以自定义幻灯片中图表的位置和大小吗？

是的，您可以使用`setX`, `setY`, `setWidth`， 和`setHeight`图表绘图区域上的方法。根据您的要求调整这些值以定位图表并调整图表的大小。

### 在哪里可以找到有关 Aspose.Slides for Java 的更多信息？

您可以在以下位置找到有关 Aspose.Slides for Java 的更多信息：[文档](https://reference.aspose.com/slides/java/)。它包含详细的 API 参考和示例，可帮助您在 Java 中有效地使用幻灯片和图表。