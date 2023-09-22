---
title: Java 幻灯片中图表中的默认标记
linktitle: Java 幻灯片中图表中的默认标记
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides for Java 在图表中创建带有默认标记的 Java 幻灯片。带有源代码的分步指南。
type: docs
weight: 16
url: /zh/java/chart-data-manipulation/default-markers-in-chart-java-slides/
---

## Java 幻灯片中图表中的默认标记简介

在本教程中，我们将探索如何使用 Aspose.Slides for Java 创建带有默认标记的图表。默认标记是添加到图表中的数据点以突出显示它们的符号或形状。我们将创建一个带有标记的折线图来可视化数据。

## 先决条件

在开始之前，请确保您已在 Java 项目中安装并设置了 Aspose.Slides for Java 库。

## 第 1 步：创建演示文稿

首先，让我们创建一个演示文稿并向其中添加一张幻灯片。然后我们将向幻灯片添加图表。

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## 第 2 步：添加带标记的折线图

现在，让我们向幻灯片添加带有标记的折线图。我们还将清除图表中的所有默认数据。

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## 第 3 步：填充图表数据

我们将使用示例数据填充图表。在此示例中，我们将创建两个包含数据点和类别的系列。

```java
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

//系列1
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"));
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));

//系列2
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

//填充系列数据
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## 第 4 步：自定义图表

您可以进一步自定义图表，例如添加图例并调整其外观。

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## 第 5 步：保存演示文稿

最后，将带有图表的演示文稿保存到您所需的位置。

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

就是这样！您已经使用 Aspose.Slides for Java 创建了带有默认标记的折线图。

## Java 幻灯片中图表中默认标记的完整源代码

```java
        //文档目录的路径。
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
            chart.getChartData().getSeries().clear();
            chart.getChartData().getCategories().clear();
            IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
            chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
            chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
            chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());
            //采取第二个图表系列
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //现在正在填充系列数据
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
            chart.setLegend(true);
            chart.getLegend().setOverlay(false);
            pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## 结论

在这个综合教程中，您学习了如何使用 Aspose.Slides for Java 在图表中创建带有默认标记的 Java 幻灯片。我们涵盖了整个过程，从设置演示文稿到自定义图表的外观并保存结果。

## 常见问题解答

### 如何更改标记符号？

您可以通过设置每个数据点的标记样式来自定义标记符号。使用`IDataPoint.setMarkerStyle()`更改标记符号。

### 如何调整图表的颜色？

要修改图表的颜色，您可以使用`IChartSeriesFormat`和`IShapeFillFormat`设置填充和线条属性的接口。

### 我可以为数据点添加标签吗？

是的，您可以使用以下命令向数据点添加标签`IDataPoint.getLabel()`方法并根据需要自定义它们。