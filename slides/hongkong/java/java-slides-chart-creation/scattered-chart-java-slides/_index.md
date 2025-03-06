---
title: Java 投影片中的散點圖
linktitle: Java 投影片中的散點圖
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides 在 Java 中建立散點圖。用於簡報中資料視覺化的 Java 原始碼逐步指南。
weight: 11
url: /zh-hant/java/chart-creation/scattered-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Aspose.Slides for Java中的散佈圖簡介

在本教學中，我們將引導您完成使用 Aspose.Slides for Java 建立散點圖的過程。散點圖對於可視化二維平面上的資料點非常有用。為了您的方便，我們將提供逐步說明並包含 Java 原始程式碼。

## 先決條件

在開始之前，請確保您具備以下先決條件：

1. [用於 Java 的 Aspose.Slides](https://products.aspose.com/slides/java)安裝。
2. Java開發環境搭建完畢。

## 第 1 步：初始化簡報

首先，導入必要的庫並建立一個新的簡報。

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";

//如果目錄尚不存在，則建立該目錄。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

//建立新簡報
Presentation pres = new Presentation();
```

## 第 2 步：新增投影片並建立散佈圖

接下來，新增一張投影片並在其上建立散點圖。我們將使用`ScatterWithSmoothLines`本例中的圖表類型。

```java
//取得第一張投影片
ISlide slide = pres.getSlides().get_Item(0);

//建立散點圖
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## 第三步：準備圖表數據

現在，讓我們為散點圖準備資料。我們將新增兩個系列，每個系列都有多個數據點。

```java
//取得預設圖表資料工作表索引
int defaultWorksheetIndex = 0;

//取得圖表資料工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

//刪除示範系列
chart.getChartData().getSeries().clear();

//新增第一個系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

//取得第一個圖表系列
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

//將資料點加入第一個系列
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

//編輯系列類型
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); //更改標記大小
series.getMarker().setSymbol(MarkerStyleType.Star); //更改標記符號

//採取第二個圖表系列
series = chart.getChartData().getSeries().get_Item(1);

//將資料點加入第二個系列
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

//變更第二個系列的標記樣式
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## 第 4 步：儲存簡報

最後，將帶有散點圖的簡報儲存到 PPTX 檔案。

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

就是這樣！您已使用 Aspose.Slides for Java 成功建立了散點圖。現在您可以進一步自訂此範例，以滿足您的特定資料和設計要求。

## Java 投影片中散點圖的完整原始碼
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//如果目錄尚不存在，則建立該目錄。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
//建立預設圖表
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
//取得預設圖表資料工作表索引
int defaultWorksheetIndex = 0;
//取得圖表資料工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//刪除示範系列
chart.getChartData().getSeries().clear();
//新增系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
//取得第一個圖表系列
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//在那裡新增點 (1:3)。
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
//新增點 (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
//編輯系列類型
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
//更改圖表系列標記
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
//採取第二個圖表系列
series = chart.getChartData().getSeries().get_Item(1);
//在那裡添加新點（5:2）。
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
//新增點 (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
//新增點 (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
//新增點 (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
//更改圖表系列標記
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## 結論

在本教學中，我們將引導您完成使用 Aspose.Slides for Java 建立散點圖的過程。散點圖是在二維空間中可視化資料點的強大工具，可以更輕鬆地分析和理解複雜的資料關係。

## 常見問題解答

### 如何更改圖表類型？

若要變更圖表類型，請使用`setType`圖表系列上的方法並提供所需的圖表類型。例如，`series.setType(ChartType.Line)`會將系列變更為折線圖。

### 如何自訂標記大小和樣式？

您可以使用以下命令變更標記大小和樣式`getMarker`系列上的方法，然後設定大小和符號屬性。例如：

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

請隨意在 Aspose.Slides for Java 文件中探索更多自訂選項。

記得更換`"Your Document Directory"`與您要儲存簡報的實際路徑。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
