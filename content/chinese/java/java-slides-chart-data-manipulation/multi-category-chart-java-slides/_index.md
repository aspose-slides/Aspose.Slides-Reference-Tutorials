---
title: Java 幻灯片中的多类别图表
linktitle: Java 幻灯片中的多类别图表
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 使用 Aspose.Slides for Java 在 Java 幻灯片中创建多类别图表。带有源代码的分步指南，可在演示文稿中实现令人印象深刻的数据可视化。
type: docs
weight: 20
url: /zh/java/chart-data-manipulation/multi-category-chart-java-slides/
---

## 使用 Aspose.Slides 介绍 Java Slides 中的多类别图表

在本教程中，我们将学习如何使用 Aspose.Slides for Java API 在 Java 幻灯片中创建多类别图表。本指南将提供分步说明以及源代码，以帮助您创建具有多个类别和系列的聚集柱形图。

## 先决条件
在开始之前，请确保您已在 Java 开发环境中安装并设置了 Aspose.Slides for Java 库。

## 第 1 步：设置环境
首先，导入必要的类并创建一个新的演示对象来处理幻灯片。

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 第 2 步：添加幻灯片和图表
接下来，创建一张幻灯片并向其中添加一个聚集柱形图。

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## 步骤3：清除现有数据
从图表中清除任何现有数据。

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## 步骤 4：设置数据类别
现在，让我们为图表设置数据类别。我们将创建多个类别并将它们分组。

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

//添加类别并对它们进行分组
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
```

## 第5步：添加系列
现在，让我们将一个系列与数据点一起添加到图表中。

```java
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);

series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
```

## 第 6 步：保存演示文稿
最后，保存带有图表的演示文稿。

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

就是这样！您已使用 Aspose.Slides 在 Java 幻灯片中成功创建了多类别图表。您可以进一步自定义此图表以满足您的特定要求。

## Java 幻灯片中多类别图表的完整源代码

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
//添加系列
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"),
		ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
//保存带有图表的演示文稿
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## 结论

在本教程中，我们学习了如何使用 Aspose.Slides for Java API 在 Java 幻灯片中创建多类别图表。我们通过源代码逐步了解了创建具有多个类别和系列的聚集柱形图的指南。

## 常见问题解答

### 如何自定义图表外观？

您可以通过修改颜色、字体和样式等属性来自定义图表外观。有关详细的自定义选项，请参阅 Aspose.Slides 文档。

### 我可以在图表中添加更多系列吗？

是的，您可以按照步骤 5 中所示的类似过程向图表添加其他系列。

### 如何更改图表类型？

要更改图表类型，请替换`ChartType.ClusteredColumn`在步骤 2 中添加图表时使用所需的图表类型。

### 如何为图表添加标题？

您可以使用以下命令向图表添加标题`ch.getChartTitle().getTextFrame().setText("Chart Title");`方法。