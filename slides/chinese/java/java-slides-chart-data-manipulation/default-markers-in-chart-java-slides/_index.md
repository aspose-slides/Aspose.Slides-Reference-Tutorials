---
"description": "学习如何使用 Aspose.Slides for Java 创建带有默认标记的 Java 幻灯片图表。包含源代码的分步指南。"
"linktitle": "Java 幻灯片中图表的默认标记"
"second_title": "Aspose.Slides Java PowerPoint 处理 API"
"title": "Java 幻灯片中图表的默认标记"
"url": "/zh/java/chart-data-manipulation/default-markers-in-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 幻灯片中图表的默认标记


## Java 幻灯片中图表默认标记介绍

在本教程中，我们将探索如何使用 Aspose.Slides for Java 创建带有默认标记的图表。默认标记是添加到图表中数据点以突出显示它们的符号或形状。我们将创建一个带有标记的折线图来可视化数据。

## 先决条件

在开始之前，请确保您已在 Java 项目中安装并设置了 Aspose.Slides for Java 库。

## 步骤 1：创建演示文稿

首先，我们创建一个演示文稿并添加一张幻灯片。然后，我们将在幻灯片中添加一个图表。

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## 步骤 2：添加带标记的折线图

现在，让我们在幻灯片中添加一个带有标记的折线图。我们还将清除图表中的所有默认数据。

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## 步骤 3：填充图表数据

我们将使用示例数据填充图表。在此示例中，我们将创建两个包含数据点和类别的系列。

```java
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// 系列 1
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

// 系列 2
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// 填充系列数据
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## 步骤 4：自定义图表

您可以进一步自定义图表，例如添加图例和调整其外观。

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## 步骤 5：保存演示文稿

最后，将带有图表的演示文稿保存到您想要的位置。

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

就这样！您已经使用 Aspose.Slides for Java 创建了带有默认标记的折线图。

## Java 幻灯片中图表默认标记的完整源代码

```java
        // 文档目录的路径。
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
            //采取第二张图表系列
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //现在填充系列数据
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

在本篇全面的教程中，您学习了如何使用 Aspose.Slides for Java 创建带有默认标记的 Java 幻灯片图表。我们涵盖了从设置演示文稿到自定义图表外观以及保存结果的整个过程。

## 常见问题解答

### 我如何更改标记符号？

您可以通过设置每个数据点的标记样式来自定义标记符号。使用 `IDataPoint.setMarkerStyle()` 更改标记符号。

### 如何调整图表的颜色？

要修改图表的颜色，您可以使用 `IChartSeriesFormat` 和 `IShapeFillFormat` 用于设置填充和线条属性的界面。

### 我可以给数据点添加标签吗？

是的，您可以使用 `IDataPoint.getLabel()` 方法并根据需要进行定制。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}