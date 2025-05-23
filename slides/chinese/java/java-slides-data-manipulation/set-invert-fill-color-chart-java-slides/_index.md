---
"description": "学习如何使用 Aspose.Slides 为 Java Slides 图表设置反转填充颜色。使用本分步指南和源代码增强您的图表可视化效果。"
"linktitle": "在 Java 幻灯片中设置反转填充颜色图表"
"second_title": "Aspose.Slides Java PowerPoint 处理 API"
"title": "在 Java 幻灯片中设置反转填充颜色图表"
"url": "/zh/java/data-manipulation/set-invert-fill-color-chart-java-slides/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 幻灯片中设置反转填充颜色图表


## Java 幻灯片中设置反转填充颜色图表的介绍

在本教程中，我们将演示如何使用 Aspose.Slides for Java 在 Java Slides 中设置图表的反转填充颜色。当您想用特定颜色突出显示图表中的负值时，反转填充颜色是一个非常有用的功能。我们将提供实现此目的的分步说明和源代码。

## 先决条件

开始之前，请确保您已满足以下先决条件：

1. 已安装 Java 库的 Aspose.Slides。
2. Java开发环境搭建。

## 步骤 1：创建演示文稿

首先，我们需要创建一个演示文稿来添加图表。您可以使用以下代码来创建演示文稿：

```java
// 文档目录的路径。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 第 2 步：添加图表

接下来，我们将在演示文稿中添加一个簇状柱形图。操作方法如下：

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## 步骤3：设置图表数据

现在，让我们设置图表数据，包括系列和类别：

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// 添加新系列和类别
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## 步骤 4：填充系列数据

现在，让我们填充图表的系列数据：

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## 步骤 5：设置反转填充颜色

要设置图表系列的反转填充颜色，可以使用以下代码：

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

在上面的代码中，我们将系列设置为反转负值的填充颜色，并指定反转填充的颜色。

## 步骤 6：保存演示文稿

最后，保存带有图表的演示文稿：

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Java 幻灯片中设置反转填充颜色图表的完整源代码

```java
// 文档目录的路径。
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// 添加新系列和类别
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
// 采取第一个图表系列并填充系列数据。
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

在本教程中，我们向您展示了如何使用 Aspose.Slides for Java 在 Java Slides 中设置图表的反转填充颜色。此功能允许您使用特定颜色突出显示图表中的负值，从而使数据更具视觉吸引力。

## 常见问题解答

在本节中，我们将解决一些与使用 Aspose.Slides for Java 设置 Java Slides 中图表的反转填充颜色有关的常见问题。

### 如何安装 Aspose.Slides for Java？

您可以通过在 Java 项目中包含 Aspose.Slides JAR 文件来安装 Aspose.Slides for Java。您可以从 [Aspose.Slides for Java下载页面](https://releases.aspose.com/slides/java/)请按照文档中针对您的特定开发环境提供的安装说明进行操作。

### 我可以自定义图表系列中反向填充的颜色吗？

是的，您可以自定义图表系列中反向填充的颜色。在提供的代码示例中， `series.getInvertedSolidFillColor().setColor(Color.RED)` 线将反色填充颜色设置为红色。您可以替换 `Color.RED` 您可以选择其他任何颜色。

### 如何修改 Aspose.Slides for Java 中的图表类型？

您可以通过更改 `ChartType` 向演示文稿添加图表时的参数。在代码示例中，我们使用了 `ChartType.ClusteredColumn`。您可以通过指定适当的 `ChartType` 枚举值。

### 如何向图表添加多个数据系列？

要向图表添加多个数据系列，您可以使用 `chart.getChartData().getSeries().add(...)` 为每个要添加的系列提供相应的方法。确保为每个系列提供适当的数据点和标签，以便用多个系列填充图表。

### 有没有办法自定义图表外观的其他方面？

是的，您可以使用 Aspose.Slides for Java 自定义图表外观的各个方面，包括轴标签、标题、图例等。有关自定义图表元素和外观的详细指导，请参阅文档。

### 我可以以不同的格式保存图表吗？

是的，您可以使用 Aspose.Slides for Java 将图表保存为不同的格式。在提供的代码示例中，我们将演示文稿保存为 PPTX 文件。您可以使用不同的 `SaveFormat` 根据您的要求，可以选择将其保存为其他格式，如 PDF、PNG 或 SVG。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}