---
"description": "了解如何使用 Aspose.Slides for Java 設定 Java Slides 中的間隙寬度。增強 PowerPoint 簡報的圖表視覺效果。"
"linktitle": "在 Java 投影片中設定間隙寬度"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 Java 投影片中設定間隙寬度"
"url": "/zh-hant/java/data-manipulation/set-gap-width-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 投影片中設定間隙寬度


## Aspose.Slides for Java 中間隙寬度設定簡介

在本教學中，我們將指導您使用 Aspose.Slides for Java 設定 PowerPoint 簡報中圖表的間隙寬度的過程。間隙寬度決定了圖表中長條圖或長條圖之間的間距，使您可以控制圖表的視覺外觀。

## 先決條件

在開始之前，請確保您已安裝 Aspose.Slides for Java 程式庫。您可以從 Aspose 網站下載 [這裡](https://releases。aspose.com/slides/java/).

## 逐步指南

請依照下列步驟使用 Aspose.Slides for Java 設定圖表中的間隙寬度：

### 1.創建一個空的演示文稿

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";

// 建立空的簡報 
Presentation presentation = new Presentation();
```

### 2. 存取第一張投影片

```java
// 存取第一張投影片
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. 新增帶有預設資料的圖表

```java
// 新增具有預設資料的圖表
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4.設定圖表資料表的索引

```java
// 設定圖表資料表的索引
int defaultWorksheetIndex = 0;
```

### 5.取得圖表數據工作簿

```java
// 取得圖表資料工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6.向圖表新增系列

```java
// 在圖表中新增系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7.向圖表新增類別

```java
// 在圖表中新增類別
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

### 8.填充系列數據

```java
// 填充系列數據
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// 填充系列數據點
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9.設定間隙寬度

```java
// 設定間隙寬度值
series.getParentSeriesGroup().setGapWidth(50);
```

### 10.儲存簡報

```java
// 將簡報與圖表一起保存
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Java Slides 中設定間隙寬度的完整原始碼

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
// 建立空白簡報 
Presentation presentation = new Presentation();
// 存取第一張投影片
ISlide slide = presentation.getSlides().get_Item(0);
// 新增帶有預設資料的圖表
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
// 設定圖表資料表的索引
int defaultWorksheetIndex = 0;
// 取得圖表資料工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// 新增系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// 新增類別
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// 採取第二張圖表系列
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// 現在填充系列數據
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// 設定 GapWidth 值
series.getParentSeriesGroup().setGapWidth(50);
// 將簡報與圖表一起保存
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## 結論

在本教學中，您學習如何使用 Aspose.Slides for Java 設定 PowerPoint 簡報中圖表的間隙寬度。調整間隙寬度可讓您控制圖表中列或條之間的間距，從而增強資料的視覺表現。

## 常見問題解答

### 如何變更間隙寬度值？

若要變更間隙寬度，請使用 `setGapWidth` 方法 `ParentSeriesGroup` 圖表系列。在提供的範例中，我們將間隙寬度設為 50，但您可以根據所需的間距調整此值。

### 我可以自訂其他圖表屬性嗎？

是的，Aspose.Slides for Java 提供了廣泛的圖表自訂功能。您可以修改各種圖表屬性，例如顏色、標籤、標題等。查看 API 參考以取得有關圖表自訂選項的詳細資訊。

### 在哪裡可以找到更多資源和文件？

您可以在 Aspose.Slides for Java 上找到全面的文件和其他資源 [Aspose 網站](https://reference。aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}