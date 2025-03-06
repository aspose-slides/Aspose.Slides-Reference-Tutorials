---
title: Java 幻灯片中的自动图表系列颜色
linktitle: Java 幻灯片中的自动图表系列颜色
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides for Java 在 PowerPoint 演示文稿中创建具有自动系列颜色的动态图表。轻松增强数据可视化。
weight: 14
url: /zh/java/chart-data-manipulation/automatic-chart-series-color-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Aspose.Slides for Java 中自动图表系列颜色介绍

在本教程中，我们将探索如何使用 Aspose.Slides for Java 创建带有图表的 PowerPoint 演示文稿，并为图表系列设置自动填充颜色。自动填充颜色可以让您的图表更具视觉吸引力，并通过让库为您选择颜色来节省您的时间。

## 先决条件

开始之前，请确保您的项目中安装了 Aspose.Slides for Java 库。您可以从以下网址下载[这里](https://releases.aspose.com/slides/java/).

## 步骤 1：创建新演示文稿

首先，我们将创建一个新的 PowerPoint 演示文稿并向其中添加幻灯片。

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//创建 Presentation 类的实例
Presentation presentation = new Presentation();
```

## 步骤 2：向幻灯片添加图表

接下来，我们将在幻灯片中添加一个簇状柱形图。我们还将设置第一个系列以显示值。

```java
//访问第一张幻灯片
ISlide slide = presentation.getSlides().get_Item(0);
//添加带有默认数据的图表
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
//将第一个系列设置为显示值
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## 步骤 3：填充图表数据

现在，我们将用数据填充图表。我们首先删除默认生成的系列和类别，然后添加新的系列和类别。

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

## 步骤 4：填充系列数据

我们将填充系列 1 和系列 2 的系列数据。

```java
//采取第一个图表系列
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//现在填充系列数据
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

//采取第二组图表
series = chart.getChartData().getSeries().get_Item(1);
//现在填充系列数据
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## 步骤 5：设置系列的自动填充颜色

现在，让我们为图表系列设置自动填充颜色。这将使库为我们选择颜色。

```java
//设置系列的自动填充颜色
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## 步骤 6：保存演示文稿

最后，我们将包含图表的演示文稿保存为 PowerPoint 文件。

```java
//保存带有图表的演示文稿
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Java 幻灯片中自动图表系列颜色的完整源代码

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//创建 Presentation 类的实例
Presentation presentation = new Presentation();
try
{
	//访问第一张幻灯片
	ISlide slide = presentation.getSlides().get_Item(0);
	//添加带有默认数据的图表
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	//将第一个系列设置为显示值
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
	//采取第一个图表系列
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	//现在填充系列数据
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	//设置系列的自动填充颜色
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	//采取第二组图表
	series = chart.getChartData().getSeries().get_Item(1);
	//现在填充系列数据
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

在本教程中，我们学习了如何使用 Aspose.Slides for Java 创建带有图表的 PowerPoint 演示文稿，并为图表系列设置自动填充颜色。自动颜色可以增强图表的视觉吸引力，并使您的演示文稿更具吸引力。您可以根据需要进一步自定义图表以满足您的特定要求。

## 常见问题解答

### 如何在 Aspose.Slides for Java 中为图表系列设置自动填充颜色？

要在 Aspose.Slides for Java 中为图表系列设置自动填充颜色，请使用以下代码：

```java
//设置系列的自动填充颜色
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

此代码将让库自动为图表系列选择颜色。

### 如果需要，我可以自定义图表颜色吗？

是的，您可以根据需要自定义图表颜色。在提供的示例中，我们使用了自动填充颜色，但您可以通过修改`FillType`和`SolidFillColor`系列格式的属性。

### 如何向图表添加其他系列或类别？

要向图表添加其他系列或类别，请使用`getSeries()`和`getCategories()`图表的方法`ChartData`对象。您可以通过指定数据和标签来添加新的系列和类别。

### 是否可以进一步格式化图表和标签？

是的，您可以根据需要进一步格式化图表、系列和标签。Aspose.Slides for Java 为图表提供了广泛的格式化选项，包括字体、颜色、样式等。您可以浏览文档以获取有关格式化选项的更多详细信息。

### 在哪里可以找到有关使用 Aspose.Slides for Java 的更多信息？

有关 Aspose.Slides for Java 的更多信息和详细文档，您可以访问参考文档[这里](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
