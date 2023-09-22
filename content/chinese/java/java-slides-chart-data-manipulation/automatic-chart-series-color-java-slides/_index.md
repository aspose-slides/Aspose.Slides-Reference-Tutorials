---
title: Java 幻灯片中的自动图表系列颜色
linktitle: Java 幻灯片中的自动图表系列颜色
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides for Java 在 PowerPoint 演示文稿中创建具有自动系列颜色的动态图表。轻松增强您的数据可视化。
type: docs
weight: 14
url: /zh/java/chart-data-manipulation/automatic-chart-series-color-java-slides/
---

## Aspose.Slides for Java中自动图表系列颜色简介

在本教程中，我们将探索如何使用 Aspose.Slides for Java 创建带有图表的 PowerPoint 演示文稿，并为图表系列设置自动填充颜色。自动填充颜色可以让您的图表更具视觉吸引力，并让库为您选择颜色，从而节省您的时间。

## 先决条件

在开始之前，请确保您的项目中安装了 Aspose.Slides for Java 库。您可以从以下位置下载：[这里](https://releases.aspose.com/slides/java/).

## 第 1 步：创建新演示文稿

首先，我们将创建一个新的 PowerPoint 演示文稿并向其中添加一张幻灯片。

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//创建Presentation类的实例
Presentation presentation = new Presentation();
```

## 第 2 步：将图表添加到幻灯片

接下来，我们将向幻灯片添加聚集柱形图。我们还将设置第一个系列来显示值。

```java
//访问第一张幻灯片
ISlide slide = presentation.getSlides().get_Item(0);
//添加带有默认数据的图表
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
//将第一个系列设置为“显示值”
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## 第 3 步：填充图表数据

现在，我们将用数据填充图表。我们将首先删除默认生成的系列和类别，然后添加新的系列和类别。

```java
//设置图表数据表索引
int defaultWorksheetIndex = 0;
//获取图表数据工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//删除默认生成的系列和类别
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

//添加新系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

//添加新类别
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## 第 4 步：填充系列数据

我们将填充系列 1 和系列 2 的系列数据。

```java
//获取第一个图表系列
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//现在正在填充系列数据
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

//采取第二个图表系列
series = chart.getChartData().getSeries().get_Item(1);
//现在正在填充系列数据
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## 第5步：设置系列的自动填充颜色

现在，让我们为图表系列设置自动填充颜色。这将使图书馆为我们选择颜色。

```java
//设置系列的自动填充颜色
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## 第 6 步：保存演示文稿

最后，我们将带有图表的演示文稿保存到 PowerPoint 文件中。

```java
//保存带有图表的演示文稿
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Java 幻灯片中自动图表系列颜色的完整源代码

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//创建Presentation类的实例
Presentation presentation = new Presentation();
try
{
	//访问第一张幻灯片
	ISlide slide = presentation.getSlides().get_Item(0);
	//添加带有默认数据的图表
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	//将第一个系列设置为“显示值”
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	//设置图表数据表索引
	int defaultWorksheetIndex = 0;
	//获取图表数据工作表
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	//删除默认生成的系列和类别
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	//添加新系列
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	//添加新类别
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	//获取第一个图表系列
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	//现在正在填充系列数据
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	//设置系列的自动填充颜色
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	//采取第二个图表系列
	series = chart.getChartData().getSeries().get_Item(1);
	//现在正在填充系列数据
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	//设置系列的填充颜色
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	//保存带有图表的演示文稿
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 结论

在本教程中，我们学习了如何使用 Aspose.Slides for Java 创建带有图表的 PowerPoint 演示文稿，并为图表系列设置自动填充颜色。自动颜色可以增强图表的视觉吸引力，并使您的演示文稿更具吸引力。您可以根据您的具体要求进一步自定义图表。

## 常见问题解答

### 如何在 Aspose.Slides for Java 中设置图表系列的自动填充颜色？

要在 Aspose.Slides for Java 中设置图表系列的自动填充颜色，请使用以下代码：

```java
//设置系列的自动填充颜色
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

此代码将使库自动为图表系列选择颜色。

### 如果需要，我可以自定义图表颜色吗？

是的，您可以根据需要自定义图表颜色。在提供的示例中，我们使用了自动填充颜色，但您可以通过修改`FillType`和`SolidFillColor`系列格式的属性。

### 如何向图表添加其他系列或类别？

要向图表添加其他系列或类别，请使用`getSeries()`和`getCategories()`图表的方法`ChartData`目的。您可以通过指定数据和标签来添加新的系列和类别。

### 是否可以进一步格式化图表和标签？

是的，您可以根据需要进一步设置图表、系列和标签的格式。 Aspose.Slides for Java 为图表提供了广泛的格式化选项，包括字体、颜色、样式等。您可以浏览文档以获取有关格式选项的更多详细信息。

### 在哪里可以找到有关使用 Aspose.Slides for Java 的更多信息？

有关 Aspose.Slides for Java 的更多信息和详细文档，您可以访问参考文档[这里](https://reference.aspose.com/slides/java/).