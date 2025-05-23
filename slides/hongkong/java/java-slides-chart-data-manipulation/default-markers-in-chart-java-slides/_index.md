---
"description": "了解如何使用 Aspose.Slides for Java 建立帶有圖表中預設標記的 Java 投影片。帶有原始程式碼的分步指南。"
"linktitle": "Java 投影片中圖表的預設標記"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "Java 投影片中圖表的預設標記"
"url": "/zh-hant/java/chart-data-manipulation/default-markers-in-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 投影片中圖表的預設標記


## Java 投影片中圖表預設標記介紹

在本教程中，我們將探討如何使用 Aspose.Slides for Java 建立帶有預設標記的圖表。預設標記是添加到圖表中的數據點以突出顯示它們的符號或形狀。我們將建立一個標記的折線圖來視覺化資料。

## 先決條件

在開始之前，請確保您已在 Java 專案中安裝並設定了 Aspose.Slides for Java 程式庫。

## 步驟 1：建立簡報

首先，讓我們建立一個簡報並新增一張投影片。然後我們將在幻燈片中新增一個圖表。

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## 步驟 2：新增標示的折線圖

現在，讓我們在幻燈片中添加帶有標記的折線圖。我們還將清除圖表中的所有預設資料。

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## 步驟 3：填入圖表數據

我們將用範例資料填充圖表。在此範例中，我們將建立兩個包含資料點和類別的系列。

```java
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// 系列 1
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"));
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));

// 系列 2
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// 填充系列數據
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## 步驟 4：自訂圖表

您可以進一步自訂圖表，例如新增圖例和調整其外觀。

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## 步驟 5：儲存簡報

最後，將帶有圖表的簡報儲存到您想要的位置。

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

就是這樣！您已經使用 Aspose.Slides for Java 建立了帶有預設標記的折線圖。

## Java 投影片中圖表預設標記的完整原始碼

```java
        // 文檔目錄的路徑。
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
            chart.getChartData().getSeries().clear();
            chart.getChartData().getCategories().clear();
            IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
            chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
            chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
            chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());
            //採取第二張圖表系列
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //現在填充系列數據
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
            chart.setLegend(true);
            chart.getLegend().setOverlay(false);
            pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## 結論

在本綜合教學中，您學習如何使用 Aspose.Slides for Java 在圖表中建立帶有預設標記的 Java 投影片。我們涵蓋了整個過程，從設定簡報到自訂圖表外觀和儲存結果。

## 常見問題解答

### 我如何更改標記符號？

您可以透過設定每個資料點的標記樣式來自訂標記符號。使用 `IDataPoint.setMarkerStyle()` 更改標記符號。

### 如何調整圖表的顏色？

要修改圖表的顏色，您可以使用 `IChartSeriesFormat` 和 `IShapeFillFormat` 用於設定填滿和線條屬性的介面。

### 我可以為數據點添加標籤嗎？

是的，您可以使用 `IDataPoint.getLabel()` 方法並根據需要進行客製化。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}