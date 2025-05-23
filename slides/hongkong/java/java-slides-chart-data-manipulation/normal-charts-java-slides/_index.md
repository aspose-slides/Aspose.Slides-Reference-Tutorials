---
"description": "使用 Aspose.Slides for Java 在 Java Slides 中建立普通圖表。用於在 PowerPoint 簡報中建立、自訂和儲存圖表的逐步指南和原始程式碼。"
"linktitle": "Java Slides 中的普通圖表"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "Java Slides 中的普通圖表"
"url": "/zh-hant/java/chart-data-manipulation/normal-charts-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slides 中的普通圖表


## Java 投影片中的普通圖表簡介

在本教程中，我們將介紹使用 Aspose.Slides for Java API 在 Java Slides 中建立普通圖表的過程。我們將使用逐步說明以及原始程式碼來示範如何在 PowerPoint 簡報中建立聚集長條圖。

## 先決條件

在開始之前，請確保您已滿足以下先決條件：

1. 已安裝 Aspose.Slides for Java API。
2. Java 開發環境已設定。
3. Java 程式設計基礎知識。

## 步驟1：設定項目

確保您的項目有目錄。我們將其稱為程式碼中提到的「您的文件目錄」。您可以將其替換為專案目錄的實際路徑。

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
// 如果目錄尚不存在，則建立該目錄。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## 第 2 步：建立簡報

現在，讓我們建立一個 PowerPoint 簡報並存取其第一張投影片。

```java
// 實例化代表 PPTX 檔案的 Presentation 類
Presentation pres = new Presentation();
// 存取第一張投影片
ISlide sld = pres.getSlides().get_Item(0);
```

## 步驟3：新增圖表

我們將在幻燈片中新增一個簇狀長條圖並設定其標題。

```java
// 新增帶有預設資料的圖表
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// 設定圖表標題
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## 步驟4：設定圖表數據

接下來，我們將透過定義系列和類別來設定圖表資料。

```java
// 將第一個系列設定為顯示值
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// 設定圖表資料表的索引
int defaultWorksheetIndex = 0;

// 取得圖表資料工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// 刪除預設產生的系列和類別
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// 新增系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// 新增類別
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## 步驟5：填充系列數據

現在，讓我們填入圖表的一系列數據點。

```java
// 採取第一個圖表系列
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// 填充系列數據
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// 設定係列的填滿顏色
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// 採取第二張圖表系列
series = chart.getChartData().getSeries().get_Item(1);

// 填充系列數據
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// 設定係列的填滿顏色
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## 步驟6：自訂標籤

讓我們自訂圖表系列的資料標籤。

```java
// 第一個標籤將顯示類別名稱
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// 顯示帶有系列名稱和分隔符號的第三個標籤的值
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## 步驟 7：儲存簡報

最後，將帶有圖表的簡報儲存到您的專案目錄中。

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

就是這樣！您已成功使用 Aspose.Slides for Java 在 PowerPoint 簡報中建立了簇狀長條圖。您可以根據您的要求進一步自訂此圖表。

## Java 投影片中普通圖表的完整原始碼

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
// 如果目錄尚不存在，則建立該目錄。
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// 實例化代表 PPTX 檔案的 Presentation 類
Presentation pres = new Presentation();
// 存取第一張投影片
ISlide sld = pres.getSlides().get_Item(0);
// 新增帶有預設資料的圖表
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// 設定圖表標題
// Chart.getChartTitle().getTextFrameForOverriding().setText("範例標題");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// 將第一個系列設定為顯示值
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// 設定圖表資料表的索引
int defaultWorksheetIndex = 0;
// 取得圖表資料工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// 刪除預設產生的系列和類別
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
int s = chart.getChartData().getSeries().size();
s = chart.getChartData().getCategories().size();
// 新增系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// 新增類別
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// 採取第一個圖表系列
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// 現在填充系列數據
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// 設定係列的填滿顏色
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// 採取第二張圖表系列
series = chart.getChartData().getSeries().get_Item(1);
// 現在填充系列數據
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// 設定係列的填滿顏色
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// 第一個標籤將顯示類別名稱
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// 顯示第三個標籤的值
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// 將簡報與圖表一起保存
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# 結論

在本教程中，我們學習如何使用 Aspose.Slides for Java API 在 Java Slides 中建立普通圖表。我們按照帶有原始程式碼的逐步指南在 PowerPoint 簡報中建立了聚集長條圖。

## 常見問題解答

### 我該如何更改圖表類型？

若要變更圖表類型，請修改 `ChartType` 使用新增圖表時的參數 `sld.getShapes().addChart()`。您可以從 Aspose.Slides 中提供的各種圖表類型中進行選擇。

### 我可以更改圖表系列的顏色嗎？

是的，您可以透過設定每個系列的填滿顏色來更改圖表系列的顏色 `series。getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### 如何為圖表新增更多類別或系列？

您可以透過使用 `chart.getChartData().getCategories().add()` 和 `chart.getChartData().getSeries().add()` 方法。

### 如何進一步自訂圖表標題？

您可以透過修改以下屬性來進一步自訂圖表標題 `chart.getChartTitle()` 例如文字對齊方式、字體大小和顏色。

### 如何將圖表儲存為不同的文件格式？

若要將圖表儲存為不同的檔案格式，請變更 `SaveFormat` 參數 `pres.save()` 方法轉換為所需的格式（例如 PDF、PNG、JPEG）。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}