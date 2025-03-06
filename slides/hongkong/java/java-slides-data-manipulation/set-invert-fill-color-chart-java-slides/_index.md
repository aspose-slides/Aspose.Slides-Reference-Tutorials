---
title: 在 Java 投影片中設定反轉填滿色彩圖表
linktitle: 在 Java 投影片中設定反轉填滿色彩圖表
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides 設定 Java Slides 圖表的反轉填滿顏色。透過此逐步指南和原始碼增強圖表視覺化效果。
weight: 22
url: /zh-hant/java/data-manipulation/set-invert-fill-color-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 投影片中設定反轉填滿色彩圖表


## Java 投影片中設定反轉填滿色彩圖表簡介

在本教學中，我們將示範如何使用 Aspose.Slides for Java 在 Java Slides 中設定圖表的反轉填滿色彩。當您想要使用特定顏色來突出顯示圖表中的負值時，反轉填滿顏色是一個有用的功能。我們將提供實現這一目標的逐步說明和原始程式碼。

## 先決條件

在開始之前，請確保您具備以下先決條件：

1. Aspose.Slides for Java 程式庫已安裝。
2. Java開發環境搭建。

## 第 1 步：建立簡報

首先，我們需要建立一個簡報來新增圖表。您可以使用以下程式碼來建立簡報：

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 第 2 步：新增圖表

接下來，我們將在簡報中新增聚集長條圖。您可以這樣做：

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## 第 3 步：設定圖表數據

現在，讓我們設定圖表數據，包括系列和類別：

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

//新增系列和類別
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## 第 4 步：填充系列數據

現在，讓我們填入圖表的系列數據：

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## 第5步：設定反轉填滿顏色

若要設定圖表系列的反轉填滿顏色，可以使用以下程式碼：

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

在上面的程式碼中，我們將系列設定為負值反轉填滿顏色，並指定反轉填滿的顏色。

## 第 6 步：儲存簡報

最後，儲存帶有圖表的簡報：

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Java 投影片中設定反轉填滿色彩圖表的完整原始碼

```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
//新增系列和類別
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
//取得第一個圖表系列並填入系列資料。
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
}
finally
{
if (pres != null) pres.dispose();
}
```

## 結論

在本教學中，我們向您展示如何使用 Aspose.Slides for Java 在 Java Slides 中設定圖表的反轉填滿顏色。此功能可讓您使用特定顏色來突出顯示圖表中的負值，使您的資料在視覺上更具資訊性。

## 常見問題解答

在本節中，我們將解決一些與使用 Aspose.Slides for Java 在 Java Slides 中設定圖表的反轉填滿顏色相關的常見問題。

### 如何安裝 Aspose.Slides for Java？

您可以透過在 Java 專案中包含 Aspose.Slides JAR 檔案來安裝 Aspose.Slides for Java。您可以從以下位置下載該程式庫[Aspose.Slides for Java 下載頁面](https://releases.aspose.com/slides/java/)。請按照特定開發環境的文件中提供的安裝說明進行操作。

### 我可以自訂圖表系列中倒置填滿的顏色嗎？

是的，您可以自訂圖表系列中反向填滿的顏色。在提供的程式碼範例中，`series.getInvertedSolidFillColor().setColor(Color.RED)` line 將反轉填滿的顏色設為紅色。您可以更換`Color.RED`與您選擇的任何其他顏色。

### 如何修改 Aspose.Slides for Java 中的圖表類型？

您可以透過變更來修改圖表類型`ChartType`將圖表新增至簡報時的參數。在程式碼範例中，我們使用了`ChartType.ClusteredColumn`。您可以透過指定適當的選項來探索其他圖表類型，例如折線圖、長條圖、圓餅圖等。`ChartType`枚舉值。

### 如何將多個資料系列新增至圖表？

若要將多個資料系列新增至圖表中，您可以使用`chart.getChartData().getSeries().add(...)`您要新增的每個系列的方法。確保為每個系列提供適當的數據點和標籤，以便用多個系列填充您的圖表。

### 有沒有辦法自訂圖表外觀的其他方面？

是的，您可以使用 Aspose.Slides for Java 自訂圖表外觀的各個方面，包括軸標籤、標題、圖例等。有關自訂圖表元素和外觀的詳細指南，請參閱文件。

### 我可以以不同的格式儲存圖表嗎？

是的，您可以使用 Aspose.Slides for Java 以不同的格式儲存圖表。在提供的程式碼範例中，我們將簡報儲存為 PPTX 檔案。您可以使用不同的`SaveFormat`根據您的要求，可以選擇將其儲存為其他格式，例如 PDF、PNG 或 SVG。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
