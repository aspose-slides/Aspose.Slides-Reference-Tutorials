---
"description": "学习如何使用 Aspose.Slides for Java 设置 PowerPoint 图表中分类轴的日期格式。提供包含源代码的分步指南。"
"linktitle": "在 Java 幻灯片中设置分类轴的日期格式"
"second_title": "Aspose.Slides Java PowerPoint 处理 API"
"title": "在 Java 幻灯片中设置分类轴的日期格式"
"url": "/zh/java/data-manipulation/setting-date-format-category-axis-java-slides/"
"weight": 26
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 幻灯片中设置分类轴的日期格式


## Java 幻灯片中设置分类轴日期格式的介绍

在本教程中，我们将学习如何使用 Aspose.Slides for Java 设置 PowerPoint 图表中类别轴的日期格式。Aspose.Slides for Java 是一个功能强大的库，允许您以编程方式创建、操作和管理 PowerPoint 演示文稿。

## 先决条件

开始之前，请确保您已具备以下条件：

1. Aspose.Slides for Java 库（您可以从 [这里](https://releases。aspose.com/slides/java/).
2. Java开发环境搭建。

## 步骤 1：创建 PowerPoint 演示文稿

首先，我们需要创建一个 PowerPoint 演示文稿，并在其中添加图表。请确保已导入必要的 Aspose.Slides 类。

```java
// 文档目录的路径。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 步骤 2：向幻灯片添加图表

现在，让我们在 PowerPoint 幻灯片中添加一个图表。本例中使用面积图。

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## 步骤3：准备图表数据

我们将设置图表数据和类别。在本例中，我们将使用日期类别。

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

// 添加日期类别
chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

// 添加数据系列
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## 步骤 4：自定义分类轴
现在，让我们自定义类别轴以特定格式显示日期（例如，yyyy）。

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## 步骤 5：保存演示文稿
最后，保存 PowerPoint 演示文稿。

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

就是这样！您已成功使用 Aspose.Slides for Java 设置 PowerPoint 图表中类别轴的日期格式。

## Java 幻灯片中设置分类轴日期格式的完整源代码

```java
	// 文档目录的路径。
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
		pres.save("Your Output Directory" + "test.pptx", SaveFormat.Pptx);
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

您已成功使用 Aspose.Slides for Java 自定义 Java Slides 图表中类别轴的日期格式。这允许您在图表上以所需的格式显示日期值。您可以根据您的具体需求，探索更多自定义选项。

## 常见问题解答

### 如何更改类别轴的日期格式？

要更改分类轴的日期格式，请使用 `setNumberFormat` 方法，并提供所需的日期格式模式，例如“yyyy-MM-dd”或“MM/yyyy”。确保设置 `setNumberFormatLinkedToSource(false)` 覆盖默认格式。

### 我可以在同一个演示文稿中对不同的图表使用不同的日期格式吗？

是的，您可以为同一演示文稿中不同图表的分类轴设置不同的日期格式。只需根据需要为每个图表自定义分类轴即可。

### 如何向图表添加更多数据点？

要向图表添加更多数据点，请使用 `getDataPoints().addDataPointForLineSeries` 方法对数据系列提供数据值。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}