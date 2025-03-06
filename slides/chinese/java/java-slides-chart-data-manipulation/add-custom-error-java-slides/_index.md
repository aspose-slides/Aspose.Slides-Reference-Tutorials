---
title: 在 Java Slides 中添加自定义错误
linktitle: 在 Java Slides 中添加自定义错误
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides 在 Java Slides 中向 PowerPoint 图表添加自定义误差线。带有源代码的分步指南，可实现精确的数据可视化。
weight: 11
url: /zh/java/chart-data-manipulation/add-custom-error-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java Slides 中添加自定义错误


## 使用 Aspose.Slides 在 Java Slides 中添加自定义误差线的简介

在本教程中，您将学习如何使用 Aspose.Slides for Java 在 PowerPoint 演示文稿中的图表中添加自定义误差线。误差线可用于显示图表上数据点的变化或不确定性。

## 先决条件

开始之前，请确保您已准备好以下物品：

- 在您的项目中安装并配置 Aspose.Slides for Java 库。
- Java 开发环境已设置。

## 步骤 1：创建空演示文稿

首先，创建一个空的 PowerPoint 演示文稿。

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//创建空演示文稿
Presentation presentation = new Presentation();
```

## 步骤 2：添加气泡图

接下来，我们将在演示文稿中添加气泡图。

```java
//创建气泡图
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## 步骤 3：添加自定义误差线

现在，让我们向图表系列添加自定义误差线。

```java
//添加自定义误差线并设置其格式
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## 步骤 4：设置误差线数据

在此步骤中，我们将访问图表系列数据点并为每个点设置自定义误差线值。

```java
//访问图表系列数据点并设置各个点的误差线值
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

//设置图表系列点的误差线
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## 步骤 5：保存演示文稿

最后，保存带有自定义误差线的演示文稿。

```java
//保存演示文稿
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

就是这样！您已成功使用 Aspose.Slides for Java 将自定义误差线添加到 PowerPoint 演示文稿中的图表中。

## 在 Java Slides 中添加自定义错误的完整源代码

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//创建空演示文稿
Presentation presentation = new Presentation();
try
{
	//创建气泡图
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	//添加自定义误差线并设置其格式
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	//访问图表系列数据点并设置单个点的误差线值
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	//设置图表系列点的误差线
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	//保存演示文稿
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 结论

在本综合教程中，您学习了如何使用 Aspose.Slides for Java 向图表添加自定义误差线来增强 PowerPoint 演示文稿。误差线提供了有关数据变化和不确定性的宝贵见解，使您的图表更具信息性和视觉吸引力。

## 常见问题解答

### 如何自定义误差线的外观？

您可以通过修改`IErrorBarsFormat`对象，例如线条样式、线条颜色和误差线宽度。

### 我可以向其他图表类型添加误差线吗？

是的，您可以将误差线添加到 Aspose.Slides for Java 支持的各种图表类型，包括条形图、折线图和散点图。

### 如何为每个数据点设置不同的误差线值？

您可以循环遍历数据点并为每个点设置自定义误差线值，如上面的代码所示。

### 是否可以隐藏特定数据点的误差线？

是的，您可以通过设置`setVisible`的财产`IErrorBarsFormat`目的。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
