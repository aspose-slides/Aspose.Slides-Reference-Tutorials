---
"description": "学习如何使用 Aspose.Slides 在 Java 演示文稿中创建箱线图。包含分步指南和源代码，助您实现高效的数据可视化。"
"linktitle": "Java 幻灯片中的箱线图"
"second_title": "Aspose.Slides Java PowerPoint 处理 API"
"title": "Java 幻灯片中的箱线图"
"url": "/zh/java/chart-elements/box-chart-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 幻灯片中的箱线图


## Aspose.Slides for Java 中的箱线图简介

在本教程中，我们将引导您使用 Aspose.Slides for Java 创建箱线图。箱线图非常适合用于可视化包含各种四分位数和异常值的统计数据。我们将提供分步说明以及源代码，帮助您快速上手。

## 先决条件

开始之前，请确保您已具备以下条件：

- Aspose.Slides for Java 库已安装并配置。
- Java 开发环境已设置。

## 步骤 1：初始化演示文稿

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

在此步骤中，我们使用现有 PowerPoint 文件的路径（此示例中为“test.pptx”）初始化演示对象。

## 步骤 2：创建箱线图

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

在此步骤中，我们在演示文稿的第一张幻灯片上创建一个箱形图形状。我们还清除了图表中所有现有的类别和系列。

## 步骤3：定义类别

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

在此步骤中，我们定义箱线图的类别。我们使用 `IChartDataWorkbook` 添加类别并进行相应标记。

## 步骤 4：创建系列

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

在这里，我们为图表创建一个 BoxAndWhisker 系列，并配置各种选项，如四分位数法、平均线、平均标记、内点和异常点。

## 步骤5：添加数据点

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

在此步骤中，我们向 BoxAndWhisker 系列添加数据点。这些数据点代表图表的统计数据。

## 步骤 6：保存演示文稿

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

最后，我们将包含箱线图的演示文稿保存到名为“BoxAndWhisker.pptx”的新 PowerPoint 文件中。

恭喜！您已成功使用 Aspose.Slides for Java 创建了箱线图。您可以根据需要调整各种属性并添加更多数据点，进一步自定义图表。

## Java 幻灯片中箱线图的完整源代码

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

在本教程中，我们学习了如何使用 Aspose.Slides for Java 创建箱线图。箱线图是可视化统计数据（包括四分位数和异常值）的宝贵工具。我们提供了分步指南和源代码，帮助您在 Java 应用程序中开始创建箱线图。

## 常见问题解答

### 如何更改箱线图的外观？

您可以通过修改线条样式、颜色和字体等属性来自定义箱线图的外观。有关图表自定义的详细信息，请参阅 Aspose.Slides for Java 文档。

### 我可以向箱线图添加其他数据系列吗？

是的，您可以通过创建额外的 `IChartSeries` 对象并向其添加数据点。

### QuartileMethodType.Exclusive 是什么意思？

这 `QuartileMethodType.Exclusive` 此设置指定四分位数计算应使用排他法。您可以根据数据和需求选择不同的四分位数计算方法。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}