---
title: 在 Java Slides 中设置外部工作簿
linktitle: 在 Java Slides 中设置外部工作簿
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides for Java 在 Java Slides 中设置外部工作簿。使用 Excel 数据集成创建动态演示文稿。
weight: 19
url: /zh/java/data-manipulation/set-external-workbook-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Java 幻灯片中设置外部工作簿的简介

在本教程中，我们将探索如何使用 Aspose.Slides 在 Java Slides 中设置外部工作簿。您将学习如何创建带有引用外部 Excel 工作簿数据的图表的 PowerPoint 演示文稿。在本指南结束时，您将清楚地了解如何将外部数据集成到 Java Slides 演示文稿中。

## 先决条件

在深入实施之前，请确保您满足以下先决条件：

- 您的系统上安装了 Java 开发工具包 (JDK)。
- Aspose.Slides for Java 库已添加到您的项目中。
- 包含您想要在演示文稿中引用的数据的 Excel 工作簿。

## 步骤 1：创建新演示文稿

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

我们首先使用 Aspose.Slides 创建一个新的 PowerPoint 演示文稿。

## 步骤 2：添加图表

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

接下来我们在演示文稿中插入一个饼图。您可以根据需要自定义图表类型和位置。

## 步骤 3：访问外部工作簿

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

要访问外部工作簿，我们使用`setExternalWorkbook`方法并提供包含数据的 Excel 工作簿的路径。

## 步骤4：绑定图表数据

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

我们通过指定系列和类别的单元格引用将图表绑定到来自外部工作簿的数据。

## 步骤 5：保存演示文稿

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

最后，我们将引用外部工作簿的演示文稿保存为 PowerPoint 文件。

## Java 幻灯片中设置外部工作簿的完整源代码

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
	chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
	pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 结论

在本教程中，我们学习了如何使用 Aspose.Slides 在 Java Slides 中设置外部工作簿。您现在可以创建动态引用 Excel 工作簿数据的演示文稿，从而增强幻灯片的灵活性和交互性。

## 常见问题解答

### 如何安装 Aspose.Slides for Java？

通过将库添加到 Java 项目，即可安装 Aspose.Slides for Java。您可以从 Aspose 网站下载该库，然后按照文档中提供的安装说明进行操作。

### 我可以在外部工作簿中使用不同的图表类型吗？

是的，您可以使用 Aspose.Slides 支持的各种图表类型，并将它们绑定到外部工作簿的数据。根据您选择的图表类型，该过程可能会略有不同。

### 如果我的外部工作簿的数据结构发生变化怎么办？

如果外部工作簿的数据结构发生变化，您可能需要更新 Java 代码中的单元格引用以确保图表数据保持准确。

### Aspose.Slides 是否与最新的 Java 版本兼容？

Aspose.Slides for Java 会定期更新以确保与最新 Java 版本兼容。请务必检查更新并使用最新版本的库以获得最佳性能和兼容性。

### 我可以添加引用同一外部工作簿的多个图表吗？

是的，您可以向演示文稿添加多个图表，所有图表都引用同一个外部工作簿。只需对要创建的每个图表重复本教程中概述的步骤即可。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
