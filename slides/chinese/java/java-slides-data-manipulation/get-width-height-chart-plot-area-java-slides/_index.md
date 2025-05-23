---
"description": "学习如何使用 Aspose.Slides for Java 在 Java 幻灯片中检索图表绘图区域尺寸。提升您的 PowerPoint 自动化技能。"
"linktitle": "从 Java Slides 中的图表绘图区域获取宽度和高度"
"second_title": "Aspose.Slides Java PowerPoint 处理 API"
"title": "从 Java Slides 中的图表绘图区域获取宽度和高度"
"url": "/zh/java/data-manipulation/get-width-height-chart-plot-area-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 从 Java Slides 中的图表绘图区域获取宽度和高度


## 介绍

图表是 PowerPoint 演示文稿中可视化数据的有效方式。有时，您可能需要出于各种原因（例如调整图表中元素的大小或位置）了解图表绘图区域的尺寸。本指南将演示如何使用 Java 和 Aspose.Slides for Java 获取绘图区域的宽度和高度。

## 先决条件

在深入代码之前，请确保你已经在你的 Java 项目中安装并设置了 Aspose.Slides for Java 库。你可以从 Aspose 网站下载该库。 [这里](https://releases。aspose.com/slides/java/).

## 步骤 1：设置环境

确保已将 Aspose.Slides for Java 库添加到您的 Java 项目中。您可以通过将该库添加到项目依赖项中或手动添加 JAR 文件来完成此操作。

## 步骤2：创建PowerPoint演示文稿

首先创建一个 PowerPoint 演示文稿，并添加一张幻灯片。它将作为图表的容器。

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

代替 `"Your Document Directory"` 以及您的文档目录的路径。

## 步骤3：添加图表

现在，让我们在幻灯片中添加一个簇状柱形图。我们还将验证图表布局。

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

此代码在位置 (100, 100) 处创建一个尺寸为 (500, 350) 的簇状柱形图。

## 步骤 4：获取绘图区域尺寸

要检索图表绘图区域的宽度和高度，我们可以使用以下代码：

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

现在，变量 `x`， `y`， `w`， 和 `h` 包含绘图区域的 X 坐标、Y 坐标、宽度和高度的相应值。

## 步骤5：保存演示文稿

最后，保存带有图表的演示文稿。

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

确保更换 `"Chart_out.pptx"` 使用您想要的输出文件名。

## Java 幻灯片中获取图表绘图区域宽度和高度的完整源代码

```java
// 文档目录的路径。
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
	// 将演示文稿与图表一起保存
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 结论

本文介绍了如何使用 Aspose.Slides for Java API 获取 Java Slides 中图表绘图区域的宽度和高度。当您需要在 PowerPoint 演示文稿中动态调整图表布局时，这些信息非常有用。

## 常见问题解答

### 如何将图表类型更改为簇状柱形图以外的其他类型？

您可以通过替换来更改图表类型 `ChartType.ClusteredColumn` 使用所需的图表类型枚举，例如 `ChartType.Line` 或者 `ChartType。Pie`.

### 我可以修改图表的其他属性吗？

是的，您可以使用 Aspose.Slides for Java API 修改图表的各种属性，例如数据、标签和格式。更多详细信息，请参阅文档。

### Aspose.Slides for Java 是否适合专业的 PowerPoint 自动化？

是的，Aspose.Slides for Java 是一个功能强大的库，用于在 Java 应用程序中自动执行 PowerPoint 任务。它提供了处理演示文稿、幻灯片、形状、图表等的全面功能。

### 如何了解有关 Aspose.Slides for Java 的更多信息？

您可以在 Aspose.Slides for Java 文档页面上找到大量文档和示例 [这里](https://reference。aspose.com/slides/java/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}