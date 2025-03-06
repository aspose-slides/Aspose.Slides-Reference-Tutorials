---
title: Java 投影片中的旭日圖
linktitle: Java 投影片中的旭日圖
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 使用 Aspose.Slides 在 Java 投影片中建立令人驚嘆的旭日圖。了解分步圖表建立和資料操作。
weight: 16
url: /zh-hant/java/chart-elements/sunburst-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## 使用 Aspose.Slides 介紹 Java 投影片中的旭日圖

在本教學中，您將學習如何使用 Aspose.Slides for Java API 在 PowerPoint 簡報中建立旭日圖。旭日圖是用來表示分層資料的徑向圖。我們將提供逐步說明以及原始程式碼。

## 先決條件

在開始之前，請確保您已在 Java 專案中安裝並配置了 Aspose.Slides for Java 程式庫。您可以從以下位置下載該程式庫[這裡](https://releases.aspose.com/slides/java/).

## 第 1 步：導入所需的庫

首先，匯入必要的程式庫以使用 Aspose.Slides 並在 Java 應用程式中建立 Sunburst 圖表。

```java
import com.aspose.slides.*;
```

## 第 2 步：初始化簡報

初始化 PowerPoint 簡報並指定簡報檔案的儲存目錄。

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## 步驟 3： 建立旭日圖

在投影片上建立旭日圖。我們指定圖表的位置（X、Y）和尺寸（寬度、高度）。

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## 第四步：準備圖表數據

從圖表中清除所有現有類別和系列數據，並為圖表建立數據工作簿。

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## 第 5 步：定義圖表層次結構

定義旭日圖的層級結構。您可以添加樹枝、莖和葉作為類別。

```java
//分行1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

//分行2
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## 第 6 步：將資料加入圖表中

將資料點新增至旭日圖系列。

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
```

## 第 7 步：儲存簡報

最後，使用旭日圖儲存簡報。

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## Java 投影片中旭日圖的完整原始碼

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//分行1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//分支2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
	pres.save("Sunburst.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

在本教學中，您學習如何使用 Aspose.Slides for Java API 在 PowerPoint 簡報中建立旭日圖。您已經了解如何初始化簡報、建立圖表、定義圖表層次結構、新增資料點以及儲存簡報。現在，您可以使用這些知識在 Java 應用程式中建立互動式且資訊豐富的 Sunburst 圖表。

## 常見問題解答

### 如何自訂旭日圖的外觀？

您可以透過修改顏色、標籤和樣式等屬性來自訂旭日圖的外觀。有關詳細的自訂選項，請參閱 Aspose.Slides 文件。

### 我可以為圖表添加更多數據點嗎？

是的，您可以使用以下命令在圖表中新增更多資料點`series.getDataPoints().addDataPointForSunburstSeries()`您想要包含的每個數據點的方法。

### 如何為 Sunburst 圖表新增工具提示？

要將工具提示新增至旭日圖，您可以設定資料標籤格式，以在將滑鼠懸停在圖表段上時顯示附加信息，例如值或說明。

### 是否可以建立帶有超連結的互動式旭日圖？

是的，您可以透過將超連結新增至特定圖表元素或段來建立具有超連結的互動式旭日圖。有關添加超連結的詳細信息，請參閱 Aspose.Slides 文件。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
