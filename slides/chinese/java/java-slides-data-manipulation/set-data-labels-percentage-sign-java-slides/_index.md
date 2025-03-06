---
title: 在 Java 幻灯片中设置数据标签百分号
linktitle: 在 Java 幻灯片中设置数据标签百分号
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides for Java 在 PowerPoint 演示文稿中设置带有百分号的数据标签。使用分步指导和源代码创建引人入胜的图表。
weight: 17
url: /zh/java/data-manipulation/set-data-labels-percentage-sign-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Aspose.Slides for Java 中设置数据标签百分号的简介

在本指南中，我们将引导您完成使用 Aspose.Slides for Java 设置带有百分比符号的数据标签的过程。我们将创建一个带有堆积柱形图的 PowerPoint 演示文稿，并配置数据标签以显示百分比。

## 先决条件

开始之前，请确保已将 Aspose.Slides for Java 库添加到项目中。您可以从以下位置下载[这里](https://releases.aspose.com/slides/java/).

## 步骤 1：创建新演示文稿

首先，我们使用 Aspose.Slides 创建一个新的 PowerPoint 演示文稿。

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//创建 Presentation 类的实例
Presentation presentation = new Presentation();
```

## 第 2 步：添加幻灯片和图表

接下来，我们在演示文稿中添加一张幻灯片和一个堆积柱形图。

```java
//获取幻灯片的参考
ISlide slide = presentation.getSlides().get_Item(0);

//在幻灯片上添加 PercentsStackedColumn 图表
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## 步骤 3：配置轴号格式

为了显示百分比，我们需要配置图表垂直轴的数字格式。

```java
//将 NumberFormatLinkedToSource 设置为 false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## 步骤 4：添加图表数据

我们通过创建系列和数据点将数据添加到图表中。在此示例中，我们添加两个系列及其各自的数据点。

```java
//获取图表数据工作表
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

//添加新系列
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));

//添加新系列
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
```

## 步骤 5：自定义数据标签

现在，让我们自定义数据标签的外观。

```java
//设置 LabelFormat 属性
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);

series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

## 步骤 6：保存演示文稿

最后，我们将演示文稿保存为 PowerPoint 文件。

```java
//将演示文稿写入磁盘
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

就是这样！您已成功创建了带有堆积柱形图的 PowerPoint 演示文稿，并配置了数据标签以使用 Aspose.Slides for Java 显示百分比。

## Java 幻灯片中设置数据标签百分号的完整源代码

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//创建 Presentation 类的实例
Presentation presentation = new Presentation();
//获取幻灯片的参考
ISlide slide = presentation.getSlides().get_Item(0);
//在幻灯片上添加 PercentsStackedColumn 图表
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
//将 NumberFormatLinkedToSource 设置为 false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
//获取图表数据工作表
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
//添加新系列
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
//设置系列的填充颜色
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
//设置 LabelFormat 属性
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
//添加新系列
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
//设置填充类型和颜色
series2.getFormat().getFill().setFillType(FillType.Solid);
series2.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE);
series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
//将演示文稿写入磁盘
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

## 结论

通过遵循本指南，您将学习如何使用基于百分比的数据标签创建引人入胜的演示文稿，这对于在商业报告、教育材料等中有效地传达信息特别有用。

## 常见问题解答

### 如何更改图表系列的颜色？

您可以使用`setFill`方法如示例所示。

### 我可以自定义数据标签的字体大小吗？

是的，您可以通过设置自定义数据标签的字体大小`setFontHeight`属性如代码所示。

### 如何向图表添加更多系列？

您可以使用`add`方法`IChartSeriesCollection`目的。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
