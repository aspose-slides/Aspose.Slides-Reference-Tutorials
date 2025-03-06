---
title: 在 Java 投影片中設定間隙寬度
linktitle: 在 Java 投影片中設定間隙寬度
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 在 Java 投影片中設定間隙寬度。增強 PowerPoint 簡報的圖表視覺效果。
weight: 21
url: /zh-hant/java/data-manipulation/set-gap-width-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 投影片中設定間隙寬度


## 在 Aspose.Slides for Java 中設定間隙寬度簡介

在本教學中，我們將引導您完成使用 Aspose.Slides for Java 設定 PowerPoint 簡報中圖表的間隙寬度的過程。間隙寬度決定圖表中柱形或條形之間的間距，使您可以控制圖表的視覺外觀。

## 先決條件

在開始之前，請確保您已安裝 Aspose.Slides for Java 程式庫。您可以從Aspose網站下載它[這裡](https://releases.aspose.com/slides/java/).

## 逐步指南

請依照下列步驟使用 Aspose.Slides for Java 設定圖表中的間隙寬度：

### 1. 建立一個空演示文稿

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";

//建立一個空演示文稿
Presentation presentation = new Presentation();
```

### 2. 存取第一張投影片

```java
//存取第一張投影片
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. 新增帶有預設資料的圖表

```java
//新增具有預設資料的圖表
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4、設定圖表資料表索引

```java
//設定圖表資料表索引
int defaultWorksheetIndex = 0;
```

### 5. 取得圖表數據工作簿

```java
//取得圖表資料工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. 將系列加入圖表中

```java
//將系列新增到圖表中
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. 將類別加入圖表中

```java
//在圖表中新增類別
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

### 8. 填充系列數據

```java
//填充系列數據
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

//填充系列數據點
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9. 設定間隙寬度

```java
//設定間隙寬度值
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. 儲存簡報

```java
//儲存帶有圖表的簡報
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## 在 Java 投影片中設定間隙寬度的完整原始碼

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//建立空白簡報
Presentation presentation = new Presentation();
//存取第一張投影片
ISlide slide = presentation.getSlides().get_Item(0);
//新增帶有預設資料的圖表
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
//設定圖表資料表索引
int defaultWorksheetIndex = 0;
//取得圖表資料工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//新增系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
//新增類別
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
//採取第二個圖表系列
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
//現在正在填充系列數據
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
//設定間隙寬度值
series.getParentSeriesGroup().setGapWidth(50);
//儲存帶有圖表的簡報
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## 結論

在本教學中，您學習如何使用 Aspose.Slides for Java 設定 PowerPoint 簡報中圖表的間隙寬度。調整間隙寬度可讓您控制圖表中的柱或條之間的間距，從而增強資料的視覺表示。

## 常見問題解答

### 如何變更間隙寬度值？

若要變更間隙寬度，請使用`setGapWidth`方法上的`ParentSeriesGroup`圖表系列。在提供的範例中，我們將間隙寬度設為 50，但您可以將此值調整為所需的間距。

### 我可以自訂其他圖表屬性嗎？

是的，Aspose.Slides for Java 提供了廣泛的圖表自訂功能。您可以修改各種圖表屬性，例如顏色、標籤、標題等。有關圖表自訂選項的詳細信息，請查看 API 參考。

### 在哪裡可以找到更多資源和文件？

您可以在 Aspose.Slides for Java 上找到全面的文件和其他資源[阿斯普斯網站](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
