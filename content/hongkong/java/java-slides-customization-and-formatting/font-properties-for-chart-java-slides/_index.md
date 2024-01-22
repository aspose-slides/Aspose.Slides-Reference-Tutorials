---
title: Java 投影片中圖表的字型屬性
linktitle: Java 投影片中圖表的字型屬性
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 使用 Aspose.Slides for Java 增強 Java 投影片中的圖表字體屬性。自訂字體大小、樣式和顏色，以獲得有影響力的簡報。
type: docs
weight: 11
url: /zh-hant/java/customization-and-formatting/font-properties-for-chart-java-slides/
---

## Java 投影片中圖表的字型屬性簡介

本指南將引導您使用 Aspose.Slides 在 Java Slides 中設定圖表的字體屬性。您可以自訂圖表文字的字體大小和外觀，以增強簡報的視覺吸引力。

## 先決條件

在開始之前，請確保您已將 Aspose.Slides for Java API 整合到您的專案中。如果您還沒有下載，您可以從[Aspose.Slides for Java 文檔](https://reference.aspose.com/slides/java/).

## 第 1 步：建立簡報

首先，使用以下程式碼建立一個新簡報：

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 第 2 步：新增圖表

現在，讓我們將聚集長條圖新增到您的簡報中：

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

在這裡，我們在第一張投影片的座標 (100, 100) 處加上一個寬度為 500 個單位、高度為 400 個單位的聚集長條圖。

## 第 3 步：自訂字體屬性

接下來，我們將自訂圖表的字體屬性。在此範例中，我們將所有圖表文字的字體大小設為 20：

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

此程式碼將圖表中所有文字的字體大小設定為 20 磅。

## 第 4 步：顯示資料標籤

您也可以使用以下程式碼在圖表上顯示資料標籤：

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

此程式碼行啟用圖表中第一個系列的資料標籤，在圖表列上顯示值。

## 第 5 步：儲存簡報

最後，使用自訂圖表字體屬性儲存簡報：

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

此程式碼將簡報儲存到指定目錄，檔案名稱為「FontPropertiesForChart.pptx」。

## Java 投影片中圖表字型屬性的完整原始碼

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	chart.getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 結論

在本教學中，您學習如何使用 Aspose.Slides for Java 自訂 Java Slides 中圖表的字型屬性。您可以應用這些技術來增強圖表和簡報的外觀。探索更多選項[Aspose.Slides for Java 文檔](https://reference.aspose.com/slides/java/).

## 常見問題解答

### 如何更改字體顏色？

若要變更圖表文字的字體顏色，請使用`chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);` 替換`Color.RED`與所需的顏色。

### 我可以更改字體樣式（粗體、斜體等）嗎？

是的，您可以變更字體樣式。使用`chart.getTextFormat().getPortionFormat().setFontBold(true);`使字體加粗。同樣，您可以使用`setFontItalic(true)`使其變為斜體。

### 如何自訂特定圖表元素的字體屬性？

若要自訂特定圖表元素（例如軸標籤或圖例文字）的字體屬性，您可以使用如上所示的類似方法存取這些元素並設定其字體屬性。