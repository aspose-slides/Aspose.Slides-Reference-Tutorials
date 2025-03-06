---
title: 在 Java 投影片中管理屬性圖表
linktitle: 在 Java 投影片中管理屬性圖表
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 學習使用 Aspose.Slides 建立令人驚嘆的圖表並管理 Java 投影片中的屬性。具有原始程式碼的逐步指南，可實現強大的演示。
weight: 13
url: /zh-hant/java/data-manipulation/manage-properties-charts-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## 使用 Aspose.Slides 管理 Java 投影片中的屬性和圖表的簡介

在本教程中，我們將探索如何使用 Aspose.Slides 在 Java 投影片中管理屬性和建立圖表。 Aspose.Slides 是一個功能強大的 Java API，用於處理 PowerPoint 簡報。我們將逐步完成整個過程，包括原始碼範例。

## 先決條件

在開始之前，請確保您已在專案中安裝並設定了 Java 的 Aspose.Slides 程式庫。您可以從以下位置下載：[這裡](https://releases.aspose.com/slides/java/).

## 將圖表新增至投影片

若要將圖表新增至投影片，請依照下列步驟操作：

1. 導入必要的類別並建立Presentation 類別的實例。

```java
//建立Presentation類別的實例
Presentation presentation = new Presentation();
```

2. 存取要新增圖表的投影片。在此範例中，我們存取第一張投影片。

```java
//存取第一張投影片
ISlide slide = presentation.getSlides().get_Item(0);
```

3. 新增包含預設資料的圖表。在本例中，我們將新增 StackedColumn3D 圖表。

```java
//新增帶有預設資料的圖表
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## 設定圖表數據

要設定圖表數據，我們需要建立圖表數據工作簿並新增系列和類別。按著這些次序：

4. 設定圖表資料表的索引。

```java
//設定圖表資料表索引
int defaultWorksheetIndex = 0;
```

5. 取得圖表數據工作簿。

```java
//取得圖表資料工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. 將系列新增到圖表中。在此範例中，我們新增兩個名為「Series 1」和「Series 2」的系列。

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. 在圖表中新增類別。在這裡，我們新增三個類別。

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## 設定 3D 旋轉屬性

現在，讓我們為圖表設定 3D 旋轉屬性：

8. 設定直角軸。

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. 設定 X 軸和 Y 軸的旋轉角度。在此範例中，我們將 X 軸旋轉 40 度，Y 軸旋轉 270 度。

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. 將深度百分比設定為 150。

```java
chart.getRotation3D().setDepthPercents(150);
```

## 填充系列數據

11. 取得第二個圖表系列並用數據點填滿它。

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

//填充系列數據
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## 調整重疊

12. 設定係列的重疊值。例如，您可以將其設為 100 以實現無重疊。

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## 儲存簡報

最後，將簡報儲存到磁碟。

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

就是這樣！您已使用 Java 中的 Aspose.Slides 成功建立了具有自訂屬性的 3D 堆積長條圖。

## 在 Java 投影片中管理屬性圖表的完整原始碼

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//建立Presentation類別的實例
Presentation presentation = new Presentation();
//存取第一張投影片
ISlide slide = presentation.getSlides().get_Item(0);
//新增帶有預設資料的圖表
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
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
//設定 Rotation3D 屬性
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
//採取第二個圖表系列
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
//現在正在填充系列數據
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
//設定重疊值
series.getParentSeriesGroup().setOverlap((byte) 100);
//將簡報寫入磁碟
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## 結論

在本教程中，我們深入研究了使用 Aspose.Slides 在 Java 投影片中管理屬性和建立圖表的領域。 Aspose.Slides 是一個強大的 Java API，可讓開發人員有效率地處理 PowerPoint 簡報。我們介紹了基本步驟並提供了原始程式碼範例來引導您完成整個過程。

## 常見問題解答

### 如何更改圖表類型？

您可以透過修改來更改圖表類型`ChartType`新增圖表時的參數。請參閱 Aspose.Slides 文件以了解可用的圖表類型。

### 我可以自訂圖表顏色嗎？

是的，您可以透過設定係列資料點或類別的填滿屬性來自訂圖表顏色。

### 如何為系列添加更多數據點？

您可以使用以下命令將更多資料點新增至系列中`series.getDataPoints().addDataPointForBarSeries()`方法並指定包含資料值的儲存格。

### 如何設定不同的旋轉角度？

若要為 X 軸和 Y 軸設定不同的旋轉角度，請使用`chart.getRotation3D().setRotationX()`和`chart.getRotation3D().setRotationY()`與所需的角度值。

### 我還可以自訂哪些其他 3D 屬性？

您可以透過參考 Aspose.Slides 文件來探索圖表的其他 3D 屬性，例如深度、透視和照明。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
