---
"description": "使用 Aspose.Slides for Java 在 Java Slides 中建立多類別圖表。帶有原始程式碼的分步指南，用於在簡報中實現令人印象深刻的資料視覺化。"
"linktitle": "Java 投影片中的多類別圖表"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "Java 投影片中的多類別圖表"
"url": "/zh-hant/java/chart-data-manipulation/multi-category-chart-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 投影片中的多類別圖表


## 使用 Aspose.Slides 在 Java Slides 中建立多類別圖表的介紹

在本教程中，我們將學習如何使用 Aspose.Slides for Java API 在 Java 投影片中建立多類別圖表。本指南將提供逐步說明以及原始程式碼，以協助您建立具有多個類別和系列的聚集長條圖。

## 先決條件
在開始之前，請確保您已在 Java 開發環境中安裝並設定了 Aspose.Slides for Java 程式庫。

## 步驟 1：設定環境
首先，匯入必要的類別並建立一個新的 Presentation 物件來處理投影片。

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 步驟 2：新增投影片和圖表
接下來，建立一個投影片並在其中新增一個叢集長條圖。

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## 步驟3：清除現有數據
清除圖表中的所有現有資料。

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## 步驟4：設定資料類別
現在，讓我們設定圖表的資料類別。我們將建立多個類別並對其進行分組。

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// 新增類別並進行分組
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

## 步驟5：新增系列
現在，讓我們為圖表中新增一系列數據點。

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

## 步驟6：儲存簡報
最後，儲存帶有圖表的簡報。

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

就是這樣！您已成功使用 Aspose.Slides 在 Java 投影片中建立多類別圖表。您可以進一步自訂此圖表以滿足您的特定要求。

## Java 投影片中多類別圖表的完整原始碼

```java
// 文檔目錄的路徑。
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
//            新增系列
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
// 將簡報與圖表一起保存
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## 結論

在本教程中，我們學習如何使用 Aspose.Slides for Java API 在 Java 投影片中建立多類別圖表。我們按照帶有原始程式碼的逐步指南創建了具有多個類別和系列的聚集長條圖。

## 常見問題解答

### 如何自訂圖表外觀？

您可以透過修改顏色、字體和樣式等屬性來自訂圖表外觀。有關詳細的自訂選項，請參閱 Aspose.Slides 文件。

### 我可以為圖表添加更多系列嗎？

是的，您可以按照步驟 5 中所示的類似流程為圖表添加其他系列。

### 如何更改圖表類型？

若要變更圖表類型，請替換 `ChartType.ClusteredColumn` 在步驟 2 新增圖表時選擇所需的圖表類型。

### 如何為圖表新增標題？

您可以使用 `ch.getChartTitle().getTextFrame().setText("Chart Title");` 方法。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}