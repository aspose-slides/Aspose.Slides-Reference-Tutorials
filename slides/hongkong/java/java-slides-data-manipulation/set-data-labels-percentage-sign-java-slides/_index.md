---
"description": "了解如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中設定帶有百分號的資料標籤。透過逐步指導和原始程式碼創建引人入勝的圖表。"
"linktitle": "在 Java 投影片中設定資料標籤百分號"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 Java 投影片中設定資料標籤百分號"
"url": "/zh-hant/java/data-manipulation/set-data-labels-percentage-sign-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 投影片中設定資料標籤百分號


## Aspose.Slides for Java 中設定資料標籤百分號的介紹

在本指南中，我們將引導您完成使用 Aspose.Slides for Java 設定帶有百分號的資料標籤的過程。我們將建立一個帶有堆積長條圖的 PowerPoint 演示文稿，並配置資料標籤以顯示百分比。

## 先決條件

在開始之前，請確保已將 Aspose.Slides for Java 庫新增至您的專案。您可以從下載 [這裡](https://releases。aspose.com/slides/java/).

## 步驟 1：建立新簡報

首先，我們使用 Aspose.Slides 建立一個新的 PowerPoint 簡報。

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
// 建立 Presentation 類別的實例
Presentation presentation = new Presentation();
```

## 第 2 步：新增投影片和圖表

接下來，我們在簡報中新增一張投影片和一個堆積長條圖。

```java
// 取得投影片的參考
ISlide slide = presentation.getSlides().get_Item(0);

// 在投影片上新增 PercentsStackedColumn 圖表
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## 步驟3：配置軸號格式

為了顯示百分比，我們需要配置圖表垂直軸的數字格式。

```java
// 將 NumberFormatLinkedToSource 設定為 false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## 步驟 4：新增圖表數據

我們透過建立系列和資料點來為圖表新增資料。在這個例子中，我們加入了兩個系列及其各自的資料點。

```java
// 取得圖表資料工作表
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// 新增系列
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));

// 新增系列
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
```

## 步驟5：自訂資料標籤

現在，讓我們自訂資料標籤的外觀。

```java
// 設定 LabelFormat 屬性
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);

series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

## 步驟 6：儲存簡報

最後，我們將簡報儲存為 PowerPoint 檔案。

```java
// 將簡報寫入磁碟
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

就是這樣！您已成功建立帶有堆積長條圖的 PowerPoint 演示文稿，並配置了資料標籤以使用 Aspose.Slides for Java 顯示百分比。

## Java 投影片中設定資料標籤百分比符號的完整原始碼

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
// 建立 Presentation 類別的實例
Presentation presentation = new Presentation();
// 取得投影片的參考
ISlide slide = presentation.getSlides().get_Item(0);
// 在投影片上新增 PercentsStackedColumn 圖表
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
// 將 NumberFormatLinkedToSource 設定為 false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// 取得圖表資料工作表
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// 新增系列
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// 設定係列的填滿顏色
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// 設定 LabelFormat 屬性
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
// 新增系列
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
// 設定填滿類型和顏色
series2.getFormat().getFill().setFillType(FillType.Solid);
series2.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE);
series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
// 將簡報寫入磁碟
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

## 結論

透過遵循本指南，您將學習如何使用基於百分比的數據標籤建立引人入勝的演示文稿，這對於在商業報告、教育材料等中有效傳達訊息特別有用。

## 常見問題解答

### 如何更改圖表系列的顏色？

您可以使用 `setFill` 方法如範例所示。

### 我可以自訂資料標籤的字體大小嗎？

是的，您可以透過設定 `setFontHeight` 屬性如程式碼所示。

### 如何為圖表添加更多系列？

您可以使用 `add` 方法 `IChartSeriesCollection` 目的。


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}