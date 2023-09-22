---
title: 在 Java 幻灯片中设置反转填充颜色图表
linktitle: 在 Java 幻灯片中设置反转填充颜色图表
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides 设置 Java Slides 图表的反转填充颜色。通过此分步指南和源代码增强图表可视化效果。
type: docs
weight: 22
url: /zh/java/data-manipulation/set-invert-fill-color-chart-java-slides/
---

## Java 幻灯片中设置反转填充颜色图表简介

在本教程中，我们将演示如何使用 Aspose.Slides for Java 在 Java Slides 中设置图表的反转填充颜色。当您想要使用特定颜色突出显示图表中的负值时，反转填充颜色是一个有用的功能。我们将提供实现这一目标的分步说明和源代码。

## 先决条件

在开始之前，请确保您具备以下先决条件：

1. Aspose.Slides for Java 库已安装。
2. Java开发环境搭建。

## 第 1 步：创建演示文稿

首先，我们需要创建一个演示文稿来添加图表。您可以使用以下代码来创建演示文稿：

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 第 2 步：添加图表

接下来，我们将向演示文稿添加聚集柱形图。您可以这样做：

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## 第 3 步：设置图表数据

现在，让我们设置图表数据，包括系列和类别：

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

//添加新系列和类别
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## 第 4 步：填充系列数据

现在，让我们填充图表的系列数据：

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## 第5步：设置反转填充颜色

要设置图表系列的反转填充颜色，可以使用以下代码：

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

在上面的代码中，我们将系列设置为负值反转填充颜色，并指定反转填充的颜色。

## 第 6 步：保存演示文稿

最后，保存带有图表的演示文稿：

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Java 幻灯片中设置反转填充颜色图表的完整源代码

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
//添加新系列和类别
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
//获取第一个图表系列并填充系列数据。
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
}
finally
{
if (pres != null) pres.dispose();
}
```

## 结论

在本教程中，我们向您展示了如何使用 Aspose.Slides for Java 在 Java Slides 中设置图表的反转填充颜色。此功能允许您使用特定颜色突出显示图表中的负值，使您的数据在视觉上更具信息性。

## 常见问题解答

在本节中，我们将解决一些与使用 Aspose.Slides for Java 在 Java Slides 中设置图表的反转填充颜色相关的常见问题。

### 如何安装 Aspose.Slides for Java？

您可以通过在 Java 项目中包含 Aspose.Slides JAR 文件来安装 Aspose.Slides for Java。您可以从以下位置下载该库[Aspose.Slides for Java 下载页面](https://releases.aspose.com/slides/java/)。请按照特定开发环境的文档中提供的安装说明进行操作。

### 我可以自定义图表系列中倒置填充的颜色吗？

是的，您可以自定义图表系列中反向填充的颜色。在提供的代码示例中，`series.getInvertedSolidFillColor().setColor(Color.RED)` line 将反转填充的颜色设置为红色。您可以更换`Color.RED`与您选择的任何其他颜色。

### 如何修改 Aspose.Slides for Java 中的图表类型？

您可以通过更改来修改图表类型`ChartType`将图表添加到演示文稿时的参数。在代码示例中，我们使用了`ChartType.ClusteredColumn`。您可以通过指定适当的选项来探索其他图表类型，例如折线图、条形图、饼图等。`ChartType`枚举值。

### 如何将多个数据系列添加到图表中？

要将多个数据系列添加到图表中，您可以使用`chart.getChartData().getSeries().add(...)`您要添加的每个系列的方法。确保为每个系列提供适当的数据点和标签，以便用多个系列填充您的图表。

### 有没有办法自定义图表外观的其他方面？

是的，您可以使用 Aspose.Slides for Java 自定义图表外观的各个方面，包括轴标签、标题、图例等。有关自定义图表元素和外观的详细指南，请参阅文档。

### 我可以以不同的格式保存图表吗？

是的，您可以使用 Aspose.Slides for Java 以不同的格式保存图表。在提供的代码示例中，我们将演示文稿保存为 PPTX 文件。您可以使用不同的`SaveFormat`根据您的要求，可以选择将其保存为其他格式，例如 PDF、PNG 或 SVG。