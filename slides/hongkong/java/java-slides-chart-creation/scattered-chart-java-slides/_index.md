---
"description": "了解如何使用 Aspose.Slides 在 Java 中建立散點圖。帶有 Java 原始程式碼的分步指南，用於簡報中的資料視覺化。"
"linktitle": "Java 投影片中的散點圖"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "Java 投影片中的散點圖"
"url": "/zh-hant/java/chart-creation/scattered-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 投影片中的散點圖


## Aspose.Slides for Java 中散佈圖的介紹

在本教學中，我們將引導您完成使用 Aspose.Slides for Java 建立散點圖的過程。散點圖對於在二維平面上可視化資料點很有用。我們將提供逐步說明並包含 Java 原始程式碼以方便您使用。

## 先決條件

在開始之前，請確保您已滿足以下先決條件：

1. [Aspose.Slides for Java](https://products.aspose.com/slides/java) 已安裝。
2. Java 開發環境已設定。

## 步驟 1：初始化簡報

首先，導入必要的庫並建立一個新的簡報。

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";

// 如果目錄尚不存在，則建立該目錄。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// 建立新簡報
Presentation pres = new Presentation();
```

## 步驟 2：新增投影片並建立散佈圖

接下來，新增投影片並在其上建立散點圖。我們將使用 `ScatterWithSmoothLines` 本例中為圖表類型。

```java
// 取得第一張投影片
ISlide slide = pres.getSlides().get_Item(0);

// 建立散點圖
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## 步驟3：準備圖表數據

現在，讓我們準備散點圖的資料。我們將新增兩個系列，每個系列有多個數據點。

```java
// 取得預設圖表資料工作表索引
int defaultWorksheetIndex = 0;

// 取得圖表資料工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// 刪除示範系列
chart.getChartData().getSeries().clear();

// 新增第一個系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// 以第一個圖表系列為例
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// 在第一個系列中新增資料點
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// 編輯系列類型
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // 更改標記大小
series.getMarker().setSymbol(MarkerStyleType.Star); // 更改標記符號

// 取第二個圖表系列
series = chart.getChartData().getSeries().get_Item(1);

// 為第二個系列新增資料點
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// 變更第二個系列的標記樣式
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## 步驟 4：儲存簡報

最後，將包含散點圖的簡報儲存為 PPTX 檔案。

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

就是這樣！您已成功使用 Aspose.Slides for Java 建立散點圖。現在您可以進一步自訂此範例以滿足您的特定資料和設計要求。

## Java 投影片中散點圖的完整原始碼
```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
// 如果目錄尚不存在，則建立該目錄。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
// 建立預設圖表
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// 取得預設圖表資料工作表索引
int defaultWorksheetIndex = 0;
// 取得圖表資料工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// 刪除示範系列
chart.getChartData().getSeries().clear();
// 新增系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// 採取第一個圖表系列
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// 在那裡添加新點（1：3）。
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// 新增點 (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// 編輯系列類型
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// 更改圖表系列標記
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// 採取第二張圖表系列
series = chart.getChartData().getSeries().get_Item(1);
// 在那裡添加新點（5:2）。
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// 新增點 (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// 新增點 (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// 新增點 (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// 更改圖表系列標記
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## 結論

在本教學中，我們引導您完成使用 Aspose.Slides for Java 建立散點圖的過程。散點圖是可視化二維空間中資料點的強大工具，可以更輕鬆地分析和理解複雜的資料關係。

## 常見問題解答

### 我該如何更改圖表類型？

若要變更圖表類型，請使用 `setType` 方法在圖表系列上提供所需的圖表類型。例如， `series.setType(ChartType.Line)` 會將該系列變更為折線圖。

### 如何自訂標記的大小和樣式？

您可以使用 `getMarker` 方法，然後設定大小和符號屬性。例如：

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

歡迎隨意在 Aspose.Slides for Java 文件中探索更多自訂選項。

記得更換 `"Your Document Directory"` 與您想要儲存簡報的實際路徑。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}