---
title: Java 幻灯片中的散点图
linktitle: Java 幻灯片中的散点图
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides 在 Java 中创建散点图。使用 Java 源代码进行演示文稿数据可视化的分步指南。
weight: 11
url: /zh/java/chart-creation/scattered-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Aspose.Slides for Java 中散点图的介绍

在本教程中，我们将指导您使用 Aspose.Slides for Java 创建散点图的过程。散点图对于在二维平面上可视化数据点非常有用。我们将提供分步说明并包含 Java 源代码以方便您使用。

## 先决条件

开始之前，请确保您已满足以下先决条件：

1. [Aspose.Slides for Java](https://products.aspose.com/slides/java)已安装。
2. Java 开发环境已设置。

## 步骤 1：初始化演示文稿

首先，导入必要的库并创建一个新的演示文稿。

```java
//文档目录的路径。
String dataDir = "Your Document Directory";

//如果目录尚不存在，则创建目录。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

//创建新演示文稿
Presentation pres = new Presentation();
```

## 步骤 2：添加幻灯片并创建散点图

接下来，添加幻灯片并在其上创建散点图。我们将使用`ScatterWithSmoothLines`本例中为图表类型。

```java
//获取第一张幻灯片
ISlide slide = pres.getSlides().get_Item(0);

//创建散点图
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## 步骤 3：准备图表数据

现在，让我们为散点图准备数据。我们将添加两个系列，每个系列有多个数据点。

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

//以第一个图表系列为例
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

//向第一个系列添加数据点
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

//编辑系列类型
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); //更改标记大小
series.getMarker().setSymbol(MarkerStyleType.Star); //更改标记符号

//以第二组图表为例
series = chart.getChartData().getSeries().get_Item(1);

//向第二个系列添加数据点
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

//更改第二个系列的标记样式
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## 步骤 4：保存演示文稿

最后，将包含散点图的演示文稿保存为 PPTX 文件。

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

就是这样！您已成功使用 Aspose.Slides for Java 创建了散点图。您现在可以进一步自定义此示例以满足您的特定数据和设计要求。

## Java 幻灯片中散点图的完整源代码
```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//如果目录尚不存在，则创建目录。
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
//采取第一个图表系列
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//在那里添加新观点（1：3）。
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
//添加新观点 (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
//编辑系列类型
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
//更改图表系列标记
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
//采取第二组图表
series = chart.getChartData().getSeries().get_Item(1);
//在那里添加新观点（5:2）。
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
//添加新点 (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
//添加新观点 (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
//添加新点 (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
//更改图表系列标记
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## 结论

在本教程中，我们引导您完成使用 Aspose.Slides for Java 创建散点图的过程。散点图是可视化二维空间中数据点的强大工具，可让您更轻松地分析和理解复杂的数据关系。

## 常见问题解答

### 我如何更改图表类型？

要更改图表类型，请使用`setType`方法，并提供所需的图表类型。例如，`series.setType(ChartType.Line)`会将该系列更改为折线图。

### 如何自定义标记的大小和样式？

您可以使用`getMarker`方法，然后设置尺寸和符号属性。例如：

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

欢迎随意在 Aspose.Slides for Java 文档中探索更多自定义选项。

记得更换`"Your Document Directory"`与您想要保存演示文稿的实际路径。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
