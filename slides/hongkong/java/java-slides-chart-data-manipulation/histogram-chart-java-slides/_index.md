---
title: Java 投影片中的直方圖
linktitle: Java 投影片中的直方圖
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中建立直方圖。帶有資料視覺化原始程式碼的分步指南。
weight: 19
url: /zh-hant/java/chart-data-manipulation/histogram-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## 使用 Aspose.Slides 介紹 Java Slides 中的直方圖

在本教程中，我們將引導您完成使用 Aspose.Slides for Java API 在 PowerPoint 簡報中建立直方圖的過程。直方圖用於表示連續間隔內的資料分佈。

## 先決條件

在開始之前，請確保您已安裝 Aspose.Slides for Java 程式庫。您可以從[阿斯普斯網站](https://releases.aspose.com/slides/java/).

## 第 1 步：初始化您的項目

建立一個 Java 專案並將 Aspose.Slides 庫包含在專案的依賴項中。

## 步驟2：導入必要的函式庫

```java
import com.aspose.slides.*;
```

## 第 3 步：載入現有簡報

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

確保更換`"Your Document Directory"`與 PowerPoint 文件的實際路徑。

## 第 4 步：建立直方圖

現在，讓我們在簡報的投影片上建立直方圖。

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    //將資料點加入系列中
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    //將水平軸聚合類型設定為自動
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    //儲存簡報
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

在此程式碼中，我們首先從圖表中清除所有現有類別和系列。然後，我們使用以下方法將資料點新增至該系列中`getDataPoints().addDataPointForHistogramSeries`方法。最後，我們將水平軸聚合類型設為自動並儲存簡報。

## Java 投影片中直方圖的完整原始碼

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
	chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
	pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

在本教學中，我們探索如何使用 Aspose.Slides for Java API 在 PowerPoint 簡報中建立直方圖。直方圖是可視化連續時間間隔內資料分佈的寶貴工具，它們可以為您的簡報提供強大的補充，特別是在處理統計或分析內容時。

## 常見問題解答

### 如何安裝 Aspose.Slides for Java？

您可以從以下位置下載 Aspose.Slides for Java 程式庫[這裡](https://releases.aspose.com/slides/java/)。請按照其網站上提供的安裝說明進行操作。

### 直方圖有什麼用？

直方圖用於可視化連續間隔內的資料分佈。它通常在統計中用於表示頻率分佈。

### 我可以自訂直方圖的外觀嗎？

是的，您可以使用 Aspose.Slides API 自訂圖表的外觀，包括其顏色、標籤和軸。
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
