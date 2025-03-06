---
title: Java 投影片中圖表的第二個繪圖選項
linktitle: Java 投影片中圖表的第二個繪圖選項
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 在 Java Slides 中自訂圖表。探索第二個情節選項並增強您的簡報。
type: docs
weight: 12
url: /zh-hant/java/chart-creation/second-plot-options-charts-java-slides/
---

## Java 投影片中圖表的第二個繪圖選項簡介

在本教程中，我們將探索如何使用 Aspose.Slides for Java 為圖表新增第二個繪圖選項。第二個繪圖選項可讓您自訂圖表的外觀和行為，特別是在圓餅圖等場景中。我們將提供逐步說明和原始程式碼範例來實現這一目標。 

## 先決條件
在開始之前，請確保您已在 Java 專案中安裝並設定了 Aspose.Slides for Java。

## 第 1 步：建立簡報
讓我們從創建一個新簡報開始：

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//建立Presentation類別的實例
Presentation presentation = new Presentation();
```

## 第 2 步：將圖表新增至投影片
接下來，我們將向投影片新增圖表。在此範例中，我們將建立一個圓餅圖：

```java
//在投影片上新增圖表
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## 第 3 步：自訂圖表屬性
現在，讓我們為圖表設定不同的屬性，包括第二個繪圖選項：

```java
//顯示第一個系列的資料標籤
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

//設定第二個圓餅圖的大小（以百分比表示）
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

//以百分比分割圓餅圖
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

//設定分割位置
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## 第 4 步：儲存簡報
最後，儲存帶有圖表和第二個繪圖選項的簡報：

```java
//將簡報寫入磁碟
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## 第二個繪圖選項的完整原始碼

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//建立Presentation類別的實例
Presentation presentation = new Presentation();
//在投影片上新增圖表
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
//設定不同的屬性
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
//將簡報寫入磁碟
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## 結論

在本教程中，我們學習如何使用 Aspose.Slides for Java 為 Java Slides 中的圖表新增第二個繪圖選項。您可以自訂各種屬性來增強圖表的外觀和功能，使您的簡報資訊更豐富且更具視覺吸引力。

## 常見問題解答

### 如何更改餅圖中第二個圓餅圖的大小？

若要變更圓餅圖中第二個圓餅圖的大小，請使用`setSecondPieSize`方法如上面的程式碼範例所示。調整值以指示百分比大小。

### 什麼是`PieSplitBy` control in a Pie of Pie chart?

這`PieSplitBy`屬性控制餅圖的分割方式。您可以將其設定為`PieSplitType.ByPercentage`或者`PieSplitType.ByValue`分別以百分比或特定值分割圖表。

### 如何設定圓餅圖中的分割位置？

您可以使用以下指令設定餅圖中的分割位置：`setPieSplitPosition`方法。調整該值以指定所需的位置。