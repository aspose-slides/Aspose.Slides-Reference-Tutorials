---
title: 在 Java 幻灯片中设置类别轴的日期格式
linktitle: 在 Java 幻灯片中设置类别轴的日期格式
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides for Java 设置 PowerPoint 图表中类别轴的日期格式。带有源代码的分步指南。
type: docs
weight: 26
url: /zh/java/data-manipulation/setting-date-format-category-axis-java-slides/
---

## 在 Java 幻灯片中设置类别轴的日期格式简介

在本教程中，我们将学习如何使用 Aspose.Slides for Java 在 PowerPoint 图表中设置类别轴的日期格式。 Aspose.Slides for Java 是一个功能强大的库，允许您以编程方式创建、操作和管理 PowerPoint 演示文稿。

## 先决条件

在开始之前，请确保您具备以下条件：

1.  Aspose.Slides for Java 库（您可以从[这里](https://releases.aspose.com/slides/java/).
2. Java开发环境搭建。

## 第 1 步：创建 PowerPoint 演示文稿

首先，我们需要创建一个 PowerPoint 演示文稿，在其中添加图表。确保您已导入必要的 Aspose.Slides 类。

```java
//文档目录的路径。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 第 2 步：将图表添加到幻灯片

现在，我们将图表添加到 PowerPoint 幻灯片中。在此示例中我们将使用面积图。

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## 第三步：准备图表数据

我们将设置图表数据和类别。在此示例中，我们将使用日期类别。

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

//添加日期类别
chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

//添加数据系列
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## 第4步：自定义类别轴
现在，让我们自定义类别轴以以特定格式（例如，yyyy）显示日期。

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## 第 5 步：保存演示文稿
最后，保存 PowerPoint 演示文稿。

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

就是这样！您已使用 Aspose.Slides for Java 成功设置了 PowerPoint 图表中类别轴的日期格式。

## 在 Java 幻灯片中设置类别轴日期格式的完整源代码

```java
	//文档目录的路径。
	String dataDir = "Your Document Directory";
	Presentation pres = new Presentation();
	try
	{
		IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
		IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
		wb.clear(0);
		chart.getChartData().getCategories().clear();
		chart.getChartData().getSeries().clear();
		chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));
		IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
		chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
		chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
		chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
		pres.save(RunExamples.getOutPath() + "test.pptx", SaveFormat.Pptx);
	}
	finally
	{
		if (pres != null) pres.dispose();
	}
}
public static String convertToOADate(GregorianCalendar date) throws ParseException
{
	double oaDate;
	SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
	java.util.Date baseDate = myFormat.parse("30 12 1899");
	Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);
	oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24) + ((double) date.get(Calendar.MINUTE) / (60 * 24)) + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
	return String.valueOf(oaDate);
```

＃＃结论

您已使用 Aspose.Slides for Java 成功自定义了 Java Slides 图表中类别轴的日期格式。这允许您在图表上以所需的格式显示日期值。请随意根据您的具体要求探索进一步的定制选项。

## 常见问题解答

### 如何更改类别轴的日期格式？

要更改类别轴的日期格式，请使用`setNumberFormat`类别轴上的方法并提供所需的日期格式模式，例如“yyyy-MM-dd”或“MM/yyyy”。确保设置`setNumberFormatLinkedToSource(false)`覆盖默认格式。

### 我可以在同一演示文稿中对不同图表使用不同的日期格式吗？

是的，您可以为同一演示文稿中不同图表中的类别轴设置不同的日期格式。只需根据需要自定义每个图表的类别轴即可。

### 如何向图表添加更多数据点？

要向图表添加更多数据点，请使用`getDataPoints().addDataPointForLineSeries`数据系列上的方法并提供数据值。