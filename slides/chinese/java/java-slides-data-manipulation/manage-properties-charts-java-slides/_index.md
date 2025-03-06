---
title: 在 Java 幻灯片中管理属性图表
linktitle: 在 Java 幻灯片中管理属性图表
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 学习如何使用 Aspose.Slides 创建精美的图表并管理 Java 幻灯片中的属性。带有源代码的分步指南，可实现强大的演示文稿。
weight: 13
url: /zh/java/data-manipulation/manage-properties-charts-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## 使用 Aspose.Slides 管理 Java Slides 中的属性和图表的简介

在本教程中，我们将探索如何使用 Aspose.Slides 管理属性并在 Java 幻灯片中创建图表。Aspose.Slides 是一个功能强大的 Java API，可用于处理 PowerPoint 演示文稿。我们将逐步介绍整个过程，包括源代码示例。

## 先决条件

开始之前，请确保您已在项目中安装并设置了 Java 版 Aspose.Slides 库。您可以从以下网址下载[这里](https://releases.aspose.com/slides/java/).

## 向幻灯片添加图表

要向幻灯片添加图表，请按照以下步骤操作：

1. 导入必要的类并创建 Presentation 类的实例。

```java
//创建 Presentation 类的实例
Presentation presentation = new Presentation();
```

2. 访问要添加图表的幻灯片。在此示例中，我们访问第一张幻灯片。

```java
//访问第一张幻灯片
ISlide slide = presentation.getSlides().get_Item(0);
```

3. 添加带有默认数据的图表。在本例中，我们添加 StackedColumn3D 图表。

```java
//添加带有默认数据的图表
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## 设置图表数据

要设置图表数据，我们需要创建一个图表数据工作簿并添加系列和类别。 请按照以下步骤操作：

4. 设置图表数据表的索引。

```java
//设置图表数据表索引
int defaultWorksheetIndex = 0;
```

5. 获取图表数据工作簿。

```java
//获取图表数据工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. 将系列添加到图表。在此示例中，我们添加两个系列，分别名为“系列 1”和“系列 2”。

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. 向图表添加类别。这里我们添加三个类别。

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## 设置 3D 旋转属性

现在，让我们设置图表的 3D 旋转属性：

8. 设置直角轴。

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. 设置 X 轴和 Y 轴的旋转角度。在此示例中，我们将 X 轴旋转 40 度，Y 轴旋转 270 度。

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. 将深度百分比设置为 150。

```java
chart.getRotation3D().setDepthPercents(150);
```

## 填充系列数据

11. 取第二个图表系列并用数据点填充它。

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

//填充系列数据
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## 调整重叠

12. 设置系列的重叠值。例如，您可以将其设置为 100 以表示无重叠。

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## 保存演示文稿

最后，将演示文稿保存到磁盘。

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

就这样！您已成功使用 Java 中的 Aspose.Slides 创建了具有自定义属性的 3D 堆积柱形图。

## Java 幻灯片中管理属性图表的完整源代码

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//创建 Presentation 类的实例
Presentation presentation = new Presentation();
//访问第一张幻灯片
ISlide slide = presentation.getSlides().get_Item(0);
//添加带有默认数据的图表
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
//设置图表数据表索引
int defaultWorksheetIndex = 0;
//获取图表数据工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//添加系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
//添加类别
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
//设置 Rotation3D 属性
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
//采取第二组图表
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
//现在填充系列数据
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
//设置重叠值
series.getParentSeriesGroup().setOverlap((byte) 100);
//将演示文稿写入磁盘
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## 结论

在本教程中，我们深入研究了如何使用 Aspose.Slides 在 Java 幻灯片中管理属性和创建图表。Aspose.Slides 是一个强大的 Java API，可帮助开发人员高效地处理 PowerPoint 演示文稿。我们介绍了基本步骤并提供了源代码示例来指导您完成整个过程。

## 常见问题解答

### 我如何更改图表类型？

您可以通过修改`ChartType`添加图表时的参数。请参阅 Aspose.Slides 文档以了解可用的图表类型。

### 我可以自定义图表颜色吗？

是的，您可以通过设置系列数据点或类别的填充属性来自定义图表颜色。

### 如何向系列中添加更多数据点？

您可以使用`series.getDataPoints().addDataPointForBarSeries()`方法并指定包含数据值的单元格。

### 如何设置不同的旋转角度？

要为 X 轴和 Y 轴设置不同的旋转角度，请使用`chart.getRotation3D().setRotationX()`和`chart.getRotation3D().setRotationY()`与所需的角度值。

### 我还可以自定义哪些其他 3D 属性？

您可以参考 Aspose.Slides 文档来探索图表的其他 3D 属性，例如深度、透视和照明。
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
