---
"description": "了解如何使用 Aspose.Slides 在 Java 簡報中建立箱線圖。包含有效資料視覺化的逐步指南和原始程式碼。"
"linktitle": "Java 投影片中的箱型圖"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "Java 投影片中的箱型圖"
"url": "/zh-hant/java/chart-elements/box-chart-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 投影片中的箱型圖


## Aspose.Slides for Java 中的箱型圖簡介

在本教學中，我們將引導您完成使用 Aspose.Slides for Java 建立箱型圖的過程。箱線圖對於視覺化具有各種四分位數和異常值的統計資料很有用。我們將提供逐步說明以及原始程式碼來幫助您入門。

## 先決條件

在開始之前，請確保您已具備以下條件：

- Aspose.Slides for Java 程式庫已安裝並配置。
- Java 開發環境已設定。

## 步驟 1：初始化簡報

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

在此步驟中，我們使用現有 PowerPoint 檔案的路徑（此範例中為「test.pptx」）初始化示範物件。

## 步驟 2：建立箱線圖

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

在此步驟中，我們在簡報的第一張投影片上建立一個箱形圖形狀。我們也從圖表中清除所有現有的類別和系列。

## 步驟3：定義類別

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
```

在此步驟中，我們定義箱型圖的類別。我們使用 `IChartDataWorkbook` 新增類別並進行相應標記。

## 步驟 4：建立系列

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

在這裡，我們為圖表建立一個 BoxAndWhisker 系列，並配置各種選項，例如四分位數法、平均線、平均標記、內點和異常點。

## 步驟5：新增數據點

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

在這一步驟中，我們將數據點加入 BoxAndWhisker 系列中。這些數據點代表圖表的統計數據。

## 步驟 6：儲存簡報

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

最後，我們將包含箱線圖的簡報儲存到名為「BoxAndWhisker.pptx」的新 PowerPoint 檔案中。

恭喜！您已成功使用 Aspose.Slides for Java 建立了箱型圖。您可以透過調整各種屬性並根據需要添加更多資料點來進一步自訂圖表。

## Java 投影片中箱線圖的完整原始碼

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
	series.setQuartileMethod(QuartileMethodType.Exclusive);
	series.setShowMeanLine(true);
	series.setShowMeanMarkers(true);
	series.setShowInnerPoints(true);
	series.setShowOutlierPoints(true);
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
	pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

在本教程中，我們學習如何使用 Aspose.Slides for Java 建立箱線圖。箱線圖是可視化統計資料（包括四分位數和異常值）的寶貴工具。我們提供了逐步指南以及原始程式碼，以幫助您開始在 Java 應用程式中建立箱線圖。

## 常見問題解答

### 如何更改箱線圖的外觀？

您可以透過修改線條樣式、顏色和字體等屬性來自訂箱線圖的外觀。有關圖表定制的詳細信息，請參閱 Aspose.Slides for Java 文件。

### 我可以為箱線圖添加其他資料系列嗎？

是的，您可以透過建立額外的 `IChartSeries` 物件並向其添加資料點。

### QuartileMethodType.Exclusive 是什麼意思？

這 `QuartileMethodType.Exclusive` 設定指定應使用獨佔方法進行四分位數計算。您可以根據您的資料和要求選擇不同的四分位數計算方法。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}