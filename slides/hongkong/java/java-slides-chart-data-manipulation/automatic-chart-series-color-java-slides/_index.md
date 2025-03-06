---
title: Java 投影片中的自動圖表系列顏色
linktitle: Java 投影片中的自動圖表系列顏色
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 在 PowerPoint 簡報中建立具有自動系列顏色的動態圖表。輕鬆增強您的數據視覺化。
weight: 14
url: /zh-hant/java/chart-data-manipulation/automatic-chart-series-color-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Aspose.Slides for Java中自動圖表系列顏色簡介

在本教程中，我們將探索如何使用 Aspose.Slides for Java 建立帶有圖表的 PowerPoint 演示文稿，並為圖表系列設定自動填滿顏色。自動填滿顏色可以讓您的圖表更具視覺吸引力，並讓庫為您選擇顏色，從而節省您的時間。

## 先決條件

在開始之前，請確保您的專案中安裝了 Aspose.Slides for Java 程式庫。您可以從以下位置下載：[這裡](https://releases.aspose.com/slides/java/).

## 第 1 步：建立新簡報

首先，我們將建立一個新的 PowerPoint 簡報並在其中新增一張投影片。

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//建立Presentation類別的實例
Presentation presentation = new Presentation();
```

## 第 2 步：將圖表新增至投影片

接下來，我們將在投影片中新增聚集長條圖。我們還將設定第一個系列來顯示值。

```java
//存取第一張投影片
ISlide slide = presentation.getSlides().get_Item(0);
//新增帶有預設資料的圖表
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
//將第一個系列設定為“顯示值”
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## 第 3 步：填入圖表數據

現在，我們將用數據填充圖表。我們將首先刪除預設產生的系列和類別，然後新增新的系列和類別。

```java
//設定圖表資料表索引
int defaultWorksheetIndex = 0;
//取得圖表資料工作表
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//刪除預設產生的系列和類別
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

//新增系列
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

//新增類別
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## 第 4 步：填充系列數據

我們將填入系列 1 和系列 2 的系列資料。

```java
//取得第一個圖表系列
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//現在正在填充系列數據
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

//採取第二個圖表系列
series = chart.getChartData().getSeries().get_Item(1);
//現在正在填充系列數據
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## 步驟5：設定係列的自動填滿顏色

現在，讓我們為圖表系列設定自動填滿顏色。這將使圖書館為我們選擇顏色。

```java
//設定係列的自動填滿顏色
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## 第 6 步：儲存簡報

最後，我們將帶有圖表的簡報儲存到 PowerPoint 文件中。

```java
//儲存帶有圖表的簡報
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Java 投影片中自動圖表系列顏色的完整原始碼

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//建立Presentation類別的實例
Presentation presentation = new Presentation();
try
{
	//存取第一張投影片
	ISlide slide = presentation.getSlides().get_Item(0);
	//新增帶有預設資料的圖表
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	//將第一個系列設定為“顯示值”
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	//設定圖表資料表索引
	int defaultWorksheetIndex = 0;
	//取得圖表資料工作表
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	//刪除預設產生的系列和類別
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	//新增系列
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	//新增類別
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	//取得第一個圖表系列
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	//現在正在填充系列數據
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	//設定係列的自動填滿顏色
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	//採取第二個圖表系列
	series = chart.getChartData().getSeries().get_Item(1);
	//現在正在填充系列數據
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	//設定係列的填滿顏色
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	//儲存帶有圖表的簡報
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 結論

在本教程中，我們學習如何使用 Aspose.Slides for Java 建立帶有圖表的 PowerPoint 演示文稿，並為圖表系列設定自動填滿顏色。自動顏色可以增強圖表的視覺吸引力，並使您的簡報更具吸引力。您可以根據您的具體要求進一步自訂圖表。

## 常見問題解答

### 如何在 Aspose.Slides for Java 中設定圖表系列的自動填滿顏色？

若要在 Aspose.Slides for Java 中設定圖表系列的自動填入顏色，請使用下列程式碼：

```java
//設定係列的自動填滿顏色
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

此程式碼將使庫自動為圖表系列選擇顏色。

### 如果需要，我可以自訂圖表顏色嗎？

是的，您可以根據需要自訂圖表顏色。在提供的範例中，我們使用了自動填滿顏色，但您可以透過修改`FillType`和`SolidFillColor`系列格式的屬性。

### 如何為圖表新增其他系列或類別？

若要為圖表新增其他系列或類別，請使用`getSeries()`和`getCategories()`圖表的方法`ChartData`目的。您可以透過指定資料和標籤來新增系列和類別。

### 是否可以進一步格式化圖表和標籤？

是的，您可以根據需要進一步設定圖表、系列和標籤的格式。 Aspose.Slides for Java 為圖表提供了廣泛的格式化選項，包括字體、顏色、樣式等。您可以瀏覽文件以獲取有關格式選項的更多詳細資訊。

### 在哪裡可以找到有關使用 Aspose.Slides for Java 的更多資訊？

有關 Aspose.Slides for Java 的更多資訊和詳細文檔，您可以存取參考文檔[這裡](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
