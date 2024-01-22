---
title: Java 幻灯片中的箱形图
linktitle: Java 幻灯片中的箱形图
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides 在 Java 演示文稿中创建箱形图。包含用于有效数据可视化的分步指南和源代码。
type: docs
weight: 10
url: /zh/java/chart-elements/box-chart-java-slides/
---

## Aspose.Slides for Java 中的箱形图简介

在本教程中，我们将引导您完成使用 Aspose.Slides for Java 创建箱形图的过程。箱形图对于可视化具有各种四分位数和异常值的统计数据非常有用。我们将提供分步说明以及源代码来帮助您入门。

## 先决条件

在开始之前，请确保您具备以下条件：

- Aspose.Slides for Java 库已安装并配置。
- Java开发环境搭建完毕。

## 第 1 步：初始化演示文稿

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

在此步骤中，我们使用现有 PowerPoint 文件（本例中为“test.pptx”）的路径初始化演示文稿对象。

## 第 2 步：创建箱线图

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

在此步骤中，我们在演示文稿的第一张幻灯片上创建一个箱形图形状。我们还从图表中清除任何现有的类别和系列。

## 第 3 步：定义类别

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
```

在此步骤中，我们定义箱线图的类别。我们使用`IChartDataWorkbook`添加类别并相应地标记它们。

## 第四步：创建系列

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

在这里，我们为图表创建一个 BoxAndWhisker 系列，并配置各种选项，如四分位数方法、平均线、平均标记、内部点和离群点。

## 第 5 步：添加数据点

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

在此步骤中，我们将数据点添加到 BoxAndWhisker 系列中。这些数据点代表图表的统计数据。

## 第 6 步：保存演示文稿

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

最后，我们将包含箱形图的演示文稿保存到名为“BoxAndWhisker.pptx”的新 PowerPoint 文件中。

恭喜！您已使用 Aspose.Slides for Java 成功创建了箱形图。您可以通过调整各种属性并根据需要添加更多数据点来进一步自定义图表。

## Java 幻灯片中箱形图的完整源代码

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
	series.setQuartileMethod(QuartileMethodType.Exclusive);
	series.setShowMeanLine(true);
	series.setShowMeanMarkers(true);
	series.setShowInnerPoints(true);
	series.setShowOutlierPoints(true);
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
	pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 结论

在本教程中，我们学习了如何使用 Aspose.Slides for Java 创建箱形图。箱形图是可视化统计数据（包括四分位数和异常值）的宝贵工具。我们提供了分步指南以及源代码，以帮助您开始在 Java 应用程序中创建箱形图。

## 常见问题解答

### 如何更改箱形图的外观？

您可以通过修改线条样式、颜色和字体等属性来自定义箱形图的外观。有关图表自定义的详细信息，请参阅 Aspose.Slides for Java 文档。

### 我可以向箱形图添加其他数据系列吗？

是的，您可以通过创建额外的数据系列将多个数据系列添加到箱形图中`IChartSeries`对象并向其添加数据点。

### QuartileMethodType.Exclusive 是什么意思？

这`QuartileMethodType.Exclusive`设置指定四分位数计算应使用排除方法完成。您可以根据您的数据和要求选择不同的四分位数计算方法。