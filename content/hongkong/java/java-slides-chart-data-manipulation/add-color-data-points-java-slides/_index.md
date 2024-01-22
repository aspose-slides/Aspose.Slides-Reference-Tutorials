---
title: 為 Java 投影片中的資料點新增顏色
linktitle: 為 Java 投影片中的資料點新增顏色
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 為 Java 投影片中的資料點新增顏色。
type: docs
weight: 10
url: /zh-hant/java/chart-data-manipulation/add-color-data-points-java-slides/
---

## 在 Java 投影片中為資料點新增色彩簡介

在本教學中，我們將示範如何使用 Aspose.Slides for Java 為 Java 投影片中的資料點新增顏色。本逐步指南包含原始程式碼範例，可協助您完成此任務。

## 先決條件

在開始之前，請確保您具備以下先決條件：

- Java開發環境
- Aspose.Slides for Java 函式庫

## 第 1 步：建立新簡報

首先，我們將使用 Aspose.Slides for Java 建立一個新的簡報。該演示文稿將作為我們圖表的容器。

```java
Presentation pres = new Presentation();
```

## 步驟 2： 新增旭日圖

現在，讓我們將旭日圖加入簡報中。我們指定圖表類型、位置和大小。

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## 第 3 步：存取資料點

要修改圖表中的資料點，我們需要訪問`IChartDataPointCollection`目的。

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## 第 4 步：自訂資料點

在此步驟中，我們將自訂特定的資料點。在這裡，我們正在更改數據點的顏色並配置標籤設定。

```java
//自訂資料點0
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);

//自訂資料點9
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());
```

## 第 5 步：儲存簡報

最後，儲存帶有自訂圖表的簡報。

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

就是這樣！您已使用 Aspose.Slides for Java 成功為 Java 投影片中的特定資料點新增顏色。

## 在 Java 幻燈片中為資料點添加顏色的完整原始程式碼

```java
Presentation pres = new Presentation();
try
{
	//文檔目錄的路徑。
	String dataDir = "Your Document Directory";
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
	IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
	dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel().getDataLabelFormat().setShowValue(true);
	IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
	branch1Label.getDataLabelFormat().setShowCategoryName(false);
	branch1Label.getDataLabelFormat().setShowSeriesName(true);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);
	IFormat steam4Format = dataPoints.get_Item(9).getFormat();
	steam4Format.getFill().setFillType(FillType.Solid);
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//去做
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

在本教學中，您學習如何使用 Aspose.Slides for Java 為 Java 投影片中的資料點新增顏色。您可以根據您的具體要求進一步客製化圖表和簡報。

## 常見問題解答

### 如何更改其他數據點的顏色？

若要變更其他資料點的顏色，您可以遵循步驟 4 中所示的類似方法。存取要自訂的資料點並修改其顏色和標籤設定。

### 我可以自訂圖表的其他方面嗎？

是的，您可以自訂圖表的各個方面，包括字體、標籤、標題等。請參閱[Aspose.Slides for Java 文檔](https://reference.aspose.com/slides/java/)了解詳細的自訂選項。

### 在哪裡可以找到更多範例和文件？

您可以在以下位置找到有關使用 Aspose.Slides for Java 的更多範例和詳細文件：[Aspose.Slides 文檔](https://reference.aspose.com/slides/java/)網站。