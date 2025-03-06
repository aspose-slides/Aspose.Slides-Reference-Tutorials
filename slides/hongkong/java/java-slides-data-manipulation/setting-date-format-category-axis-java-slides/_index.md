---
title: 在 Java 投影片中設定類別軸的日期格式
linktitle: 在 Java 投影片中設定類別軸的日期格式
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 設定 PowerPoint 圖表中類別軸的日期格式。帶有原始程式碼的分步指南。
weight: 26
url: /zh-hant/java/data-manipulation/setting-date-format-category-axis-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## 在 Java 投影片中設定類別軸的日期格式簡介

在本教程中，我們將學習如何使用 Aspose.Slides for Java 在 PowerPoint 圖表中設定類別軸的日期格式。 Aspose.Slides for Java 是一個功能強大的函式庫，可讓您以程式設計方式建立、操作和管理 PowerPoint 簡報。

## 先決條件

在開始之前，請確保您具備以下條件：

1. Aspose.Slides for Java 函式庫（您可以從[這裡](https://releases.aspose.com/slides/java/).
2. Java開發環境搭建。

## 第 1 步：建立 PowerPoint 簡報

首先，我們需要建立一個 PowerPoint 演示文稿，在其中添加圖表。確保您已匯入必要的 Aspose.Slides 類別。

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 第 2 步：將圖表新增至投影片

現在，我們將圖表新增到 PowerPoint 投影片中。在此範例中我們將使用面積圖。

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## 第三步：準備圖表數據

我們將設定圖表資料和類別。在此範例中，我們將使用日期類別。

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

//新增日期類別
chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

//新增數據系列
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## 第4步：自訂類別軸
現在，讓我們自訂類別軸以以特定格式（例如，yyyy）顯示日期。

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## 第 5 步：儲存簡報
最後，儲存 PowerPoint 簡報。

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

就是這樣！您已使用 Aspose.Slides for Java 成功設定了 PowerPoint 圖表中類別軸的日期格式。

## 在 Java 投影片中設定類別軸日期格式的完整原始碼

```java
	//文檔目錄的路徑。
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

＃＃結論

您已使用 Aspose.Slides for Java 成功自訂了 Java Slides 圖表中類別軸的日期格式。這允許您在圖表上以所需的格式顯示日期值。請隨意根據您的具體要求探索進一步的客製化選項。

## 常見問題解答

### 如何更改類別軸的日期格式？

若要變更類別軸的日期格式，請使用`setNumberFormat`類別軸上的方法並提供所需的日期格式模式，例如“yyyy-MM-dd”或“MM/yyyy”。確保設定`setNumberFormatLinkedToSource(false)`覆蓋預設格式。

### 我可以在同一簡報中對不同圖表使用不同的日期格式嗎？

是的，您可以為同一簡報中不同圖表中的類別軸設定不同的日期格式。只需根據需要自訂每個圖表的類別軸即可。

### 如何為圖表添加更多數據點？

若要為圖表新增更多資料點，請使用`getDataPoints().addDataPointForLineSeries`資料系列上的方法並提供資料值。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
