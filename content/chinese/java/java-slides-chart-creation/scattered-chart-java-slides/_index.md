---
title: Java 幻灯片中的散点图
linktitle: Java 幻灯片中的散点图
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides 在 Java 中创建散点图。用于演示文稿中数据可视化的 Java 源代码分步指南。
type: docs
weight: 11
url: /zh/java/chart-creation/scattered-chart-java-slides/
---

## Aspose.Slides for Java中的散点图简介

在本教程中，我们将指导您完成使用 Aspose.Slides for Java 创建散点图的过程。散点图对于可视化二维平面上的数据点非常有用。为了您的方便，我们将提供分步说明并包含 Java 源代码。

## 先决条件

在开始之前，请确保您具备以下先决条件：

1. [用于 Java 的 Aspose.Slides](https://products.aspose.com/slides/java)安装。
2. Java开发环境搭建完毕。

## 第 1 步：初始化演示文稿

首先，导入必要的库并创建一个新的演示文稿。

```java
//文档目录的路径。
String dataDir = "Your Document Directory";

//如果目录尚不存在，则创建该目录。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

//创建新演示文稿
Presentation pres = new Presentation();
```

## 第 2 步：添加幻灯片并创建散点图

接下来，添加一张幻灯片并在其上创建散点图。我们将使用`ScatterWithSmoothLines`本例中的图表类型。

```java
//获取第一张幻灯片
ISlide slide = pres.getSlides().get_Item(0);

//创建散点图
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## 第三步：准备图表数据

现在，让我们为散点图准备数据。我们将添加两个系列，每个系列都有多个数据点。

```java
//获取默认图表数据工作表索引
int defaultWorksheetIndex = 0;

//获取图表数据工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

//删除演示系列
chart.getChartData().getSeries().clear();

//添加第一个系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

//获取第一个图表系列
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

//将数据点添加到第一个系列
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

//编辑系列类型
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); //更改标记大小
series.getMarker().setSymbol(MarkerStyleType.Star); //更改标记符号

//采取第二个图表系列
series = chart.getChartData().getSeries().get_Item(1);

//将数据点添加到第二个系列
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

//更改第二个系列的标记样式
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## 第 4 步：保存演示文稿

最后，将带有散点图的演示文稿保存到 PPTX 文件。

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

就是这样！您已使用 Aspose.Slides for Java 成功创建了散点图。您现在可以进一步自定义此示例，以满足您的特定数据和设计要求。

## Java 幻灯片中散点图的完整源代码
```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//如果目录尚不存在，则创建该目录。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
//创建默认图表
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
//获取默认图表数据工作表索引
int defaultWorksheetIndex = 0;
//获取图表数据工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//删除演示系列
chart.getChartData().getSeries().clear();
//添加新系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
//获取第一个图表系列
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//在那里添加新点 (1:3)。
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
//添加新点 (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
//编辑系列类型
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
//更改图表系列标记
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
//采取第二个图表系列
series = chart.getChartData().getSeries().get_Item(1);
//在那里添加新点（5:2）。
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
//添加新点 (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
//添加新点 (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
//添加新点 (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
//更改图表系列标记
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## 结论

在本教程中，我们将引导您完成使用 Aspose.Slides for Java 创建散点图的过程。散点图是在二维空间中可视化数据点的强大工具，可以更轻松地分析和理解复杂的数据关系。

## 常见问题解答

### 如何更改图表类型？

要更改图表类型，请使用`setType`图表系列上的方法并提供所需的图表类型。例如，`series.setType(ChartType.Line)`会将系列更改为折线图。

### 如何自定义标记大小和样式？

您可以使用以下命令更改标记大小和样式`getMarker`系列上的方法，然后设置大小和符号属性。例如：

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

请随意在 Aspose.Slides for Java 文档中探索更多自定义选项。

记得更换`"Your Document Directory"`与您要保存演示文稿的实际路径。