---
title: Java 投影片中的多類別圖表
linktitle: Java 投影片中的多類別圖表
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 使用 Aspose.Slides for Java 在 Java 投影片中建立多類別圖表。具有原始程式碼的逐步指南，可在簡報中實現令人印象深刻的資料視覺化。
type: docs
weight: 20
url: /zh-hant/java/chart-data-manipulation/multi-category-chart-java-slides/
---

## 使用 Aspose.Slides 介紹 Java Slides 中的多類別圖表

在本教程中，我們將學習如何使用 Aspose.Slides for Java API 在 Java 投影片中建立多類別圖表。本指南將提供逐步說明以及原始程式碼，以協助您建立具有多個類別和系列的聚集長條圖。

## 先決條件
在開始之前，請確保您已在 Java 開發環境中安裝並設定了 Aspose.Slides for Java 程式庫。

## 第 1 步：設定環境
首先，匯入必要的類別並建立一個新的簡報物件來處理投影片。

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 第 2 步：新增投影片和圖表
接下來，建立一張投影片並向其中添加一個聚集長條圖。

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## 步驟3：清除現有數據
從圖表中清除任何現有資料。

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## 步驟 4：設定資料類別
現在，讓我們為圖表設定資料類別。我們將建立多個類別並將它們分組。

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

//新增類別並對它們進行分組
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
```

## 第5步：新增系列
現在，讓我們將一個系列與數據點一起添加到圖表中。

```java
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);

series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
```

## 第 6 步：儲存簡報
最後，儲存帶有圖表的簡報。

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

就是這樣！您已使用 Aspose.Slides 在 Java 投影片中成功建立了多類別圖表。您可以進一步自訂此圖表以滿足您的特定要求。

## Java 投影片中多類別圖表的完整原始碼

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
//新增系列
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"),
		ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
//儲存帶有圖表的簡報
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## 結論

在本教程中，我們學習如何使用 Aspose.Slides for Java API 在 Java 投影片中建立多類別圖表。我們透過原始程式碼逐步了解了創建具有多個類別和系列的聚集長條圖的指南。

## 常見問題解答

### 如何自訂圖表外觀？

您可以透過修改顏色、字體和樣式等屬性來自訂圖表外觀。有關詳細的自訂選項，請參閱 Aspose.Slides 文件。

### 我可以在圖表中添加更多系列嗎？

是的，您可以按照步驟 5 中所示的類似流程為圖表添加其他系列。

### 如何更改圖表類型？

若要變更圖表類型，請替換`ChartType.ClusteredColumn`在步驟 2 中新增圖表時使用所需的圖表類型。

### 如何為圖表新增標題？

您可以使用以下命令向圖表新增標題`ch.getChartTitle().getTextFrame().setText("Chart Title");`方法。