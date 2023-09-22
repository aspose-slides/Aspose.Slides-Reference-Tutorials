---
title: 在 Java 幻灯片中设置工作簿中的图表数据
linktitle: 在 Java 幻灯片中设置工作簿中的图表数据
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides 在 Java Slides 中设置 Excel 工作簿中的图表数据。包含动态演示代码示例的分步指南。
type: docs
weight: 15
url: /zh/java/data-manipulation/set-chart-data-from-workbook-java-slides/
---

## 在 Java 幻灯片中从工作簿设置图表数据简介

Aspose.Slides for Java 是一个功能强大的库，允许开发人员以编程方式处理 PowerPoint 演示文稿。它提供了用于创建、操作和管理 PowerPoint 幻灯片的丰富功能。使用演示文稿时的一项常见要求是从外部数据源（例如 Excel 工作簿）动态设置图表数据。在本教程中，我们将演示如何使用 Java 实现此目的。

## 先决条件

在我们深入实施之前，请确保您满足以下先决条件：

- 您的系统上安装了 Java 开发工具包 (JDK)。
- Aspose.Slides for Java 库已添加到您的项目中。
- 包含要用于图表的数据的 Excel 工作簿。

## 第 1 步：创建演示文稿

```java
String outPath = RunExamples.getOutPath() + "response2.pptx";
Presentation pres = new Presentation();
```

我们首先使用 Aspose.Slides for Java 创建一个新的 PowerPoint 演示文稿。

## 第 2 步：添加图表

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

接下来，我们将图表添加到演示文稿中的一张幻灯片中。在此示例中，我们添加了饼图，但您可以选择适合您需要的图表类型。

## 第3步：清除图表数据

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

我们清除图表中的所有现有数据，为 Excel 工作簿中的新数据做好准备。

## 第 4 步：加载 Excel 工作簿

```java
Workbook workbook = new Workbook(RunExamples.getDataDir_Charts() + "book1.xlsx");
```

我们加载包含要用于图表的数据的 Excel 工作簿。代替`"book1.xlsx"`以及 Excel 文件的路径。

## 第 5 步：将工作簿流写入图表数据

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

我们将Excel工作簿数据转换为流并将其写入图表数据。

## 第6步：设置图表数据范围

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

我们指定 Excel 工作簿中应用作图表数据的单元格范围。根据数据需要调整范围。

## 第 7 步：自定义图表系列

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

您可以自定义图表系列的各种属性来满足您的要求。在此示例中，我们为图表系列启用不同的颜色。

## 第 8 步：保存演示文稿

```java
pres.save(outPath, SaveFormat.Pptx);
```

最后，我们将包含更新的图表数据的演示文稿保存到指定的输出路径。

## 在 Java 幻灯片中从工作簿设置图表数据的完整源代码

```java
String outPath = RunExamples.getOutPath() + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook(RunExamples.getDataDir_Charts() + "book1.xlsx");
	} catch (Exception ex) {
		System.out.println(ex);
	}
	ByteArrayOutputStream mem = new ByteArrayOutputStream();
	workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
	mem.flush();
	chart.getChartData().writeWorkbookStream(mem.toByteArray());
	chart.getChartData().setRange("Sheet2!$A$1:$B$3");
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getParentSeriesGroup().setColorVaried(true);
	pres.save(outPath, SaveFormat.Pptx);
} catch(Exception e) {
} finally {
	if (pres != null) pres.dispose();
}
```

## 结论

在本教程中，我们学习了如何使用 Aspose.Slides for Java 库在 Java Slides 中设置 Excel 工作簿中的图表数据。通过遵循分步指南并使用提供的源代码示例，您可以轻松地将动态图表数据集成到 PowerPoint 演示文稿中。

## 常见问题解答

### 如何自定义演示文稿中图表的外观？

您可以通过修改颜色、字体、标签等属性来自定义图表的外观。有关图表自定义选项的详细信息，请参阅 Aspose.Slides for Java 文档。

### 我可以将不同 Excel 文件中的数据用于图表吗？

是的，您可以在代码中加载工作簿时通过指定正确的文件路径来使用任何 Excel 文件中的数据。

### 我还可以使用 Aspose.Slides for Java 创建哪些其他类型的图表？

Aspose.Slides for Java支持各种图表类型，包括条形图、折线图、散点图等。您可以选择最适合您的数据表示需求的图表类型。

### 是否可以在运行的演示文稿中动态更新图表数据？

是的，您可以通过修改基础工作簿然后刷新图表数据来动态更新演示文稿中的图表数据。

### 在哪里可以找到更多使用 Aspose.Slides for Java 的示例和资源？

您可以探索其他示例和资源[阿斯普斯网站](https://www.aspose.com/)。此外，Aspose.Slides for Java 文档提供了有关使用该库的全面指导。