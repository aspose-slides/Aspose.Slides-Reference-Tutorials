---
"description": "學習使用 Aspose.Slides 建立令人驚嘆的圖表並管理 Java 投影片中的屬性。帶有原始程式碼的分步指南，用於強大的演示。"
"linktitle": "在 Java 投影片中管理屬性圖表"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 Java 投影片中管理屬性圖表"
"url": "/zh-hant/java/data-manipulation/manage-properties-charts-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 投影片中管理屬性圖表


## 使用 Aspose.Slides 管理 Java Slides 中的屬性和圖表簡介

在本教程中，我們將探討如何使用 Aspose.Slides 管理屬性和在 Java 投影片中建立圖表。 Aspose.Slides 是一個用於處理 PowerPoint 簡報的強大的 Java API。我們將逐步介紹整個過程，包括原始碼範例。

## 先決條件

在開始之前，請確保您已在專案中安裝並設定了 Java 的 Aspose.Slides 庫。您可以從下載 [這裡](https://releases。aspose.com/slides/java/).

## 在投影片中新增圖表

若要將圖表新增至投影片，請依照下列步驟操作：

1. 導入必要的類別並建立 Presentation 類別的實例。

```java
// 建立 Presentation 類別的實例
Presentation presentation = new Presentation();
```

2. 存取您想要新增圖表的投影片。在這個例子中，我們訪問第一張投影片。

```java
// 存取第一張投影片
ISlide slide = presentation.getSlides().get_Item(0);
```

3. 新增具有預設資料的圖表。在本例中，我們新增一個 StackedColumn3D 圖表。

```java
// 新增帶有預設資料的圖表
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## 設定圖表數據

要設定圖表數據，我們需要建立一個圖表數據工作簿並新增系列和類別。請依照以下步驟操作：

4. 設定圖表資料表的索引。

```java
// 設定圖表資料表的索引
int defaultWorksheetIndex = 0;
```

5. 取得圖表數據工作簿。

```java
// 取得圖表資料工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. 在圖表中新增系列。在此範例中，我們新增了兩個系列，分別名為「系列 1」和「系列 2」。

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. 在圖表中新增類別。這裡我們新增三個類別。

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## 設定 3D 旋轉屬性

現在，讓我們設定圖表的 3D 旋轉屬性：

8. 設定直角軸。

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. 設定 X 軸和 Y 軸的旋轉角度。在這個例子中，我們將 X 旋轉 40 度，將 Y 旋轉 270 度。

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. 將深度百分比設定為 150。

```java
chart.getRotation3D().setDepthPercents(150);
```

## 填充系列數據

11. 取第二個圖表系列並用數據點填充它。

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// 填充系列數據
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## 調整重疊

12. 設定係列的重疊值。例如，您可以將其設為 100，表示不重疊。

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## 儲存簡報

最後，將簡報儲存到磁碟。

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

就是這樣！您已成功使用 Java 中的 Aspose.Slides 建立具有自訂屬性的 3D 堆積長條圖。

## Java 投影片中管理屬性圖表的完整原始碼

```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
// 建立 Presentation 類別的實例
Presentation presentation = new Presentation();
// 存取第一張投影片
ISlide slide = presentation.getSlides().get_Item(0);
// 新增帶有預設資料的圖表
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
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
// 設定 Rotation3D 屬性
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// 採取第二張圖表系列
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// 現在填充系列數據
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// 設定重疊值
series.getParentSeriesGroup().setOverlap((byte) 100);
// 將簡報寫入磁碟
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## 結論

在本教程中，我們深入研究了使用 Aspose.Slides 在 Java 投影片中管理屬性和建立圖表的世界。 Aspose.Slides 是一個強大的 Java API，可讓開發人員有效率地處理 PowerPoint 簡報。我們介紹了基本步驟並提供了原始程式碼範例來引導您完成整個過程。

## 常見問題解答

### 我該如何更改圖表類型？

您可以透過修改 `ChartType` 新增圖表時的參數。有關可用的圖表類型，請參閱 Aspose.Slides 文件。

### 我可以自訂圖表顏色嗎？

是的，您可以透過設定係列資料點或類別的填滿屬性來自訂圖表顏色。

### 如何為系列添加更多數據點？

您可以使用 `series.getDataPoints().addDataPointForBarSeries()` 方法並指定包含資料值的儲存格。

### 如何設定不同的旋轉角度？

若要為 X 軸和 Y 軸設定不同的旋轉角度，請使用 `chart.getRotation3D().setRotationX()` 和 `chart.getRotation3D().setRotationY()` 具有所需的角度值。

### 我還可以自訂哪些其他 3D 屬性？

您可以參考 Aspose.Slides 文件來探索圖表的其他 3D 屬性，例如深度、透視和照明。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}